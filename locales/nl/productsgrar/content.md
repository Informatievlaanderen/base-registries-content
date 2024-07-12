Het bestaat uit verschillende registers:
* Gemeenteregister
* Postinforegister
* Straatnamenregister
* Adressenregister
* Gebouwen- en gebouweenhedenregister
* Percelenregister

Voor straatnamen, adressen, gebouwen & gebouweneheden is het gebouwen- en adressenregister de authentieke bron. 

Deze informatie kan op verschillende manieren geraadpleegd worden:
* [Via de read endpoints](#readendpointsgrar)
* [Via de feed endpoints](#feedendpointsgrar)
* [Via de downloadbestanden](#downloadbestandgrar)
* [Via de WMS, WFS & OGC API features](#wmswfsogcgrar)
* [Via de Geolocation service](#geolocationservice)

## Read endpoints {#readendpointsgrar}

De read endpoints van het gebouwen- en adressenregister zijn REST API's en laten toe om op een snelle manier informatie van objecttypes te tonen/op te zoeken of te implementeren in toepassingen. De objecttypes die wordt aangeroepen in deze API's kunnen niet worden gewijzigd. Het is mogelijk om details van de objecttypes op te vragen, maar ook lijsten van de objecttypes op basis van parameters. Welke parameters er meegegeven kunnen worden is per read endpoint verschillend.

### Documentatie

Elk read endpoint is ook gedocumenteerd. Deze documentatie kan [hier](https://docs.basisregisters.staging-vlaanderen.be/docs/api-documentation.html#tag/api-documentation.html) geraadpleegd worden.
          
### Toegang
De read endpoints zijn anoniem raadpleegbaar echter is er een beperking aanwezig op het aantal verzoeken dat u tegelijkertijd kan versturen naar deze endpoints. Wanneer u een API key meegeeft dan zal u meer requests kunnen versturen.

Meer informatie omtrent API keys vind je [hier](/apikey).

### De read endpoints zijn comform aan het OSLO-model
De v2 read endpoints zijn conform aan het OSLO-model.

**Wat betekent 'conform aan het OSLO-model'?**

Door informatie conform aan het OSLO-model te ontsluiten, kan deze vlot gecombineerd worden met datasets op het wereldwijde web. Contextuele informatie wordt aan de response van de endpoints gekoppeld waardoor ze geschikt zijn om te gebruiken in Linked Data toepassingen.
Meer informatie over OSLO kan u hier vinden: https://overheid.vlaanderen.be/producten-diensten/oslo.

### Hoeveel objecten worden er getoond in de lijst endpoints? 

Default als de parameter `limit` niet meegegeven is, zitten er maximum 100 objecten in de lijst. Wanneer de parameter `limit` is meegegeven, kan er gekozen worden wat het maximum aantal objecten is dat kan worden teruggegeven. Dit kan van waarde 0 tot en met 500 gaan. Geeft u een getal mee hoger dan 500 dan zullen er slechts maximum 500 objecten getoond worden. 

## Feed endpoints {#feedendpointsgrar}

De feed endpoints van het gebouwen- en adressenregister laten toe om alle wijzigingen per objecttype of ‘resource’ op te vragen. Deze maken gebruik van Atom als standaard. 

### Documentatie

Elk feed endpoint is ook gedocumenteerd. Deze documentatie kan [hier](https://docs.basisregisters.staging-vlaanderen.be/docs/api-documentation.html#tag/Feeds) geraadpleegd worden.
Een overzicht van alle mogelijke business events en de betekenis van de attributen onder het blokje `<event>` kan [hier](https://api.basisregisters.staging-vlaanderen.be/v2/info/events?tags=sync) gevonden worden. [Hier](https://api.basisregisters.staging-vlaanderen.be/v2/info/events?tags=edit) kunnen enkel de nieuwe events (na migratie) gevonden worden. 

### Beoogde toepassing

Aan de hand van een feed kan u de wijzigingen op drie manieren opvragen: als gebeurtenissen(‘business events’), als de daaruit resulterende objectversies, of een combinatie van beide. Dit doet u door aan de `embed` parameter respectievelijk `event`, `object` of `object,event` mee te geven.

U gebruikt de `from` parameter om een startpunt te kiezen vanaf waar u de wijzigingen wilt binnenhalen, in combinatie met de `limit` parameter voor het aantal wijzigingen.

Deze functionaliteit stelt u in staat een pull-based mechanisme te bouwen om op de hoogte te blijven van voor u relevante wijzigingen. Zo kan u uw lokale databank bijwerken met de laatst beschikbare informatie uit het centrale register, of kan u bijvoorbeeld de gebeurtenissen als trigger gebruiken om uw bedrijfsprocessen te activeren (bv. IF[‘AddressWasRetired’ AND ‘dossier gekoppeld aan adres’] THEN ‘check of dossier mag afgesloten worden’).

### Aan de slag
In pseudo-code zou u als volgt wijzigingen binnenhalen:
* Roep het feed endpoint aan van het objecttype dat u wenst, zonder `from` parameter.
* Lees het `<link>` veld met `rel="next"` uit om de volgende pagina met wijzigingen te weten te komen.
* Lees de gevraagde gegevens uit en sla het `<id>` veld van de laatste `<entry>` op de pagina op zodat u weet tot hoever u de wijzigingen reeds verwerkt hebt.
* Roep nu de volgende pagina met wijzigingen aan.
* Herhaal dit tot u alle gegevens hebt verwerkt en er geen volgende pagina meer is.
        
Wanneer uw proces zou stopgezet of onderbroken worden, kan u eenvoudig terug oppikken waar u gebleven was:
* Roep opnieuw het feed endpoint aan, maar dit keer met de `from` parameter 1 groter dan het laatste `<id>` veld dat u hebt uitgelezen.
* Voer bovenstaande stappen uit om alle gegevens te verwerken.

In het veld `<content>` kan u het event en/of de objectversiedetails terugvinden per wijziging (`<entry>`).

### PersistentObjectId
De persistentLocalId is het objectId dat gebruikt wordt in de read endpoints en de andere producten van het gebouwen- en adressenregister. Vanaf het eerste event van een object is dit persistenLocalId beschikbaar. 

### Welk eventid als start nemen om de feed endpoints te beginnen lezen

Het is mogelijk om bij al de feed endpoints te starten van eventid 0. Echter zijn de eerste events, events gebaseerd op het CRAB. Doordat CRAB is uitgeschakeld en de nieuwe events anders zijn raden we aan om te vertrekken vanaf het eerste migratie event of vanaf het laatste migratie event.
Dit migratie event is tevens ook een snapshot van dat object op die moment. 

Hieronder staan de migratie eventid's per register. Voor de feed endpoints gemeenten en postinfo kan er wel vertrokken worden vanaf 0 aangezien hier geen veranderingen voor zijn gebeurd.

#### Eerste migratie eventid:
- Feed straatnamen: 1910883 
- Feed adressen: 132217751
- Feed gebouwen- en gebouweenheden: 254204946
- Feed percelen: 121611733

#### Laatste migratie eventid:
- Feed straatnamen: 2232254
- Feed adressen: 140572240
- Feed gebouwen- en gebouweenheden: 265905563
- Feed percelen: 133515551

### Interne events
In de feed endpoints kan u alle eventids terugvinden van alle aangeboden objecttypes. Echter zal u merken dat er soms eventids niet aanwezig zijn. De eventids die niet getoond worden, zijn interne events en niet beschikbaar voor de externe gebruikers. Wanneer u een eventid van een intern event meegeeft in de URL dan zal automatisch het eerstvolgende extern eventid na het meegegeven eventid in de response getoond worden.

### API key verplicht
Om de Feeds te gebruiken is het verplicht om een API key mee te geven. Als u dit namelijk niet doet dan krijgt u een errormelding 401 als response terug.
Meer informatie omtrent API keys vind je [hier](/apikey).

### Provenance
In het veld Provenance staat de metadata van een event. Het bestaat uit 3 onderdelen:
* `Timestamp/Tijdstip`: In dit veld staat het tijdstip waarop het event is uitgevoerd.
* `Organisation/Organisatie`: In dit veld staat de organisatie die de agent vertegenwoordigt bij het uitvoeren van een specifieke activiteit en waarvan hij/zij de vereiste autoriteit/verantwoordelijkheid heeft gekregen om dit te doen. De mogelijke waarden bij onderdeel `Event` zijn: Unknown, Municipality, NationalRegister, Akred, TeleAtlas, Vlm, Agiv, Aiv, DigitaalVlaanderen, Ngi, DePost, NavTeq, Vkbo of Other. De mogelijke waarden bij onderdeel `Object` zijn: Onbekend, Gemeente, Federale Overheidsdienst Binnenlandse Zaken (Rijksregister), Federale Overheidsdienst Financiën (Algemene Administratie van de Patrimoniumdocumentatie), TeleAtlas, Vlaamse Landmaatschappij, Agentschap voor Geografische Informatie Vlaanderen, Agentschap Informatie Vlaanderen, Digitaal Vlaanderen, Nationaal Geografisch Instituut, bpost, NavTeq, Coördinatiecel Vlaams e-government of Andere.
* `Reason/Reden`: In dit veld staat de aanleiding of motivatie voor de activiteit op de entiteit.

### Timestamps 
De feed bevat een aantal velden waarin een timestamp staat. Hieronder staat de betekenis van de verschillende timestamps.
* `<Feed> <Updated>` : Tijdstip waarop de data feed het laatst gewijzigd werd.
* `<Entry> <Updated>` : Tijdstip waarop het event zich voordeed.
* `<Entry> <Published>` : Tijdstip waarop de eerste versie van het object aangeboden werd.

### Hoeveel events worden er getoond? 

Default als de parameter `limit` niet meegegeven is, zitten er maximum 100 events in de lijst. Wanneer de parameter `limit` is meegegeven, kan er gekozen worden wat het maximum aantal events is dat kan worden teruggegeven. Dit kan van waarde 0 tot en met 500 gaan. Geeft u een getal mee hoger dan 500 dan zullen er slechts maximum 500 events getoond worden. 

## Downloadbestanden {#downloadbestandgrar}

Er zijn in totaal 4 downloadbestanden van het gebouwen- en adressenregister:
- 1 met alle data van het gebouwen- en adressenregister: https://download.vlaanderen.be/product/10142-gebouwen-en-adressenregister.
- 1 met alle straatnamen van het gebouwen- en adressenregister: https://download.vlaanderen.be/product/10143-gebouwen-en-adressenregister-straatnamen.
- 1 met alle adressen van het gebouwen- en adressenregister: https://download.vlaanderen.be/product/10145-gebouwen-en-adressenregister-adressen.
- 1 met alle adressen en adreskoppelingen van het gebouwen- en adressenregister: https://download.vlaanderen.be/product/10144-gebouwen-en-adressenregister-adreskoppelingen.

Deze bestanden bevatten data over heel Vlaanderen, daarom is het niet mogelijk om enkel de data van een bepaalde gemeente op te vragen. Ook is het niet mogelijk om het downloadproduct van het gebouwen- en adressenregister als verschilbestand op te vragen. 

Deze downloadbestanden worden elke nacht gegenereerd. Wanneer de generatie die dag niet gelukt is dan zal er een downloadbestand gedownload worden van de laatste datum waarop de generatie gelukt is. De downloadbestanden zijn een zip file met daarin een aantal bestanden van verschillende formaten. De formaten die hierin kunnen teruggevonden worden zijn: .dbf, .shp, .prj & .shx. 

### Inhoud volledig downloadbestand gebouwen- en adressenregister

| Bestandnaam |  Formaat .dbf | Formaat .prj | Formaat .shp | Formaat .shx | Inhoud bestand |
|:-:|:-:|:-:|:-:|:-:|:-:|
| Adres | x | x | x | x | Alle Vlaamse adressen met de bijhorende attributen|
| Adres_metadata | x | \ | \ | \ | Bevat de parameter 'Latest_event_id' voor feed adressen (1) |
| AdresGebouweenheidKoppelingen | x | \ | \ | \ | Alle Vlaamse adressen met hun bijhorende gekoppelde gebouweenhe(i)d(en) objectId(s)|
| AdresPerceelKoppelingen | x | \ | \ | \ | Alle Vlaamse adressen met hun bijhorende gekoppelde perce(e)l(en) objectId(s) |
| CrabHuisnummer | x | \ | \ | \ | Alle Vlaamse crabHuisnummers met hun bijhorende GRAR adres objectId |
| CrabSubadres | x | \ | \ | \ | Alle Vlaamse crabSubadressen met hun bijhorende GRAR adres objectId  |
| Gebouw | x | x | x | x | Alle Vlaamse gebouwen met de bijhorende attributen |
| Gebouw_metadata | x | \ | \ | \ |  Bevat de parameter 'Latest_event_id' voor feed gebouwen (1) |
| Gebouweenheid | x | x | x | x | Alle Vlaamse gebouweenheden met de bijhorende attributen |
| Gebouweeneheid_metadata | x | \ | \ | \ |  Bevat de parameter 'Latest_event_id' voor feed gebouwen (1) |
| Gemeente | x | \ | \ | \ | Alle Belgische gemeenten met de bijhorende attributen in de eerste officiële taal van de gemeente|
| Gemeente_metadata | x | \ | \ | \ |  Bevat de parameter 'Latest_event_id' voor feed gemeenten (1) |
| Perceel | x | \ | \ | \ | Alle Vlaamse percelen met de bijhorende attributen |
| Perceel_metadata | x | \ | \ | \ |  Bevat de parameter 'Latest_event_id' voor feed percelen (1) |
| Postinfo | x | \ | \ | \ | Alle postcodes aangelever door bPost |
| Postinfo_metadata | x | \ | \ | \ |  Bevat de parameter 'Latest_event_id' voor feed postinfo (1) |
| Straatnaam | x | \ | \ | \ | Alle Belgische straatnamen met de bijhorende attributen in de eerste officiële taal van de gemeente|
| Straatnaam_metadata | x | \ | \ | \ |  Bevat de parameter 'Latest_event_id' voor feed straatnamen (1) |

(1) Om aan de slag te gaan met de feed endpoints moet dit momenteel van het eerste eventid tot het laatste eventid uitgelezen worden. Om dit te vermijden kan er vanaf nu vertrokken worden van het downloadbestand gebouwen- en adressenregister. Hiervoor zitten er bij het downoadbestand ‘_metadata.dbf’ files. In deze files staat het ‘Latest_event_id’. Dit id wordt in de overeenkomstige feed endpoint meegegeven bij de parameter ‘from’ & dat is het startpunt vanaf waar de feed endpoints worden ingelezen op basis van het downloadbestand.

vb. In de file Adres_metadata.dbf staat er dat het Latest_event_id = 100 dan wordt er in de feed endpoint adressen het volgende meegegeven: https://api.basisregisters.staging-vlaanderen.be/v2/feeds/adressen?embed=object,event&from=100.

### Handleiding
Om meer te weten te komen over hoe het downloadbestand te gebruiken, kan deze handleiding gedownload worden: [Handleiding opsplitsen donwloadbestand gebouwen- en adressenregister](https://github.com/Informatievlaanderen/base-registries-content/files/11381530/CookBook_opsplitsen_downloadbestand_gebouwen-_en_adressenregister.docx).

### Feed endpoints
Om aan de slag te gaan met de feed endpoints van het gebouwen- en adressenregister kan er ook vertrokken worden vanaf het downloadbestand. Zo moeten de feed endpoints niet volledig van het eerste eventid tot het laatste eventid uitgelezen worden. In het downloadbestand zijn er namelijk bestanden met in hun naamgeving ‘_metadata.dbf’. In deze bestanden staat het ‘Latest_event_id’. Dit id wordt in de overeenkomstige feed endpoint meegegeven bij de parameter ‘from’ & dat is het startpunt vanaf waar de feed endpoints kan worden ingelezen op basis van het downloadbestand.  
* vb. In het bestand Adres_metadata.dbf staat er dat het Latest_event_id = 100 dan wordt er in de feed endpoint adressen het volgende meegegeven: `https://api.basisregisters.vlaanderen.be/v1/feeds/adressen?embed=object,event&from=100`.

### Bestanden crabHuisnummer & crabSubadres
In het downloadbestand zijn er ook 2 bestanden te vinden die de mapping maken tussen CRAB & het gebouwen- en adressenregister, namelijk crabHuisnummer.dbf & crabSubadres.dbf. De adres objectid's die in het gebouwen- en adressenregister gebruikt worden zijn andere objectId's dan in het CRAB. Omdat er moet worden overgeschakeld van CRAB naar het gebouwen- en adressenregister, werden deze bestanden voorzien zodat er vlot kan overgeschakeld worden. De laatste versie van deze CRAB objectId's zal nog worden bijwerkt tot en met 1 november 2023. Deze bestanden zullen nog bijgehouden worden na 1 november 2022, maar zullen geen updates meer kennen. Vanaf 1 maart 2024 worden deze bestanden uit het downloadbestand gehaald. 


## WMS, WFS & OGC API features {#wmswfsogcgrar}

Het gebouwen- en adressenregister wordt ook als WMS, WFS & OGC API features ontsloten:
* De WMS maakt het mogelijk om adressen, gebouwen & gebouweenheden van het gebouwen- en adressenregister te visualiseren op een kaart. Per status is er een laag voorzien. Meer informatie over wat een WMS is, kan [hier][5] gevonden worden. 
* De WFS maakt het mogelijk om geografische bevragingen te doen op adressen, gebouwen en gebouweenheden van het gebouwen- en adressenregister. Meer informatie over wat een WFS is, kan [hier][6] gevonden worden.
* De standaard [OGC API Features][9], ontwikkeld door het Open Geospatial Consortium (OGC), specificeert de vereisten en aanbevelingen voor API’s met betrekking tot ruimtelijke gegevens. Het laat toe de adressen, gebouwen en gebouweenheden geometrisch te bevragen. 

Alle URL's van de WMS'en, WFS'en en OGC API features van het gebouwen- en adressenregister kunnen gevonden worden in de catalogus van datavindplaats. 

### WMS
* [WMS gebouwenregister][1]
* [WMS adressenregister][2]

### WFS
* [WFS gebouwenregister][3]
* [WFS adressenregister][4]

### OGC API features
* [OGC API features gebouwenregister][7]
* [OGC API features adressenregister][8]

## Geolocation service {#geolocationservice}

Meer informatie kan u op deze pagina terugvinden: [Geolocation][11].


[1]:https://www.vlaanderen.be/datavindplaats/catalogus/wms-gebouwenregister
[2]:https://www.vlaanderen.be/datavindplaats/catalogus/wms-adressenregister
[3]:https://www.vlaanderen.be/datavindplaats/catalogus/wfs-gebouwenregister
[4]:https://www.vlaanderen.be/datavindplaats/catalogus/wfs-adressenregister
[5]:https://vlaanderen.be/digitaal-vlaanderen/onze-oplossingen/geografische-webdiensten/ons-gis-aanbod/raadpleegdiensten
[6]:https://www.vlaanderen.be/digitaal-vlaanderen/onze-oplossingen/geografische-webdiensten/ons-gis-aanbod/overdrachtdiensten
[7]:https://www.vlaanderen.be/datavindplaats/catalogus/ogc-api-features-gebouwenregister
[8]:https://www.vlaanderen.be/datavindplaats/catalogus/ogc-api-features-adressenregister
[9]:https://ogcapi.ogc.org/features/
[10]:https://dynamicforms.crmiv.vlaanderen.be/DynamicForms/Page/Show/CfDJ8M4Eu9v84l9JmW3p7WGylS-u2ToCLC5KvqQZmZ4G99X5TBULO4n0LCDpm7870eDUOk90hogqVcE7BCVQf2u_4WlsZ7B8friBrkyuAqmXYpIX_BzvQVVo8eUZyNd-njc33Y-Z-B87y03Y2Jgukp2AN5U93jT1Xv2l0afgvenLD9k0fasSMJkt4uNzKmlr_gILGrOy%2FJSqnRom_MLu0h7sALJ8uNvPywCMsZ1zy5Lal4h63?path=APIKey-aanvraag
[11]:https://www.vlaanderen.be/digitaal-vlaanderen/onze-oplossingen/geografische-webdiensten/ons-api-aanbod/geolocation-service
