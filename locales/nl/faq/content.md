Hieronder vindt u een overzicht van de meest voorkomende vragen met hun antwoorden die onze gebruikers hebben over de basisregisters.
Als u een vraag heeft die hieronder niet beantwoord wordt, mail dan naar digitaal.vlaanderen@vlaanderen.be.

* [Algemene vragen](#algemenevragen)
* [Vragen gebouwen- en adressenregister](#vragengebouwenenadressenregister)

  
## Algemene vragen {#algemenevragen}
 
<details>

<summary>1.1 - Wat is de flow van de statussen van de verschillende objecten van het gebouwen- en adressenregister?  </summary>

Zie https://basisregisters.vlaanderen.be/documentatie/statusflowgrar voor een volledig overzicht per object per status. 

</details>

<details>

<summary>1.2 - Hoe kan ik de endpoints van de basisregisters uitproberen? </summary>

Een eenvoudige test van de REST-services kan door een URL samen te stellen in de adresbalk van uw browser. In uw browser krijgt u dan ook het resultaat van de aangeroepen service. 
- Algemene uitleg over de endpoints kan [hier](https://basisregisters.vlaanderen.be/producten/grar#readendpointsgrar) gevonden worden.
- Documentatie over de URL's en bijhorende parmameters kan [hier](https://docs.basisregisters.vlaanderen.be/docs/api-documentation.html#tag/api-documentation.html) gevonden worden.

</details>


<details>

<summary>1.3 - Elk object heeft een identificator (attribuut 'id') in de vorm van webadres. Wat is dit?</summary>

De **Vlaamse URI-standaard** schrijft voor dat naar Vlaamse ‘resources’ (zoals een object in het Gebouwenregister) kan verwezen worden met een [Uniform Resource Identifier](https://www.vlaanderen.be/digitaal-vlaanderen/onze-oplossingen/gebouwen-en-adressenregister/verklarende-woordenlijst-adressen-en-gebouwenregister) (URI). Deze data-URI is door zijn opbouw uniek binnen het World Wide Web en kan dus als stabiele identificator in eender welk systeem of databank gebruikt worden om ondubbelzinnig naar dat ene object te verwijzen. Daarnaast laten data-URI’s toe de resources als ‘linked data’ aan te bieden (cfr. CRAB-LOD).

Op dit moment zijn enkel een aantal data-URI’s voor adressen resolvable, dit wil zeggen, linken enkel deze URI’s door naar een webdocument (voorstelling van het adres op het web). Op termijn moet er achter deze link data voor elk object beschikbaar zijn. 

</details>

<details>

<summary>1.4 - Hoe kan ik de WMS gebruiken?</summary>

De WMS laat toe adressen, gebouwen en gebouweenheden per status en wegsegmenten per soort **op kaart te visualiseren** en objecten aan te klikken voor meer informatie. Deze kaartlagen kunnen ingeladen worden in GIS- of andere software. Een lijst van GIS-software vindt u [hier](https://en.wikipedia.org/wiki/Comparison_of_geographic_information_systems_software). We kunnen zelf QGIS (open source, gratis) aanbevelen.

Het is belangrijk in de GIS-software als coördinatensysteem voor het project **EPSG:31370** (Belgian Lambert 72) te kiezen en **PNG** als beeldformaat vooraleer lagen toe te voegen. De adressen worden zichtbaar vanaf schaal 1:2000 en hoger, gebouwen en gebouweenheden worden zichtbaar vanaf schaal 1:8000 of hoger en wegen worden zichtbaar afhankelijk van soort weg. De maximumschaal is 1:28000. 

Via de ‘identify’-functie kunt u de details van een object op de kaart met een muisklik opvragen.

</details>

<details>

<summary>1.5 - Is het downloadbestand als dataproduct beschikbaar? </summary>
Het downloadbestand is bechikbaar als dataproduct. Meer informatie over dit downloadbestand kan u [hier](https://basisregisters.vlaanderen.be/producten/grar#downloadbestandgrar) vinden.
 
</details>

<details>

<summary>1.6 - Hoe kan ik het downloadbestand gebruiken?</summary>

Het downloadbestand kan ingeladen en gevisualiseerd worden met GIS-software. Een lijst van GIS-software vindt u [hier](https://en.wikipedia.org/wiki/Comparison_of_geographic_information_systems_software). We kunnen zelf QGIS (open source, gratis) aanbevelen.
Meer informatie over dit downloadbestand kan u [hier](https://basisregisters.vlaanderen.be/producten/grar#downloadbestandgrar) vinden. 

</details>

<details>

<summary>1.7 - Moet ik nu al overschakelen naar de v2 endpoints van het gebouwen- en adressenregister? </summary>

Dit wordt sterk aangeraden. Vanaf ten laatste 1 november 2023 zullen de v1 endpoints niet meer up-to-date zijn als gevolg van de migratie van CRAB naar het Gebouwen- en Adressenregister. Om ervoor te zorgen dat u de meest recente gegevens blijft ontvangen, is het dus belangrijk om vóór deze datum over te stappen naar de nieuwe v2 endpoints. We begrijpen dat het migratieproces enige tijd kan vergen. Daarom hebben we besloten om de v1 endpoints **tot 1 maart 2024** beschikbaar te houden, zodat u voldoende tijd heeft om over te stappen naar de nieuwe v2 endpoints.
</details>

<details>

<summary>1.8 - Waar vind ik informatie over GRB-meldingen?</summary>

Op de pagina [Bijhouding & (fout)melding van het GRB](https://www.vlaanderen.be/digitaal-vlaanderen/onze-oplossingen/basiskaart-vlaanderen-grb/veelgestelde-vragen/bijhouding-foutmelding-van-het-grb) wordt meer uitleg gegeven over de meldingen specifiek voor het GRB. 

</details>


## Vragen adressenregister {#vragenadressenregister}

<details>

<summary>2.1 - Ik heb een CRAB huisnummer- of CRAB subadresId, wat is het gebouwen- en adressenregister objectId?</summary>

U kan op 2 manieren achterhalen wat het adressen objectId is van een CRAB huisnummer of een CRAB subadres.
- Via de read endpoints
  -   Voor CRAB huisnummers gebruikt u volgende readAPI: https://docs.basisregisters.vlaanderen.be/docs/api-documentation.html#operation/ListCrabHouseNumbers.
  -   Voor CRAB subadressen gebruikt u volgende readAPI: https://docs.basisregisters.vlaanderen.be/docs/api-documentation.html#operation/ListCrabSubaddresses.
- Via het downloadbestand
  - In het downloadbestand van het gebouwen- en adressenregister zitten er 2 dbf's files met daarin een overzicht van het CRAB huisnummer- en CRAB subadresId met hun overeenkomstige gebouwen- en adressenregister objectId.

</details>

<details>

<summary>2.2 - Ik heb een terreinObjectId of identificatorTerreinObject, hoe weet ik welke gebouwen- en adressenregister objectId dit is?</summary>

Via het read endpoint van CRAB gebouwen kan u achterhalen wat het gebouwen- en adressenregister objectId is. U geeft in de URL het terreinObjectId of identificatorTerreinObject mee en u krijgt een overzicht 
Zie https://docs.basisregisters.vlaanderen.be/docs/api-documentation.html#operation/ListCrabBuildings.

</details>

<details>

<summary>2.3 - Wat is het verschil tussen adresmatch endpoint v1 en adresmatch endpoint v2? </summary>

#### Wat is hetzelfde gebleven tov adresmatch v1?
- De logica achter de fuzzy matching.
- De responses die als resultaat worden teruggestuurd.

#### Wat is er uit adresmatch v2 verwijderd dat in adresmatch v1 zat?
- De query parameter ‘kadStraatcode’.
- De query parameter ‘rrStraatcode’.
- De query parameter ‘index’.
- Het response veld ‘adresseerbareObjecten’. Er werd hiervoor een alternatief voorzien. Dit kan u vinden onder toevoegingen. 

#### Wat is het verschil tussen adresmatch v2 en adresmatch v1?
- Het content-type van v2 is ‘application/ld+json’. Van v1 was dit default ‘application+json’, maar ‘application/xml’ was ook mogelijk.
- De geometrievelden zijn gewijzigd. De coördinaten van het object staan vanaf nu in het gml-formaat en alle velden die met geometrie te maken hebben zijn samengevoegd onder 1 veld.

#### Wat is er in adresmatch v2 toegevoegd dat niet in adresmatch v1 zit?
- Het veld ‘links’. In dit veld zit een lijst van gerelateerde resources om te achterhalen wat de gelinkte objecten zijn aan het adres. Momenteel worden er 2 URL’s getoond. 
  - URL 1: URL die alle gebouweenheden gaat tonen die gekoppeld zijn aan dit adres objectId.
  - URL 2: URL die alle percelen gaat tonen die gekoppeld zijn aan dit adres obejctId.
  - Op termijn zal er een nieuwe API zijn waarin de adreskoppelingen per adres zullen getoond worden.
- Het veld @context. Dit veld bevat de linked-data context van het endpoint. Dit is een URI naar de JSON-LD file.
- Het veld @type. Dit veld bevat het linked-data type van het endpoint. 
</details>


<details>

<summary>2.4 - Wat is de update frequentie van de WMS'en van het gebouwen- en adressenregister?  </summary>
De update frequentie van de geolocation service bij wijzigingen in het gebouwen- en adressenregister zullen pas de dag nadien zichtbaar zijn in de geolocation service. 

</details>

<details>

<summary>2.5 - Wat is de update frequentie van de geolocation service?  </summary>
De update frequentie van de WMS'en bij wijzigingen in het gebouwen- en adressenregister zijn near real time. Wat houdt dit in? Dit wit zeggen dat als bijvoorbeeld een adres wordt aangepast, de aanpassing van het adres zo goed als direct erna ook in de WMS van het gebouwen- en adressenregister zichtbaar zal zijn. 

</details>

<details>

<summary>2.6 - Is de puntgeometrie van een gebouweenheid dezelfde als deze van het adres?</summary>
Het attribuut ‘geometrie’ van een gebouweenheid is de positie van de gebouweenheid binnen de gebouwcontour. Deze geometrie kan niet buiten het gebouw liggen.  Staat de ‘positieGeometrieMethode’ op ‘afgeleidVanObject’ dan werd deze positie afgeleid van het gebouw waarbinnen de gebouweenheid ligt en betreft het de centroïde van het gebouw. - Staat de ‘positieGeometrieMethode’ op ‘aangeduidDoorBeheerder’ dan werd de positie manueel geplaatst door een decentraal beheerder. Het is dus mogelijk dat de gebouweenheid op een andere positie ligt dan het adres. 

</details>

<details>

<summary>2.7 - Welke objecten kunnen een adres dragen? </summary>

Er worden vier adresseerbare objecten onderscheiden:
- gebouweenheid
- perceel
- standplaats
- ligplaats

Stand- en ligplaatsen zullen later als object (‘resource’) worden toegevoegd. Gebouwen dragen enkel adressen via de daarbinnen gelegen gebouweenheden (fijnmazigere adressering).
</details>


<details>

<summary>2.8 - Hoe kan ik gebouwen terugvinden o.b.h. hun adres? </summary>

**Adressen worden in het gebouwen- en adressenregister niet meer rechtstreeks aan het gebouw gekoppeld, maar aan gebouweenheden binnen dat gebouw.**

De te volgend aanpak - met de services die vandaag beschikbaar zijn- is daarom:
- Stap 1: Bepaal de objectidentificator van het adres in kwestie (vb. URL: http://basisregisters.vlaanderen.be/api/v2/adressen?gemeentenaam=Denderleeuw&straatnaam=Nieuwstraat&huisnummer=2).
- Stap 2: Filter de gebouweenheden o.b.v. dit adres (vb. URL: http://basisregisters.vlaanderen.be/api/v2/gebouweenheden?adresobjectid=278669).
- Stap 3: Bepaal in welk gebouw(en) de teruggegeven gebouweenheden liggen.
</details>


<details>

<summary>2.9 - Welke adresposities zijn mogelijk binnen het gebouwen- en adressenregister? </summary>
De adresposities die mogelijk zijn binnen het gebouwen- en adressenregister zijn: gemeente, straat, perceel, lot, standplaats, ligplaats, gebouw, gebouweenheid, ingang en wegsegment. 
</details>


<details>

<summary>2.10 - Hoe kan ik adressuggesties (autocomplete) in mijn toepassing implementeren?  </summary>

- Stap 1: Maak gebruik van de **geolocation-API** (documentatie: https://loc.geopunt.be/) om suggesties te verkrijgen voor vrije tekstinvoer: vb: https://loc.geopunt.be/v4/suggestion?q=Koningin Mar.
- Stap 2: Teruggegeven straatnamen volgen het patroon: **<straatnaam>, <gemeentenaam>** vb: https://loc.geopunt.be/v4/suggestion?q=Graaf van Hoornestraat 5.
- Stap 3: Teruggegeven adressen volgen het patroon: **<straatnaam> <huisnummer>, <postcode> <gemeentenaam>** (merk op: er worden geen adressen met busnummer gesuggereerd).
- Stap 4: Indien u de unieke adresidentificator van de gesuggereerde adressen wil kennen, ‘parst’ u de adrescomponenten uit bovenstaand antwoord en plakt u deze in volgende request: vb: https://basisregisters.vlaanderen.be/api/v2/adressen?gemeentenaam=Nevele&straatnaam=Graaf van Hoornestraat&huisnummer=5
- Stap 5: Vervolgens leest u het id-veld uit.
</details>


<details>

<summary>2.11 - Hoe kan ik keuzelijsten voor adresformulieren creëren?</summary>

![image](https://github.com/Informatievlaanderen/base-registries-content/assets/49196256/88364e4e-fcae-4a90-9d1a-ca711ea75174)

U kan op basis van de verschillende read endpoints (https://basisregisters.vlaanderen.be/producten/grar#readendpointsgrar) een lijst tonen met gegevens in.
- Stap 1: Vraag een lijst met gemeenten op​.
- Stap 2: Vraag een lijst met postinfo over postcodes op binnen de gekozen gemeente.​
- Stap 3: Vraag een lijst met straatnamen op binnen de gekozen gemeente​.
- Stap 4: Vraag een lijst met adressen op binnen de gekozen gemeente & straatnaam.​
- Stap 5: Vraag een adres op.

</details>


<details>

<summary>2.12 - Wat is de betekenis van het veld 'homoniemtoevoeging'?</summary>

Een straatnaam moet uniek zijn binnen een gemeente. Districten zijn in geen enkel adresmodel (Adressenregister, OSLO², BeSt-Add) voorzien. Echter in bepaalde gemeenten zijn er nog dezelfde straatnamen in verschillende districten. De homoniemtoevoeging wordt gebruikt om aan te duiden in welk district de straatnaam ligt. Een straatnaam is met de bijhorende homoniemtoevoeging uniek binnen een gemeente. 

Voorbeeld: 
- Straatnaam = Krijgsbaan, homoniemtoevoeging = HO, waarbij ‘HO’ staat voor het district ‘Hoboken’.
- Straatnaam = Krijgsbaan, homoniemtoevoeging = DE, waarbij ‘DE’ staat voor het district ‘Deurne’. 

**Nieuwe homoniemtoevoegingen zijn niet toegestaan.** Het is wel mogelijk om bestaande homoniemtoevoegingen te wijzigen of te verwijderen. Bij gemeentelijke fusies moeten de homoniemen opgelost zijn op de datum dat de fusie ingaat.
</details>

## Vragen gebouwenregister {#vragengebouwenenregister}

<details>

<summary>3.1 - Wat is de definitie van een gebouweenheid?</summary>

Een gebouweenheid is de kleinste eenheid binnen een gebouw die geschikt is voor woon-, bedrijfsmatige, of recreatieve doeleinden en die ontsloten wordt via een eigen afsluitbare toegang vanaf de openbare weg, een erf of een gedeelde circulatieruimte. Een gebouweenheid is in functioneel opzicht zelfstandig.

</details>

<details>

<summary>3.2 - Hoe worden gebouwen afgebakend?</summary>

Voor afbakening gebouwen worden deze uiterlijke kenmerken in acht genomen:
- Zijn er meerdere huisnummers toegekend?
- Loopt er een perceelsgrens door het gebouw?
- Zijn er meerdere ingangen?
- Is er een verticale as door het gebouw?
Als 3 van deze 4 criteria positief zijn, dan wordt een gebouw meestal gesplitst.

Indien men beschikt over bouwplannen, dan kunnen deze meer inzicht verschaffen over de opdeling. Als uit deze plannen blijkt dat interne circulatie mogelijk is dan kan het gebouw als één gebouw afgebakend worden.

Een gedetailleerde toelichting hierover vind je [hier](https://assets.vlaanderen.be/image/upload/v1722241326/GRB-procedure_Afbakening_Gebouw_1.1.0-3_htj3kh.pdf)).
</details>

<details>

<summary>3.3 - Hoe wordt een gebouweenheid afgebakend?</summary>

Voor afbakening van een gebouweenheid wordt deze beslissingsboom gehanteerd:
![gebouweenheid_afbakening_v0 9](https://github.com/Informatievlaanderen/base-registries-content/assets/99253145/6518e337-0dc0-44b1-b47d-95beb468d417)

Momenteel zijn er werkgroepen ingepland om de afbakening van een gebouweenheid te verfijnen en definities te verduidelijken.

</details>

<details>

<summary>3.4 - Heeft ieder gebouw één gebouweenheid?  </summary>

Nee, dit is niet het geval. Het gebouw kan 0, 1 of meerdere gebouweenheden hebben. De decentrale beheerder zal gebouweenheden aanmaken in het gebouwen- en adressenregister. Deze hebben automatisch de functie ‘nietGekend’. Een gemeenschappelijk deel zal niet door een decentrale beheerder kunnen aangemaakt worden, want deze gebouweenheid wordt automatisch aangemaakt van zodra er 2 gebouweenheden aan het gebouw zijn gekoppeld. 

</details>

<details>

<summary>3.5 - Wat is de relatie tussen een gebouweenheid en adres?  </summary>
In gebouwen met exact één gebouweenheid krijgt de gebouweenheid een huisnummer. Als er voor één gebouw meerdere gebouweenheden bestaan, dan moeten de gemeenten aan elk van deze gebouweenheden een busnummer toekennen terwijl aan de gemeenschappelijke delen geen busnummer mag worden toegekend. Het is niet verplicht om aan een gemeenschappelijk deel een huisnummer toe te kennen. 

Het is mogelijk om uitzonderlijk meerdere adressen aan een gebouweenheid te koppelen onder de principes van maatschappelijk belang zoals vermeld in Bestadd (Artikel 10§4).
Een gemeenschappelijk deel kan ook verschillende adressen toegekend krijgen (bv. één appartementsgebouw met verschillende huisnummers)

</details>

<details>

<summary>3.6 - Wat is de betekenis van gebouweenheden met de functie 'gemeenschappelijk deel'? </summary>

In gebouwen waarin minstens twee functioneel zelfstandige gebouweenheden voorkomen (bv. gebouw met winkel op gelijkvloers en wooneenheid op eerste verdieping) worden de ruimten en structuren die door de eenheden in kwestie gedeeld worden voorgesteld door een extra gebouweenheid met functie ‘gemeenschappelijk deel’. Merk op dat slechts één gemeenschappelijk deel per gebouw wordt aangemaakt. Een flatgebouw met meerdere trappenhallen, liftkokers en een gedeelde ondergrondse garage krijgt dus één gemeenschappelijk deel (niet één per trappenhal/liftkoker/garage). Het gemeenschappelijk deel is tevens de drager van het huisnummeradres daar waar dit huisnummer uitsluitend naar (de gemeenschappelijke ruimten en structuren van) het gebouw verwijst. Er kan ook een gemeenschappelijk deel zijn zonder bijhorend adres.

</details>


<details>

<summary>3.7 - Hoe weet ik welk perceel aan het gebouw gekoppeld is?</summary>

Via het read endpoint detail gebouw v2 ([Documentatie](https://docs.basisregisters.vlaanderen.be/docs/api-documentation.html#operation/GetBuildingV2)) kunnen de eventuele gekoppelde percelen opgevraagd worden of via het read endpoint lijst gebouw v2 ([Documentatie](https://docs.basisregisters.vlaanderen.be/docs/api-documentation.html#operation/ListBuildingsV2)) waarbij de filter CaPaKey wordt meegegeven. 
Een perceel wordt als onderliggend aan een gebouw beschouwd indien het voldoet aan volgende voorwaarde (formule voor de berekening van de ‘verbeterde topologische relatie’): oppervlak overlap gebouw - perceel / oppervlak gebouw > 0.8 / # percelen waarmee het gebouw overlapt.

</details>

<details>

<summary>3.8 - Waar vind ik het onderscheid en de relatie tussen hoofd- en bijgebouwen?</summary>

De relatie tussen hoofd- en bijgebouwen is niet opgenomen in het gebouwenregister. 
Hoofd-en bijgebouwen is een concept binnen GRB-Basiskaart (https://overheid.vlaanderen.be/help/grb/objectcatalogus/gebouw-aan-de-grond-gbg) en is niet gekend in het gebouwenregister.

</details>


