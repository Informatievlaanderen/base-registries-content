## Overzicht pagina
* [Decentraal beheer](#decentraalbeheer)
* [Betekenis van de edit events en velden in de feed](#editeventsfeed)
* [Welke huisnummers & busnummers worden aanvaard voor een nieuw adres?](#regex)
* [Unieke straatnaam, homoniemtoevoeging, huisnummer of busnummer, hoe uniek is dit? ](#uniek)
* [Welke combinaties zijn mogelijk bij adrespositie?](#adrespositie)
* [Functie van een gebouweenheid: nietGekend of gemeenschappelijkDeel](#functiegebouweenheid)
* [Wat is het verschil tussen een correctie en een wijziging?](#verschilcorrectiewijziging)
* [Kan een straatnaam worden gecorrigeerd naar een andere straatnaam?](#correctiestraatnaam)
* [Hoe adres (de)regularisatie wijzigen of corrigeren?](#deregularisatie)
* [Werking edit functie ‘Heradresseren van adressen binnen éénzelfde straatnaam of naar een andere straatnaam’](#heradresseren)
* [Validaties edit endpoint](#validatieseditendpoints)
* [Flow statussen](#flowstatussen)
* [Ticketing service](#ticketingservice)

## Decentraal beheer {#decentraalbeheer}

De edit endpoints maken decentraal beheer mogelijk in het gebouwen- en adressenregister. Deze endpoints worden door de dienstenleveranciers geïmplementeerd in hun software. Zo kunnen vb. straatnamen, adressen, gebouwen, gebouweenheden en percelen toegevoegd, verwijderd of aangepast worden. 

Niet alle edit endpoints mogen door iedereen uitgevoerd worden, daarom werden er een aantal rollen opgesteld. Elke rol heeft zijn eigen specifieke eigenschappen.  

* Decentrale bijwerker: De decentrale bijwerker staat in voor het beheer van adressen, ingeschetste gebouwen en enkele correcties. vb. lokale besturen. 
* Interne bijwerker: De interne bijwerker staat in voor de verwijdering en correcties van straatnamen, adressen, ingeschetste gebouwen en gebouweenheden. De interne bijwerker kan ook uitvoeren wat een decentrale bijwerker kan. vb. operatoren van Digitaal Vlaanderen.

Hieronder kan per register een lijst gevonden worden van welke beheeracties er allemaal mogelijk zijn en welke rol welke beheeractie mag uitvoeren.

### Straatnamen
* Stel een straatnaam voor. (Decentrale bijwerker)
* Keur een straatnaam goed. (Decentrale bijwerker)
* Keur een straatnaam af. (Decentrale bijwerker)
* Hef een straatnaam op. (Interne bijwerker)
* Verwijder een straatnaam. (Interne bijwerker)
* Corrigeer de straatnaam van een straatnaam. (Decentrale bijwerker)
* Corrigeer de homoniemtoevoeging van een straatnaam. (Interne bijwerker)
* Corrigeer de goedkeuring van een straatnaam. (Interne bijwerker)
* Corrigeer de afkeuring van een straatnaam. (Interne bijwerker)
* Corrigeer de opheffing van een straatnaam. (Interne bijwerker)
* Hernoem de straatnaam van een straatnaam. (Interne bijwerker)

### Adressen
* Stel een adres voor. (Decentrale bijwerker)
* Keur een adres goed. (Decentrale bijwerker)
* Keur een adres af. (Decentrale bijwerker)
* Hef een adres op. (Decentrale bijwerker)
* Verwijder een adres. (Interne bijwerker)
* Regulariseer een adres. (Decentrale bijwerker)
* Deregulariseer een adres. (Decentrale bijwerker)
* Heradresseren van adressen binnen éénzelfde straatnaam of naar een andere straatnaam. (Decentrale bijwerker)
* Corrigeer de adrespositie van een adres. (Decentrale bijwerker)
* Corrigeer de postcode van een adres. (Decentrale bijwerker)
* Corrigeer het huisnummer van een adres. (Decentrale bijwerker)
* Corrigeer het busnummer van een adres. (Decentrale bijwerker)
* Corrigeer de busnummers van adressen. (Decentrale bijwerker)
* Corrigeer de goedkeuring van een adres. (Decentrale bijwerker)
* Corrigeer de afkeuring van een adres. (Decentrale bijwerker)
* Corrigeer de opheffing van een adres. (Decentrale bijwerker)
* Wijzig de postcode van een adres. (Interne bijwerker)

### Gebouwen
De edit endpoints van gebouwen kunnen alleen toegepast worden op gebouwen met geometrieMethode- = ingeschetst. 
* Plan een gebouw in. (Decentrale bijwerker)
* Plaats een gebouw in aanbouw. (Decentrale bijwerker)
* Realiseer een gebouw. (Decentrale bijwerker)
* Realiseer een gebouw niet. (Decentrale bijwerker, Omgeving)
* Verwijder een geschetst gebouw. (Interne bijwerker)
* Corrigeer de inAanbouw plaatsing van een gebouw. (Decentrale bijwerker)
* Corrigeer de realisering van een gebouw. (Decentrale bijwerker)
* Corrigeer de nietRealisering van een gebouw. (Decentrale bijwerker)
* Wijzig de geometrie van een geschetst gebouw. (Decentrale bijkwerker)

### Gebouweenheid
* Plan een gebouweenheid in. (Decentrale bijwerker)
* Realiseer een gebouweenheid. (Decentrale bijwerker)
* Realiseer een gebouweenheid niet. (Decentrale bijwerker)
* Hef een gebouweenheid op. (Decentrale bijwerker)
* Verwijder een gebouweenheid. (Interne bijwerker)
* Regulariseer een gebouweenheid. (Decentrale bijwerker)
* Deregulariseer een gebouweenheid. (Decentrale bijwerker)
* Corrigeer de realisering van een gebouweenheid. (Decentrale bijwerker)
* Corrigeer de niet realisering van een gebouweenheid. (Decentrale bijwerker)
* Corrigeer de opheffing van een gebouweenheid. (Decentrale bijwerker)
* Corrigeer de positie van een gebouweenheid. (Decentrale bijwerker)
* Corrigeer de regularisatie van een gebouweenheid. (Decentrale bijwerker)
* Corrigeer de deregularisatie van een gebouweenheid. (Decentrale bijwerker)
* Koppel een adres aan een gebouweenheid. (Decentrale bijwerker)
* Ontkoppel een adres van een gebouweenheid. (Decentrale bijwerker)

### Percelen
* Koppel een adres aan een perceel. (Decentrale bijwerker)
* Ontkoppel een adres van een perceel. (Decentrale bijwerker)

## Betekenis van de edit events en velden in de feed {#editeventsfeed}

Een overzicht van alle mogelijke edit events en de betekenis van de attributen onder het blokje <event> vindt u op deze pagina: https://api.basisregisters.vlaanderen.be/v2/info/events?tags=edit.

## Welke huisnummers & busnummers worden aanvaard voor een nieuw adres? {#regex}

Als er een nieuw voorgesteld adres wordt ingevoerd dan moet het huisnummer en eventueel het busnummer aan bepaalde voorwaarden voldoen.

De regex die van toepassing is op het huisnummer is ^[1-9] ([0-9]{0,8}([A-H]|[K-N]|[P]|[R-T]|[V-Z]){0,1}|[0-9]{0,9})$. Dit wilt zeggen dat huisnummers 45, 2C of 7563M zullen aanvaard worden, maar huisnummers 045, 2I, 5BIS of 4a niet aanvaard zullen worden.

De regex die van toepassing is op het busnummer is ^(?!^[./]|.* [./]$)(?!.* [./]{2,})[a-zA-Z0-9./]{1,10}$. Bovenop deze regex worden de woorden bus, Bus of BUS niet aanvaard en is het ook niet mogelijk om busnummer 0 mee te geven. Dit wilt zeggen dat busnummers 1, 001, 5C,1.1 aanvaard zullen worden, maar busnummers 0, Bus 1, 1-A, 12..1 niet aanvaard zullen worden.
 
## Unieke straatnaam, homoniemtoevoeging, huisnummer of busnummer, hoe uniek is dit? {#uniek}
 
Als er een straatnaam, homoniemtoevoeging, huisnummer of busnummer wordt ingevoerd dan wordt er achterliggend gekeken of deze al bestaan in een bepaalde gemeente of straatnaam. Dit wordt gedaan zodat er geen 2 dezelfde straatnamen, homoniemtoevoegingen, huisnummers of busnummers met status 'voorgesteld' of 'inGebruik' aanwezig zijn binnen deze gemeente of straatnaam. Ook werd ervoor gezorgd dat deze vergelijking niet hoofdlettergevoelig is. Het is namelijk niet mogelijk om een straatnaam met hoofdletters mee te geven en wat later diezelfde straatnaam zonder hoofdletters. vb. 'Straatnaam' en 'straatnaam' zal niet mogelijk zijn.

## Welke combinaties zijn mogelijk bij adrespositie? {#adrespositie}

In de edit endpoints ‘Stel een adres voor’ en ‘Corrigeer de adrespositie van een adres’ zijn de parameters positieGeometrieMethode, positieSpecificatie en positie verplicht. 

De parameter positieGeometrieMethode kan de waarde aangeduidDoorBeheerder of afgeleidVanObjrect bevatten. Wanneer positieGeometrieMethode aangeduidDoorBeheerder wordt gekozen dan zijn volgende waarden mogelijk bij de parameter positieSpecificatie:
* Lot
* Perceel
* Ingang
* Standplaats
* Ligplaats
* Gebouweenheid

Wanneer positieGeometrieMethode afgeleidVanObject wordt gekozen dan zijn volgende waarden mogelijk bij de parameter positieSpecificatie:
* Perceel
* Gebouweenheid

## Functie van een gebouweenheid: nietGekend of gemeenschappelijkDeel {#functiegebouweenheid}

Een gebouweenheid kan 2 functies hebben: nietGekend of gemeenschappelijkDeel. In de toekomst zal deze lijst met mogelijke waarden uitgebreid worden.

Wanneer er een gebouweenheid wordt ingepland, is het enkel mogelijk om een ‘nietGekend’ als functie mee te geven. De functie ‘gemeenschappelijkDeel’ wordt automatisch toegekend van zodra er 2 ‘nietGekend’ ‘gepland/gerealiseerde’ gebouweenheden gekoppeld zijn aan het gebouw.

## Wat is het verschil tussen een correctie en een wijziging? {#verschilcorrectiewijziging}

Er wordt een onderscheid gemaakt tussen correcties en wijzigingen. In het eerste geval gaat het om een rechtzetting van een fout (vb. ‘Van Eikstraat’ moet zijn ‘Van Eyckstraat’), in het tweede geval gaat het om een verandering in administratieve toestand (vb. gebouw veranderd van status ‘inAanbouw’ naar ‘inGebruik’).

Voorbeeld: Het wijzigen of corrigeren van de postcode van een adres.

Hiervoor zijn 2 aparte API’s gemaakt. De API ‘Corrigeer de postcode van een adres’ mag door elke decentrale beheerder uitgevoerd worden. Dit wordt uitgevoerd als de verkeerde postinfoID van een gemeente aan het adres is gekoppeld. Deze correctie kan alleen maar naar postinfoId’s worden gezet gekoppeld aan deze gemeente. De API ‘Wijzig de postcode van een adres’ is voor interne bijwerkers en wordt bijvooorbeeld op vraag van Bpost uitgevoerd. Bpost wilt dat postbodes een zo optimaal mogelijke route afleggen om deze reden kan het zijn dat adressen van bepaalde gemeenten een andere postinfoId krijgen dan deze die in de gemeente liggen. Deze API laat dit toe, vandaar dat dit niet door iedereen mogelijk is om uit te voeren. 

## Kan een straatnaam worden gecorrigeerd naar een andere straatnaam? {#correctiestraatnaam}

Er zijn 2 mogelijkheden. In het edit endpoint 'Corrigeer de straatnaam van een straatnaam' worden enkel kleine correcties toegestaan. Dit zijn kleine correcties gebaseerd op het Levenshtein distance algoritme.
Hieronder kunnen voorbeelden gevonden worden van dit algoritme.

Hieronder kunnen voorbeelden gevonden worden van dit algoritme.
- Niewstraat → Nieuwstraat: Deze correctie wordt toegelaten. 
- Sint-Niklaasstraat → St-Niklaasstraat: Deze correctie wordt toegelaten. 
- Jean-Philppestraat → JeanPhilippestraat: Deze correctie wordt toegelaten. 
- Molenstraat → Kerkstraat: Deze correctie wordt niet toegelaten.
 
In het edit endpoint ‘Hernoem de straatnaam van een straatnaam’ is het mogelijk om de straatnaam volledig te hernoemen. Deze actie is een complexe beheersactie, omdat we verschillende acties gaan combineren. Wanneer deze actie wordt toegepast dan gaan alle ‘actieve’ adressen met hun bijhorende eigenschappen mee worden overgezet naar deze nieuwe straatnaam (status, adrespositie, koppeling gebouweenheid, koppeling perceel).
 
Let op: Bij het hernoemen van een straatnaam worden nieuwe adres objectId’s aangemaakt & de oude worden gehistoreerd. Ook moet de straatnaam waarnaar de oude straatnaam moet hernoemd worden, al bestaan in het gebouwen- en adressenregister.


## Hoe adres (de)regularisatie wijzigen of corrigeren? {#deregularisatie}

Wanneer er een (de)regularisatie is gebeurd van een adres, maar dit moet gewijzigd worden of was verkeerd ingevoerd dan kan u gebruik maken van de edit endpoints ‘(De)Regulariseer een adres’.  

## Werking edit functie ‘Heradresseren van adressen binnen éénzelfde straatnaam of naar een andere straatnaam’ {#heradresseren}

Heradresseren van adressen binnen éénzelfde straatnaam of naar een andere straatnaam is een complexe beheersactie, dit wilt zeggen dat het verschillende acties gaat combineren. Deze edit API wordt het best aangeroepen wanneer er een hernummering van adressen moet gebeuren binnen éénzelfde of een andere straatnaam. Dit houdt in dat aan een adrespositie een ander adres toegekend wordt. 

### Wat wordt er van het oude adres overgenomen? 
De geometrie, positieGeometrieMethode, positieSpecificatie, adresStatus en de gekoppelde gebouweenheden en percelen. 

### Tip
*	Als de heradressering van adressen naar een andere straatnaam wordt gedaan dan moet de nieuwe straatnaam al bestaan. 
*	Deze actie wordt best niet gecombineerd binnen de reguliere wijzigingsacties van een adres. Aangezien we spreken over een complexe beheersactie zien we dit voor een gebruiker ook als een aparte actie.

### Voorbeeld

![image](https://github.com/Informatievlaanderen/base-registries-content/assets/49196256/fb699032-b7ff-45be-8bb7-7ecf718d0974)

## Validaties edit endpoint {#validatieseditendpoints}
 
Zie https://vlaamseoverheid.atlassian.net/wiki/spaces/AGB/pages/7668138177/Gebruik+van+de+edit-API+s+GRAR.
 
## Flow statussen   {#flowstatussen}
 
Zie https://vlaamseoverheid.atlassian.net/wiki/spaces/AGB/pages/7668138177/Gebruik+van+de+edit-API+s+GRAR.
 
 
 ## Ticketing service {#ticketingservice}
 
 ### Flow status ticketing service 
 
 ![image](https://user-images.githubusercontent.com/49196256/229503216-612d1f51-d13a-4cd6-8c1e-25b0498f5400.png)
 
 ### Veld ‘metadata’
 
- Wanneer er een actie wordt uitgevoerd dan bestaat de inhoud van het veld metadata in het ticket uit de volgende velden :
  - action
  -	objectId
  -	registry
  -	aggregateId
  - Uitzondering: De edit API ‘Stel een straatnaam voor’, 'Stel een adres voor', 'Heradresseren van adressen binnen éénzelfde straatnaam of naar een andere straatnaam' en 'Plan een gebouweenheid in' hebben het veld ‘objectId’ niet.

- Betekenis velden:
  -	action: De naam van de uitgevoerde actie.
  - objectId: Het objectId van het meegegeven of nieuwe object.
  -	registry: In welk register deze actie zich bevindt.
  -	aggregateId:  In het domein gedreven ontwerp (DDD) betekent een "aggregaat" een groep van objecten die bij elkaar horen en samenwerken om een bepaalde taak uit te voeren. Dit aggregaat is een soort "pakketje" van objecten die samenwerken en als één geheel worden beheerd.
Het idee hierachter is dat het aggregaat zorgt voor consistentie en dat alle veranderingen die binnen het aggregaat plaatsvinden als één geheel worden opgeslagen of teruggedraaid. Dit zorgt voor een duidelijke grens voor de buitenwereld, waarbij alle communicatie met de objecten binnen het aggregaat plaatsvindt via één centraal punt.
Deze structuur helpt bij het organiseren van complexe bedrijfsprocessen en zorgt ervoor dat verschillende objecten binnen het systeem beter kunnen worden beheerd. Dit zorgt voor meer flexibiliteit en onderhoudbaarheid van de software, wat uiteindelijk kan leiden tot betere prestaties en efficiëntie.

### Veld ‘result’
 
- Wanneer het ticket als status ‘complete’ heeft dan bestaat het veld ‘result’ uit een json met de volgende waarden:
  -	Location: De URL naar het detail van het objectId.
  -	ETag: De nieuwe eTag die het objectId heeft meegekregen. 

- Wanneer het ticket als status ‘error’ heeft dan bestaat het veld ‘result’ uit een json met de volgende waarden:
  -	ErrorMessage: Uitgebreide errormelding waarom het ticket de status ‘error’ heeft.
  -	ErrorCode: Unieke errorCode. Dit kan gebruikt om eigen errormeldingen te gebruiken. De errormelding die in het ticket staat kan ook gebruikt worden. 
