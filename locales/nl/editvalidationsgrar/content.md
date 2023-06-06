Op deze pagina vindt u een overzicht van alle geldende validaties per edit API.

## Straatnamen

#### Stel een straatnaam voor 

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Straatnaam leeg of null meegegeven|Error 400 |StraatnaamNietLeegValidatie|Straatnaam in 'taal' kan niet leeg zijn.| 
|Meegegeven straatnaam > 60 tekens|Error 400 |StraatnaamMaxlengteValidatie|Maximum lengte van een straatnaam in 'taal' is 60 tekens. U heeft momenteel <aantaltekens> tekens.| 
|Niet Vlaamse gemeente meegegeven|Error 400 |StraatnaamVlaamsGewestValidatie|De gemeente 'gemeenteId' is geen Vlaamse gemeente.|
|Onbestaande gemeente meegegeven|Error 400 |StraatnaamGemeenteNietGekendValidatie|De gemeente 'gemeenteId' is niet gekend in het gemeenteregister. |
|Het veld gemeenteId niet meegegeven/het veld straatnamen niet meegegeven/onbestaande taal meegegeven|Error 400 |JsonInvalid| Json is not valid.|
|Straatnaam bestaat reeds in de gemeente|Ticketing error |StraatnaamBestaatReedsInGemeente|Straatnaam 'straatnaam' bestaat reeds in de gemeente.|
|De meegegeven taal is geen officiële of faciliteitentaal van de gemeente|Ticketing error  | StraatnaamTaalNietInOfficieleOfFaciliteitenTaal|'Straatnamen' kunnen enkel voorkomen in de officiële of faciliteitentaal van de gemeente.|
|Er ontbreekt een officiële- of faciliteitentaal|Ticketing error | StraatnaamOntbreektOfficieleOfFaciliteitenTaal|In 'Straatnamen' ontbreekt een officiële of faciliteitentaal. |
|Gehistoreerde Vlaamse gemeente meegegeven|Ticketing error |StraatnaamGemeenteVoorgesteldOfInGebruik|Deze actie is enkel toegestaan binnen gemeenten met       status 'voorgesteld' of 'inGebruik'.|
  
#### Keur een straatnaam goed
|<div width="50%">Validatie</div>|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig straatnaamId meegegeven   |Error 400  |/ |De waarde 'straatnaamId' is ongeldig.  |
|Onbestaand straatnaamId meegegeven  |Error 404 |/  |/  |
|Status straatnaamId gehistoreerd/afgekeurd|Ticketing error|StraatnaamAfgekeurdOfGehistoreerd| Deze actie is enkel toegestaan op straatnamen met status 'voorgesteld' . |
|Verwijderd straatnaamId meegegeven |Ticketing error |VerwijderdeStraatnaam  |Verwijderde straatnaam.  |

#### Keur een straatnaam af 

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig straatnaamId meegegeven   |Error 400  |/ |De waarde 'straatnaamId' is ongeldig.  |
|Onbestaand straatnaamId meegegeven  |Error 404 |/  |/  |
|Status straatnaamId gehistoreerd/inGebruik|Ticketing error|StraatnaamInGebruikOfGehistoreerd| Deze actie is enkel toegestaan op straatnamen met status 'voorgesteld'. |
|Verwijderd straatnaamId meegegeven |Ticketing error |VerwijderdeStraatnaam  |Verwijderde straatnaam.  |
  
#### Hef een straatnaam op 

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig straatnaamId meegegeven   |Error 400  |/ |De waarde 'straatnaamId' is ongeldig.  |
|Onbestaand straatnaamId meegegeven  |Error 404 |/  |/  |
|Status straatnaamId voorgesteld/afgekeurd|Ticketing error|StraatnaamVoorgesteldOfAfgekeurd| Deze actie is enkel toegestaan op straatnamen met status 'inGebruik'. |
|Verwijderd straatnaamId meegegeven |Ticketing error |VerwijderdeStraatnaam  |Verwijderde straatnaam.  |
  
#### Corrigeer de goedkeuring van een straatnaam 

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig straatnaamId meegegeven   |Error 400  |/ |De waarde 'straatnaamId' is ongeldig.  |
|Onbestaand straatnaamId meegegeven  |Error 404 |/  |/  |
|Status straatnaamId gehistoreerd/inGebruik|Ticketing error|StraatnaamGehistoreerdAfgekeurd| Deze actie is enkel toegestaan op straatnamen met status 'inGebruik'. |
|Verwijderd straatnaamId meegegeven |Ticketing error |VerwijderdeStraatnaam  |Verwijderde straatnaam.  |
  
#### Corrigeer de afkeuring van een straatnaam 

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig straatnaamId meegegeven   |Error 400  |/ |De waarde 'straatnaamId' is ongeldig.  |
|Onbestaand straatnaamId meegegeven  |Error 404 |/  |/  |
|Status straatnaamId gehistoreerd/inGebruik|Ticketing error|StraatnaamGehistoreerdOfInGebruik| Deze actie is enkel toegestaan op straatnamen met status 'afgekeurd'. |
|Straatnaam bestaat in gemeente met status voorgesteld/inGebruik |Ticketing error |StraatnaamBestaatReedsInGemeente  | Straatnaam 'straatnaam' bestaat reeds in de gemeente. |
|Verwijderd straatnaamId meegegeven |Ticketing error |VerwijderdeStraatnaam  |Verwijderde straatnaam.  |
  
#### Corrigeer de opheffing van een straatnaam 

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig straatnaamId meegegeven   |Error 400  |/ |De waarde 'straatnaamId' is ongeldig.  |
|Onbestaand straatnaamId meegegeven  |Error 404 |/  |/  |
|Status straatnaamId voorgesteld/afgekeurd|Ticketing error|StraatnaamAfgekeurdOfVoorgesteld| Deze actie is enkel toegestaan op straatnamen met status 'gehistoreerd'. |
|Straatnaam bestaat in gemeente met status voorgesteld/inGebruik |Ticketing error |StraatnaamBestaatReedsInGemeente  | Straatnaam 'straatnaam' bestaat reeds in de gemeente. |
|Straatnaam in gemeente met status gehistoreerd |Ticketing error |StraatnaamGemeenteInGebruik  | Deze actie is enkel toegestaan binnen gemeenten met status 'inGebruik'. |
|Verwijderd straatnaamId meegegeven |Ticketing error |VerwijderdeStraatnaam  |Verwijderde straatnaam.  |
  
#### Verwijder een straatnaam

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig straatnaamId meegegeven   |Error 400  |/ |De waarde 'straatnaamId' is ongeldig.  |
|Onbestaand straatnaamId meegegeven  |Error 404 |/  |/  |
  
#### Corrigeer de straatnaam van een straatnaam 

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig straatnaamId meegegeven   |Error 400  |/ |De waarde 'straatnaamId' is ongeldig.  |
|Het veld straatnamen niet meegegeven/onbestaande taal meegegeven   |Error 400  |JsonInvalid |Json is not valid |
|Meegegeven straatnaam > 60 tekens |Error 400  |StraatnaamMaxlengteValidatie |De waarde 'straatnaamId' is ongeldig.  |
|Straatnaam leeg of null meegegeven   |Error 400  |StraatnaamNietLeegValidatie |De waarde 'straatnaamId' is ongeldig.  |
|Onbestaand straatnaamId meegegeven  |Error 404 |/  |/  |
|Status straatnaamId gehistoreerd/afgekeurd|Ticketing error|StraatnaamGehistoreerdOfAfgekeurd| Deze actie is enkel toegestaan op straatnamen met status 'voorgesteld' of 'inGebruik'. |
|Straatnaam bestaat in gemeente met status voorgesteld/inGebruik |Ticketing error |StraatnaamBestaatReedsInGemeente   | Straatnaam 'straatnaam' bestaat reeds in de gemeente. |
|De meegegeven taal is geen officiële of faciliteitentaal van de gemeente|Ticketing error | StraatnaamTaalNietInOfficieleOfFaciliteitenTaal| 'Straatnamen' kunnen enkel voorkomen in de officiële of faciliteitentaal van de gemeente.|
|Verwijderd straatnaamId meegegeven |Ticketing error |VerwijderdeStraatnaam  |Verwijderde straatnaam.  |
  
#### Corrigeer de homoniemtoevoeging van een straatnaam 

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig straatnaamId meegegeven   |Error 400  |/ |De waarde 'straatnaamId' is ongeldig.  |
|Het veld homoniemtoevoegingen niet meegegeven/onbestaande taal meegegeven   |Error 400  |JsonInvalid |Json is not valid |
|Meegegeven homoniemToevoeging > 20 tekens  |Error 400  |StraatnaamHomoniemToevoegingMaxlengteValidatie| Maximum lengte van een homoniemToevoeging in 'taal' is 20 tekens. U heeft momenteel <aantalTekens> tekens.  |
|Onbestaand straatnaamId meegegeven  |Error 404 |/  |/  |
|Status straatnaamId gehistoreerd/afgekeurd|Ticketing error|StraatnaamGehistoreerdOfAfgekeurd|   Deze actie is enkel toegestaan op straatnamen met status 'voorgesteld' of 'inGebruik'. |
|Homoniemtoevoeging bestaat reeds in deze gemeente voor dezelfde straatnaam |Ticketing error |StraatnaamHomoniemToevoegingBestaatReedsInGemeente  | Binnen deze gemeente bestaat er reeds een straatnaam met status 'voorgesteld' of 'inGebruik' met dezelfde straatnaam en homoniemToevoeging.   |
|Geen homoniemtoevoeging voor bepaalde taal aanwezig |Ticketing error |StraatnaamHomoniemToevoeging  | Er kan geen homoniemToevoeging worden toegevoegd voor taalcode 'taal'. |
|Verwijderd straatnaamId meegegeven |Ticketing error |VerwijderdeStraatnaam  |Verwijderde straatnaam.  |


## Adressen
  
#### Stel een adres voor

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Het veld postinfoId/straatnaamId/huisnummer/positieGeometrieMethode/positieSpecificatie/positie niet/leeg/onbestaande waarde meegegeven |Error 400| JsonInvalid |Json is not valid. |
|Huisnummer voldoet niet aan regex huisnummer |Error 400  |AdresOngeldigHuisnummerformaat |Ongeldig huisnummerformaat. |
|Busnummer voldoet niet aan regex busnummer |Error 400  |AdresOngeldigBusnummerformaat |Ongeldig busnummerformaat. |
|Onbestaand postinfoId meegegeven  |Error 400 |AdresPostinfoNietGekendValidatie |   De postinfo 'postinfoId' is niet gekend in het postinforegister. |
|Onbestaand straatnaamId meegegeven  |Error 400 |AdresStraatnaamNietGekendValidatie  |   De straatnaam 'straatnaamId' is niet gekend in het straatnaamregister.   |
|Combinatie positieGeometrieMethode & positieSpecificatie is niet correct  |Error 400  |AdresPositieSpecificatieValidatie |Ongeldige positieSpecificatie. |
|Het veld positie leeg meegegeven   |Error 400  |AdresPositieVerplicht |De positie is verplicht.   |
|Ongeldig waarde bij positie meegegeven   |Error 400  |AdresPositieformaatValidatie |De positie is geen geldige gml-puntgeometrie.   |
|Postcode ligt niet in de gemeente van het adres |Ticketing error |AdresPostinfoNietInGemeente  |De ingevoerde postcode wordt niet gebruikt binnen deze gemeente.  | 
|Wanneer het huisnummer/busnummer al bestaat|Ticketing error |AdresBestaandeHuisnummerBusnummerCombinatie  | Deze combinatie huisnummer-busnummer bestaat reeds voor de opgegeven straatnaam.   |  
|Adres met busnummer meegeven, maar geen adres met huisnummer aanwezig |Ticketing error |AdresActiefHuisNummerNietGekendValidatie | Er bestaat geen actief adres zonder busnummer voor straatnaam 'straatnaamId' en huisnummer 'huisnummer'.   | 
|Meegegeven straatnaam heeft status afgekeurd/gehistoreerd |Ticketing error |AdresStraatnaamGehistoreerdOfAfgekeurd  |De straatnaam is gehistoreerd of afgekeurd.   | 
|Meegegeven postinfoId is verschillend tov postinfoId van het adres met huisnummer |Ticketing error |AdresPostinfoNietHetzelfdeAlsHuisnummer  | De ingevoerde postcode komt niet overeen met de postcode van het huisnummer.   | 
 
#### Keur een adres goed

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig adresId meegegeven   |Error 400  |/ |De waarde 'adresId' is ongeldig.  |
|Onbestaand adresId meegegeven  |Error 404 |/  |/  |
|Status adresId afgekeurd/gehistoreerd|Ticketing error|AdresAfgekeurdOfGehistoreerd| Deze actie is enkel toegestaan op adressen met status 'voorgesteld'. |
|Adres in straatnaam met status afgekeurd/gehistoreerd|Ticketing error|AdresStraatnaamVoorgesteldOfInGebruik|   Deze actie is enkel toegestaan binnen straatnamen met  status 'voorgesteld' of 'inGebruik'. |
|Adres is een busnummer & mag niet voorlopen op status adres dat een huisnummer is|Ticketing error|AdresHuisnummerVoorgesteldGehistoreerdOfAfgekeurd| Deze actie is enkel toegestaan op adressen waarbij het huisnummer de status 'inGebruik' heeft. |
|Verwijderd adresId meegegeven |Ticketing error |VerwijderdAdres  |Verwijderd adres.  |

#### Keur een adres af

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig adresId meegegeven   |Error 400  |/ |De waarde 'adresId' is ongeldig.  |
|Onbestaand adresId meegegeven  |Error 404 |/  |/  |
|Status adresId inGebruik/gehistoreerd|Ticketing error|AdresGehistoreerdOfInGebruik| Deze actie is enkel toegestaan op adressen met status 'voorgesteld'. |
|Verwijderd adresId meegegeven |Ticketing error |VerwijderdAdres  |Verwijderd adres.  |

#### Hef een adres op

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig adresId meegegeven   |Error 400  |/ |De waarde 'adresId' is ongeldig.  |
|Onbestaand adresId meegegeven  |Error 404 |/  |/  |
|Status adresId voorgesteld/gehistoreerd|Ticketing error|AdresVoorgesteldOfAfgekeurd| Deze actie is enkel toegestaan op adressen met status 'inGebruik'. |
|Verwijderd adresId meegegeven |Ticketing error |VerwijderdAdres  |Verwijderd adres.  |  
  
#### Verwijder een adres

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig adresId meegegeven   |Error 400  |/ |De waarde 'adresId' is ongeldig.  |
|Onbestaand adresId meegegeven  |Error 404 |/  |/  |
  
#### Regulariseer een adres

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig adresId meegegeven   |Error 400  |/ |De waarde 'adresId' is ongeldig.  |
|Onbestaand adresId meegegeven  |Error 404 |/  |/  |
|Status adresId afgekeurd/gehistoreerd|Ticketing error|AdresGehistoreerdOfAfgekeurd| Deze actie is enkel toegestaan op adressen met status 'voorgesteld' of 'inGebruik'. |
|Verwijderd adresId meegegeven |Ticketing error |VerwijderdAdres  |Verwijderd adres.  |  
  
#### Deregulariseer een adres
  
|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig adresId meegegeven   |Error 400  |/ |De waarde 'adresId' is ongeldig.  |
|Onbestaand adresId meegegeven  |Error 404 |/  |/  |
|Status adresId afgekeurd/gehistoreerd|Ticketing error|AdresGehistoreerdOfAfgekeurd| Deze actie is enkel toegestaan op adressen met status 'voorgesteld' of 'inGebruik'. |
|Verwijderd adresId meegegeven |Ticketing error |VerwijderdAdres  |Verwijderd adres.  |
|Adres is een busnummer & mag niet voorlopen op status adres dat huisnummer is|Ticketing error |AdresHuisnummerVoorgesteldGehistoreerdOfAfgekeurd | Deze actie is enkel toegestaan op adressen waarbij het huisnummer de status ‘inGebruik’ heeft. |

#### Heradresseren van adressen binnen éénzelfde straatnaam of naar een andere straatnaam
 
|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Het veld doelStraatnaamId/herAdresseer/bronAdresId/doelHuisnummer niet of null meegegeven   |Error 400  |JsonInvalid |Json is not valid.  |
|Het veld doelStraatnaamId leeg of ongeldige waarde meegegeven   |Error 400  |AdresStraatnaamNietGekendValidatie | De straatnaam 'straatnaamId' is niet gekend in het straatnaamregister. |
|Het veld doelStraatnaamId leeg of ongeldige waarde meegegeven  |Error 400  |AdresIsOnbestaand |Onbestaand adres 'adresId'.  |
|2x hetzelfde adresId meegegeven in het veld bronAdresId  |Error 400  |BronAdresIdReedsInLijstHerAdresseer | Het bronAdresId zit meerdere keren in lijst van herAdresseer: <adresId>.  |
|AdresId zit in opheffenAdressen, maar niet in bronAdresId   |Error 400  |OpgehevenAdresNietInLijstHerAdresseer | Het op te heffen adres dient voor te komen in de lijst van herAdresseer. |
|2x hetzelfde huisnummer meegegeven in het veld doelHuisnummer  |Error 400  |DoelHuisnummerReedsInLijstHerAdresseer | Het doelHuisnummer zit meerdere keren in lijst van herAdresseer: <huisnummer>.  |
|Huisnummer voldoet niet aan regex huisnummer   |Error 400  |DoelHuisnummerOngeldigHuisnummerformaat |Ongeldig huisnummerformaat: <huisnummer>.  |
|Verwijderd doelStraatnaamId meegegeven |Ticketing error |VerwijderdeStraatnaam  |Verwijderde straatnaam.  |  
|Afgekeurd/gehistoreerd doelStraatnaamId meegegeven |Ticketing error |AdresStraatnaamGehistoreerdOfAfgekeurd  |De straatnaam is gehistoreerd of afgekeurd.  |  
|Verwijderd bronAdresId meegegeven|Ticketing error |VerwijderdAdres  |Verwijderd adres.  |  
|Afgekeurd/gehistoreerd bronAdresId meegegeven |Ticketing error |BronAdresIdAfgekeurdGehistoreerd  | Deze actie is enkel toegestaan op adressen met status 'voorgesteld' of 'inGebruik': <adresid>. |  
|Meegegeven bronAdresId is een busnummer |Ticketing error |BronAdresIdBusnummer  | Deze actie is niet toegestaan op adressen met een busnummer: <adresid>.  |  
|Het adres bij bronAdresId = het adres bij doelHuisnummer |Ticketing error |BronAdresIdHetzelfdeAlsDoelHuisnummer  | Het bronAdresId is hetzelfde als het doelHuisnummer: <adresid>.  |  
|Het bronAdresId heeft geen postinfoId |Ticketing error |BronAdresIdPostcode  |Deze actie is niet toegestaan op adressen die geen postcode hebben: <adresid>.  |  

#### Corrigeer de goedkeuring van een adres

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig adresId meegegeven   |Error 400  |/ |De waarde 'adresId' is ongeldig.  |
|Onbestaand adresId meegegeven  |Error 404 |/  |/  |
|Status adresId afgekeurd/gehistoreerd|Ticketing error|AdresAfgekeurdGehistoreerd| Deze actie is enkel toegestaan op adressen met status 'inGebruik'. |
|Adres in straatnaam met status afgekeurd/gehistoreerd|Ticketing error|AdresStraatnaamVoorgesteldOfInGebruik| Deze actie is enkel toegestaan binnen straatnamen met  status 'voorgesteld' of 'inGebruik'. |
|Adres is niet officieelToegekend |Ticketing error |AdresNietOfficeeltoegekend  |Deze actie is enkel toegestaan voor officieel toegekende adressen.  |
|Verwijderd adresId meegegeven |Ticketing error |VerwijderdAdres  |Verwijderd adres.  |

#### Corrigeer de afkeuring van een adres
  
|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig adresId meegegeven   |Error 400  |/ |De waarde 'adresId' is ongeldig.  |
|Onbestaand adresId meegegeven  |Error 404 |/  |/  |
|Adres is een busnummer & mag niet voorlopen op status adres dat huisnummer is|Ticketing error |AdresHuisnummerAfgekeurdOfGehistoreerd | Deze actie is enkel toegestaan op adressen waarbij het huisnummer de status ‘voorgesteld' of ‘inGebruik’ heeft. |
|Wanneer het huisnummer of busnummer al bestaat|Ticketing error |AdresBestaandeHuisnummerBusnummerCombinatie | Deze combinatie huisnummer-busnummer bestaat reeds voor de opgegeven straatnaam. |
|Adres met huisnummer werd gecorrigeerd na opheffing van adres met busnummer|Ticketing error |AdresBusnummerHuisnummerInconsistent | Deze actie is niet toegestaan op een busnummer wegens een inconsistent huisnummer.|
|Postcode van adres met huisnummer werd gecorrigeerd na opheffing adres met busnummer|Ticketing error |AdresBusnummerPostcodeInconsistent | Deze actie is niet toegestaan op een busnummer wegens een inconsistente postcode. |  
|Status adresId afgekeurd/gehistoreerd|Ticketing error|AdresInGebruikOfGehistoreerd| Deze actie is enkel toegestaan op adressen met status 'afgekeurd'.|
|Adres in straatnaam met status afgekeurd/gehistoreerd|Ticketing error|AdresStraatnaamVoorgesteldOfInGebruik| Deze actie is enkel toegestaan binnen straatnamen met  status 'voorgesteld' of 'inGebruik'. |
|Verwijderd adresId meegegeven |Ticketing error |VerwijderdAdres  |Verwijderd adres.  | 
  
#### Corrigeer de opheffing van een adres
  
|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig adresId meegegeven   |Error 400  |/ |De waarde 'adresId' is ongeldig.  |
|Onbestaand adresId meegegeven  |Error 404 |/  |/  |
|Adres is een busnummer & mag niet voorlopen op status adres dat huisnummer is|Ticketing error |AdresHuisnummerVoorgesteldAfgekeurdOfGehistoreerd | Deze actie is enkel toegestaan op adressen waarbij het huisnummer de status ‘inGebruik’ heeft. |
|Wanneer het huisnummer of busnummer al bestaat|Ticketing error |AdresBestaandeHuisnummerBusnummerCombinatie | Deze combinatie huisnummer-busnummer bestaat reeds voor de opgegeven straatnaam. |
|Adres met huisnummer werd gecorrigeerd na opheffing van adres met busnummer|Ticketing error |AdresBusnummerHuisnummerInconsistent | Deze actie is niet toegestaan op een busnummer wegens een inconsistent huisnummer.|
|Postcode van adres met huisnummer werd gecorrigeerd na opheffing adres met busnummer|Ticketing error |AdresBusnummerPostcodeInconsistent | Deze actie is niet toegestaan op een busnummer wegens een inconsistente postcode. |  
|Status adresId afgekeurd/voorgesteld|Ticketing error|AdresAfgekeurdOfVoorgesteld| Deze actie is enkel toegestaan op adressen met status 'gehistoreerd'. |
|Adres in straatnaam met status afgekeurd/gehistoreerd|Ticketing error|AdresStraatnaamVoorgesteldOfInGebruik| Deze actie is enkel toegestaan binnen straatnamen met  status 'voorgesteld' of 'inGebruik'. |
|Verwijderd adresId meegegeven |Ticketing error |VerwijderdAdres  |Verwijderd adres.  | 
  
#### Corrigeer de regularisering van een adres
  
|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig adresId meegegeven   |Error 400  |/ |De waarde 'adresId' is ongeldig.  |
|Onbestaand adresId meegegeven  |Error 404 |/  |/  |
|Status adresId afgekeurd/gehistoreerd|Ticketing error|AdresGehistoreerdOfAfgekeurd| Deze actie is enkel toegestaan op adressen met status 'voorgesteld' of 'inGebruik'. |
|Verwijderd adresId meegegeven |Ticketing error |VerwijderdAdres  |Verwijderd adres.  |
|Adres is een busnummer & mag niet voorlopen op status adres dat huisnummer is|Ticketing error |AdresHuisnummerVoorgesteldGehistoreerdOfAfgekeurd | Deze actie is enkel toegestaan op adressen waarbij het huisnummer de status ‘inGebruik’ heeft. |
  
#### Corrigeer de deregularisering van een adres

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig adresId meegegeven   |Error 400  |/ |De waarde 'adresId' is ongeldig.  |
|Onbestaand adresId meegegeven  |Error 404 |/  |/  |
|Status adresId afgekeurd/gehistoreerd|Ticketing error|AdresGehistoreerdOfAfgekeurd| Deze actie is enkel toegestaan op adressen met status 'voorgesteld' of 'inGebruik'. |
|Verwijderd adresId meegegeven |Ticketing error |VerwijderdAdres  |Verwijderd adres.  |  
  
#### Corrigeer de adrespositie van een adres
 
|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig adresId meegegeven   |Error 400  |/ |De waarde 'adresId' is ongeldig.  |
|Combinatie positieGeometrieMethode & positieSpecificatie is niet correct  |Error 400  |AdresPositieSpecificatieValidatie |Ongeldige positieSpecificatie. |
|Het veld positie leeg meegegeven   |Error 400  |AdresPositieVerplicht |De positie is verplicht.   |
|Ongeldig waarde bij positie meegegeven   |Error 400  |AdresPositieformaatValidatie |De positie is geen geldige gml-puntgeometrie.   |
|Het veld positie/positieSpecificatie/positieGeometrieMethode niet/leeg/onbestaande waarde meegegeven  |Error 400  |JsonInvalid |Json is not valid. |
|Onbestaand adresId meegegeven  |Error 404 |/  |/  |
|Status adresId afgekeurd/gehistoreerd|Ticketing error|AdresGehistoreerdOfAfgekeurd| Deze actie is enkel toegestaan op adressen met status 'voorgesteld' of 'inGebruik'. |
|Adres in straatnaam met status afgekeurd/gehistoreerd|Ticketing error|AdresStraatnaamVoorgesteldOfInGebruik| Deze actie is enkel toegestaan binnen straatnamen met  status 'voorgesteld' of 'inGebruik'. |
|Verwijderd adresId meegegeven |Ticketing error |VerwijderdAdres  |Verwijderd adres.  |  
 
#### Corrigeer de postcode van een adres
  
|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig adresId meegegeven   |Error 400  |/ |De waarde 'adresId' is ongeldig.  |
|Het veld postinfoId niet meegegeven |Error 400  |JsonInvalid |Json is not valid. |
|Onbestaande postinfoId meegegeven |Error 400  |AdresPostinfoNietGekendValidatie | De postinfo 'postinfoId' is niet gekend in het postinforegister.  |
|Onbestaand adresId meegegeven  |Error 404 |/  |/  |
|Status adresId afgekeurd/gehistoreerd|Ticketing error|AdresGehistoreerdOfAfgekeurd| Deze actie is enkel toegestaan op adressen met status 'voorgesteld' of 'inGebruik'. |
|Postcode ligt niet in de gemeente van het adres |Ticketing error |AdresPostinfoNietInGemeente  |De ingevoerde postcode wordt niet gebruikt binnen deze gemeente.  |  
|Het adres is een busnummer|Ticketing error |AdresPostinfoGeenHuisnummer  |Het is niet mogelijk om de postcode van een busnummer te veranderen.   |  
|Adres in straatnaam met status afgekeurd/gehistoreerd|Ticketing error|AdresStraatnaamVoorgesteldOfInGebruik| Deze actie is enkel toegestaan binnen straatnamen met  status 'voorgesteld' of 'inGebruik'. |
|Verwijderd adresId meegegeven |Ticketing error |VerwijderdAdres  |Verwijderd adres.  |   
   
#### Wijzig de postcode van een adres
  
|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig adresId meegegeven   |Error 400  |/ |De waarde 'adresId' is ongeldig.  |
|Het veld postinfoId niet meegegeven |Error 400  |JsonInvalid |Json is not valid. |
|Onbestaande postinfoId meegegeven |Error 400  |AdresPostinfoNietGekendValidatie | De postinfo 'postinfoId' is niet gekend in het postinforegister.  |
|Onbestaand adresId meegegeven  |Error 404 |/  |/  |
|Status adresId afgekeurd/gehistoreerd|Ticketing error|AdresGehistoreerdOfAfgekeurd| Deze actie is enkel toegestaan op adressen met status 'voorgesteld' of 'inGebruik'. |  
|Het adres is een busnummer|Ticketing error |AdresPostinfoGeenHuisnummer  |Het is niet mogelijk om de postcode van een busnummer te veranderen.   |  
|Adres in straatnaam met status afgekeurd/gehistoreerd|Ticketing error|AdresStraatnaamVoorgesteldOfInGebruik| Deze actie is enkel toegestaan binnen straatnamen met  status 'voorgesteld' of 'inGebruik'. |
|Verwijderd adresId meegegeven |Ticketing error |VerwijderdAdres  |Verwijderd adres.  | 
   
#### Corrigeer het huisnummer van een adres

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig adresId meegegeven   |Error 400  |/ |De waarde 'adresId' is ongeldig.  |
|Het veld huisnummer niet of leeg meegegeven |Error 400  |JsonInvalid |Json is not valid. |
|Huisnummer voldoet niet aan regex huisnummer |Error 400  |AdresOngeldigHuisnummerformaat |Ongeldig huisnummerformaat. |
|Onbestaand adresId meegegeven  |Error 404 |/  |/  |
|Status adresId afgekeurd/gehistoreerd|Ticketing error|AdresGehistoreerdOfAfgekeurd| Deze actie is enkel toegestaan op adressen met status 'voorgesteld' of 'inGebruik'. |   
|Wanneer het huisnummer al bestaat|Ticketing error |AdresBestaandeHuisnummerBusnummerCombinatie  | Deze combinatie huisnummer-busnummer bestaat reeds voor de opgegeven straatnaam.   |  
|Het adres mag geen busnummer zijn.|Ticketing error |AdresCorrectieHuisnummermetBusnummer  |Te corrigeren huisnummer mag geen busnummer bevatten.   |   
|Adres in straatnaam met status afgekeurd/gehistoreerd|Ticketing error|AdresStraatnaamVoorgesteldOfInGebruik| Deze actie is enkel toegestaan binnen straatnamen met  status 'voorgesteld' of 'inGebruik'. |
|Verwijderd adresId meegegeven |Ticketing error |VerwijderdAdres  |Verwijderd adres.  | 
   
#### Corrigeer het busnummer van een adres

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig adresId meegegeven   |Error 400  |/ |De waarde 'adresId' is ongeldig.  |
|Het veld busnummer niet of leeg meegegeven |Error 400  |JsonInvalid |Json is not valid. |
|Busnummer voldoet niet aan regex busnummer |Error 400  |AdresOngeldigBusnummerformaat |Ongeldig busnummerformaat. |
|Onbestaand adresId meegegeven  |Error 404 |/  |/  |
|Status adresId afgekeurd/gehistoreerd|Ticketing error|AdresGehistoreerdOfAfgekeurd| Deze actie is enkel toegestaan op adressen met status 'voorgesteld' of 'inGebruik'. |   
|Wanneer het busnummer al bestaat|Ticketing error |AdresBestaandeHuisnummerBusnummerCombinatie  | Deze combinatie huisnummer-busnummer bestaat reeds voor de opgegeven straatnaam.   |  
|Het adres mag geen huisnummer zijn.|Ticketing error |AdresHuisnummerZonderBusnummer  |Het adres heeft geen te corrigeren busnummer.   |   
|Adres in straatnaam met status afgekeurd/gehistoreerd|Ticketing error|AdresStraatnaamVoorgesteldOfInGebruik| Deze actie is enkel toegestaan binnen straatnamen met  status 'voorgesteld' of 'inGebruik'. |
|Verwijderd adresId meegegeven |Ticketing error |VerwijderdAdres  |Verwijderd adres.  | 

## Gebouwen

#### Plan een gebouw in 

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Parameter geometriePolygoon ontbreekt   |Error 400  |JsonInvalid  |Json is not valid.  |
|GeometriePolygoon leeg/niet correct meegegeven |Error 400 |GebouwPolygoonValidatie  |Ongeldig formaat geometriePolygoon. |

#### Plaats een gebouw in aanbouw

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouwId meegegeven   |Error 400  |/ |De waarde 'gebouwId' is ongeldig.  |
|Onbestaand gebouwId meegegeven  |Error 404 |/  |/  |
|Status gebouwId gerealiseerd/gehistoreerd/nietGerealiseerd|Ticketing error|GebouwGehistoreerdGerealiseerdOfNietGerealiseerd| Deze actie is enkel toegestaan op gebouwen met status 'gepland'. |
|Verwijderd gebouwId meegegeven |Ticketing error |VerwijderdGebouw  |Verwijderd gebouw.  |

#### Realiseer een gebouw

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouwId meegegeven   |Error 400  |/ |De waarde 'gebouwId' is ongeldig.  |
|Onbestaand gebouwId meegegeven  |Error 404 |/  |/  |
|Status gebouwId gepland/gehistoreerd/nietGerealiseerd|Ticketing error|GebouwGehistoreerdGeplandOfNietGerealiseerd|  Deze actie is enkel toegestaan op gebouwen met status 'inAanbouw'. |
|Verwijderd gebouwId meegegeven |Ticketing error |VerwijderdGebouw  |Verwijderd gebouw.  |
  
#### Realiseer een gebouw niet

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouwId meegegeven   |Error 400  |/ |De waarde 'gebouwId' is ongeldig.  |
|Onbestaand gebouwId meegegeven  |Error 404 |/  |/  |
|Status gebouwId gerealiseerd/gehistoreerd|Ticketing error|GebouwGehistoreerdOfGerealiseerd| Deze actie is enkel toegestaan op gebouwen met status 'gepland' of ‘inAanbouw’.  |
|Verwijderd gebouwId meegegeven |Ticketing error |VerwijderdGebouw  |Verwijderd gebouw.  |
  
 #### Verwijder een geschetst gebouw

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouwId meegegeven   |Error 400  |/ |De waarde 'gebouwId' is ongeldig.  |
|Onbestaand gebouwId meegegeven  |Error 404 |/  |/  |
|GeometrieMethode = ingemetenGRB|Ticketing error|GebouwGeometrieMethodeIngemetenGRB| Deze actie is enkel toegestaan op gebouwen met geometrieMethode 'ingeschetst'.|
  
#### Corrigeer de realisering van een gebouw

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouwId meegegeven   |Error 400  |/ |De waarde 'gebouwId' is ongeldig.  |
|Onbestaand gebouwId meegegeven  |Error 404 |/  |/  |
|Status gebouwId gepland/gehistoreerd/nietGerealiseerd|Ticketing error|GebouwGeplandGehistoreerdOfNietGerealiseerd | Deze actie is enkel toegestaan op gebouwen met status 'gerealiseerd'.  |
|GeometrieMethode = ingemetenGRB|Ticketing error|GebouwGeometrieMethodeIngemetenGRB| Deze actie is enkel toegestaan op gebouwen met geometrieMethode 'ingeschetst'.|
|Gebouw heeft gekoppelde gehistoreerde gebouweenheden|Ticketing error|GebouwBevatGehistoreerdeGebouweenheden| Deze actie is niet toegestaan wanneer er gehistoreerde gebouweenheden aanwezig zijn.|
|Verwijderd gebouwId meegegeven |Ticketing error |VerwijderdGebouw  |Verwijderd gebouw.  |
 
#### Corrigeer de niet realisering van een gebouw

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouwId meegegeven   |Error 400  |/ |De waarde 'gebouwId' is ongeldig.  |
|Onbestaand gebouwId meegegeven  |Error 404 |/  |/  |
|Status gebouwId inAanbouw/gehistoreerd/gerealiseerd|Ticketing error|GebouwInAanbouwGerealiseerdOfGehistoreerd | Deze actie is enkel toegestaan op geschetste gebouwen met status 'nietGerealiseerd’. |
|GeometrieMethode = ingemetenGRB|Ticketing error|GebouwGeometrieMethodeIngemetenGRB| Deze actie is enkel toegestaan op gebouwen met geometrieMethode 'ingeschetst'.|
|Verwijderd gebouwId meegegeven |Ticketing error |VerwijderdGebouw  |Verwijderd gebouw.  |

#### Corrigeer de in aanbouw plaatsing van een gebouw

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouwId meegegeven   |Error 400  |/ |De waarde 'gebouwId' is ongeldig.  |
|Onbestaand gebouwId meegegeven  |Error 404 |/  |/  |
|Status gebouwId gerealiseerd/gehistoreerd/nietGerealiseerd|Ticketing error|GebouwGerealiseerdGehistoreerdOfNietGerealiseerd | Deze actie is enkel toegestaan op geschetste gebouwen met status 'inAanbouw’. |
|Verwijderd gebouwId meegegeven |Ticketing error |VerwijderdGebouw  |Verwijderd gebouw.  |
  
#### Corrigeer de geometrie van een geschetst gebouw

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouwId meegegeven   |Error 400  |/ |De waarde 'gebouwId' is ongeldig.  |
|Onbestaand gebouwId meegegeven  |Error 404 |/  |/  |
|Status gebouwId gehistoreerd/gerealiseerd|Ticketing error|GebouwGehistoreerdOfNietGerealiseerd | Deze actie is enkel toegestaan op gebouwen met status 'gepland', 'inAanbouw' of 'gerealiseerd'. |
|GeometrieMethode = ingemetenGRB|Ticketing error|GebouwGeometrieMethodeIngemetenGRB| Deze actie is enkel toegestaan op gebouwen met geometrieMethode 'ingeschetst'.|
|Geometrie gekoppelde gebouweenheden ligt niet in nieuwe geometrie |Ticketing error|GebouweenheidGeomtrieBuitenGebouwGeometrie| Het gebouw heeft onderliggende gebouweenheden met status 'gepland' of 'gerealiseerd' buiten de nieuw geschetste gebouwgeometrie. |
|Verwijderd gebouwId meegegeven |Ticketing error |VerwijderdGebouw  |Verwijderd gebouw.  |


## Gebouweenheden
  
#### Plan een gebouweenheid in

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Het veld gebouwId/afwijkingVastgesteld/functie/positieGeometrieMethode niet meegegeven / Ongeldige waarde of leeg bij positieGeometrieMethode/afwijkingVastgesteld/functie meegegeven  |Error 400  |JsonInvalid |Json is not valid.  |
|GebouwId leeg of ongeldige waarde meegegeven |Error 400 |GebouweenheidGebouwIdNietGekendValidatie | De gebouwId 'gebouwId' is niet gekend in het gebouwenregister.   |
|Het veld positie niet/leeg meegegeven  |Error 400  |GebouweenheidGebouwIdNietGekendValidatie |De verplichte parameter 'positie' ontbreekt.  |
|Het veld positie met ongeldige waarde meegegeven  |Error 400  |GebouweenheidPositieformaatValidatie |De positie is geen geldige gml-puntgeometrie.  |
|De nieuwe positie ligt buiten de geometrie van het gebouw|Ticketing error |GebouweenheidOngeldigePositieValidatie | De positie dient binnen de geometrie van het gebouw te liggen.  |
|Gehistoreerd of nietGerealiseerd gebouwId meegegeven |Ticketing error |GebouweenheidGebouwIdNietGerealiseerdofGehistoreerd | De gebouwId is niet gerealiseerd of gehistoreerd.  |
  
#### Realiseer een gebouweenheid

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouweenheidId meegegeven   |Error 400  |/ |De waarde 'gebouweenheidId' is ongeldig.  |
|Onbestaand gebouweenheidId meegegeven  |Error 404 |/  |/  |
|Gebouweenheid met functie gemeenschappelijkDeel meegegeven |Ticketing error |GebouweenheidGemeenschappelijkDeel  | Deze actie is niet toegestaan op gebouweenheden me functie gemeenschappelijkDeel.  |
|Gebouweenheid ligt in gebouw met status gepland/inAanbouw/gehistoreerd/nietGerealiseerd |Ticketing error | GebouwStatusNietInGerealiseerd|Deze actie is enkel toegestaan binnen een gerealiseerd gebouw.  |
|Status gebouweenheidId gehistoreerd/nietGerealiseerd|Ticketing error|GebouweenheidGehistoreerdOfNietGerealiseerd| Deze actie is enkel toegestaan op gebouweenheden met status 'gepland'. |
|Verwijderd gebouweenheidId meegegeven |Ticketing error |VerwijderdeGebouweenheid  |Verwijderde gebouweenheid.  |
  
#### Realiseer een gebouweenheid niet

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouweenheidId meegegeven   |Error 400  |/ |De waarde 'gebouweenheidId' is ongeldig.  |
|Onbestaand gebouweenheidId meegegeven  |Error 404 |/  |/  |
|Gebouweenheid met functie gemeenschappelijkDeel meegegeven |Ticketing error |GebouweenheidGemeenschappelijkDeel  | Deze actie is niet toegestaan op gebouweenheden me functie gemeenschappelijkDeel.  |
|Status gebouweenheidId gehistoreerd/gerealiseerd|Ticketing error|GebouweenheidGehistoreerdOfGerealiseerd|  Deze actie is enkel toegestaan op gebouweenheden met status 'gepland'. |
|Verwijderd gebouweenheidId meegegeven |Ticketing error |VerwijderdeGebouweenheid  |Verwijderde gebouweenheid.  |
  
#### Hef een gebouweenheid op

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouweenheidId meegegeven   |Error 400  |/ |De waarde 'gebouweenheidId' is ongeldig.  |
|Onbestaand gebouweenheidId meegegeven  |Error 404 |/  |/  |
|Gebouweenheid met functie gemeenschappelijkDeel meegegeven |Ticketing error |GebouweenheidGemeenschappelijkDeel  | Deze actie is niet toegestaan op gebouweenheden me functie gemeenschappelijkDeel.  |
|Gebouweenheid ligt in gebouw met status gehistoreerd/nietGerealiseerd |Ticketing error |GebouwStatusNietInGeplandInAanbouwOfGerealiseerd|  Deze actie is enkel toegestaan binnen een gepland, inAanbouw of gerealiseerd gebouw.  |
|Status gebouweenheidId gepland/nietGerealiseerd|Ticketing error|GebouweenheidGeplandOfNietGerealiseerd| Deze actie is enkel toegestaan op gebouweenheden met status 'gerealiseerd'. |
|Verwijderd gebouweenheidId meegegeven |Ticketing error |VerwijderdeGebouweenheid  |Verwijderde gebouweenheid.  |
  
#### Verwijder een gebouweenheid

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouweenheidId meegegeven   |Error 400  |/ |De waarde 'gebouweenheidId' is ongeldig.  |
|Onbestaand gebouweenheidId meegegeven  |Error 404 |/  |/  |
|Gebouweenheid met functie gemeenschappelijkDeel meegegeven |Ticketing error |GebouweenheidGemeenschappelijkDeel  | Deze actie is niet toegestaan op gebouweenheden me functie gemeenschappelijkDeel.  |

#### Regulariseer een gebouweenheid
  
|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouweenheidId meegegeven   |Error 400  |/ |De waarde 'gebouweenheidId' is ongeldig.  |
|Onbestaand gebouweenheidId meegegeven  |Error 404 |/  |/  |
|Gebouweenheid met functie gemeenschappelijkDeel meegegeven |Ticketing error |GebouweenheidGemeenschappelijkDeel  | Deze actie is niet toegestaan op gebouweenheden me functie gemeenschappelijkDeel.  |
|Gebouweenheid ligt in gebouw met status gehistoreerd/nietGerealiseerd |Ticketing error |GebouwStatusNietInGeplandInAanbouwOfGerealiseerd | Deze actie is enkel toegestaan binnen een gepland, inAanbouw of gerealiseerd gebouw.  |
|Status gebouweenheidId gehistoreerd/nietGerealiseerd|Ticketing error|GebouweenheidNietGerealiseerdOfGehistoreerd | Deze actie is enkel toegestaan op gebouweenheden met status 'gepland' of 'gerealiseerd'. |
|Verwijderd gebouweenheidId meegegeven |Ticketing error |VerwijderdeGebouweenheid  |Verwijderde gebouweenheid.  |
  
#### Deregulariseer een gebouweenheid
  
|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouweenheidId meegegeven   |Error 400  |/ |De waarde 'gebouweenheidId' is ongeldig.  |
|Onbestaand gebouweenheidId meegegeven  |Error 404 |/  |/  |
|Gebouweenheid met functie gemeenschappelijkDeel meegegeven |Ticketing error |GebouweenheidGemeenschappelijkDeel  | Deze actie is niet toegestaan op gebouweenheden me functie gemeenschappelijkDeel.  |
|Gebouweenheid ligt in gebouw met status gehistoreerd/nietGerealiseerd |Ticketing error  | GebouwStatusNietInGeplandInAanbouwOfGerealiseerd|Deze actie is enkel toegestaan binnen een gepland, inAanbouw of gerealiseerd gebouw.|
|Status gebouweenheidId gehistoreerd/nietGerealiseerd|Ticketing error|GebouweenheidNietGerealiseerdOfGehistoreerd | Deze actie is enkel toegestaan op gebouweenheden met status 'gepland' of 'gerealiseerd'. |
|Verwijderd gebouweenheidId meegegeven |Ticketing error |VerwijderdeGebouweenheid  |Verwijderde gebouweenheid.  |
  
#### Corrigeer de realisering van een gebouweenheid

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouweenheidId meegegeven   |Error 400  |/ |De waarde 'gebouweenheidId' is ongeldig.  |
|Onbestaand gebouweenheidId meegegeven  |Error 404 |/  |/  |
|Gebouweenheid met functie gemeenschappelijkDeel meegegeven |Ticketing error |GebouweenheidGemeenschappelijkDeel  | Deze actie is niet toegestaan op gebouweenheden me functie gemeenschappelijkDeel.  |
|Status gebouweenheidId gehistoreerd/nietGerealiseerd|Ticketing error|GebouweenheidGehistoreerdNietGerealiseerd| Deze actie is enkel toegestaan op gebouweenheden met status 'gerealiseerd'. |
|Verwijderd gebouweenheidId meegegeven |Ticketing error |VerwijderdeGebouweenheid  |Verwijderde gebouweenheid.  |

#### Corrigeer de niet realisering van een gebouweenheid

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouweenheidId meegegeven   |Error 400  |/ |De waarde 'gebouweenheidId' is ongeldig.  |
|Onbestaand gebouweenheidId meegegeven  |Error 404 |/  |/  |
|Gebouweenheid met functie gemeenschappelijkDeel meegegeven |Ticketing error |GebouweenheidGemeenschappelijkDeel  | Deze actie is niet toegestaan op gebouweenheden me functie gemeenschappelijkDeel.  |
|Gebouweenheid ligt in gebouw met status gehistoreerd/nietGerealiseerd |Ticketing error |GebouwStatusNietInGeplandInAanbouwOfGerealiseerd  | Deze actie is enkel toegestaan binnen een gepland, inAanbouw of gerealiseerd gebouw.   |
|Status gebouweenheidId gehistoreerd/gerealiseerd|Ticketing error|GebouweenheidGerealiseerdOfGehistoreerd| Deze actie is enkel toegestaan op gebouweenheden met status 'nietGerealiseerd'. |
|Verwijderd gebouweenheidId meegegeven |Ticketing error |VerwijderdeGebouweenheid  |Verwijderde gebouweenheid.  |
  
#### Corrigeer de opheffing van een gebouweenheid

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouweenheidId meegegeven   |Error 400  |/ |De waarde 'gebouweenheidId' is ongeldig.  |
|Onbestaand gebouweenheidId meegegeven  |Error 404 |/  |/  |
|Gebouweenheid met functie gemeenschappelijkDeel meegegeven |Ticketing error |GebouweenheidGemeenschappelijkDeel  | Deze actie is niet toegestaan op gebouweenheden me functie gemeenschappelijkDeel.  |
|Gebouweenheid ligt in gebouw met status gepland/inAanbouw/gehistoreerd/nietGerealiseerd |Ticketing error |GebouwStatusNietInGerealiseerd  | Deze actie is enkel toegestaan binnen een gerealiseerd gebouw.  |
|Status gebouweenheidId gepland/nietGerealiseerd|Ticketing error|GebouweenheidNietGerealiseerdOfGepland| Deze actie is enkel toegestaan op gebouweenheden met status 'gehistoreerd'. |
|Verwijderd gebouweenheidId meegegeven |Ticketing error |VerwijderdeGebouweenheid  |Verwijderde gebouweenheid.  |  
  
#### Corrigeer de regularisering van een gebouweenheid

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouweenheidId meegegeven   |Error 400  |/ |De waarde 'gebouweenheidId' is ongeldig.  |
|Onbestaand gebouweenheidId meegegeven  |Error 404 |/  |/  |
|Gebouweenheid met functie gemeenschappelijkDeel meegegeven |Ticketing error |GebouweenheidGemeenschappelijkDeel  | Deze actie is niet toegestaan op gebouweenheden me functie gemeenschappelijkDeel.  |
|Gebouweenheid ligt in gebouw met status gehistoreerd/nietGerealiseerd |Ticketing error| GebouwStatusNietInGeplandInAanbouwOfGerealiseerd|Deze actie is enkel toegestaan binnen een gepland, inAanbouw of gerealiseerd gebouw.  |
|Status gebouweenheidId gehistoreerd/nietGerealiseerd|Ticketing error|GebouweenheidNietGerealiseerdOfGehistoreerd | Deze actie is enkel toegestaan op gebouweenheden met status 'gepland' of 'gerealiseerd'. |
|Verwijderd gebouweenheidId meegegeven |Ticketing error |VerwijderdeGebouweenheid  |Verwijderde gebouweenheid.  |
  
#### Corrigeer de deregularisering van een gebouweenheid
  
|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouweenheidId meegegeven   |Error 400  |/ |De waarde 'gebouweenheidId' is ongeldig.  |
|Onbestaand gebouweenheidId meegegeven  |Error 404 |/  |/  |
|Gebouweenheid met functie gemeenschappelijkDeel meegegeven |Ticketing error |GebouweenheidGemeenschappelijkDeel | Deze actie is niet toegestaan op gebouweenheden me functie gemeenschappelijkDeel.  |
|Gebouweenheid ligt in gebouw met status gehistoreerd/nietGerealiseerd |Ticketing error | GebouwStatusNietInGeplandInAanbouwOfGerealiseerd | Deze actie is enkel toegestaan binnen een gepland, inAanbouw of gerealiseerd gebouw.  |
|Status gebouweenheidId gehistoreerd/nietGerealiseerd|Ticketing error|GebouweenheidNietGerealiseerdOfGehistoreerd | Deze actie is enkel toegestaan op gebouweenheden met status 'gepland' of 'gerealiseerd'. |
|Verwijderd gebouweenheidId meegegeven |Ticketing error |VerwijderdeGebouweenheid  |Verwijderde gebouweenheid.  |

#### Corrigeer de positie van een gebouweenheid
  
|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouweenheidId meegegeven   |Error 400  |/ |De waarde 'gebouweenheidId' is ongeldig.  |
|Het veld positieGeometrieMethode niet/leeg/ongeldige waarde meegegeven   |Error 400  |JsonInvalid |Json is not valid.  |
|Het veld positie niet/leeg/ongeldige waarde meegegeven   |Error 400  |GebouweenheidPositieformaatValidatie |De positie is geen geldige gml-puntgeometrie.  |
|Onbestaand gebouweenheidId meegegeven  |Error 404 |/  |/  |
|De nieuwe positie ligt buiten de geometrie van het gebouw  |Ticketing error  |GebouweenheidOngeldigePositieValidatie|  De positie dient binnen de geometrie van het gebouw te liggen.   |  
|Gebouweenheid met functie gemeenschappelijkDeel meegegeven |Ticketing error |GebouweenheidGemeenschappelijkDeel  | Deze actie is niet toegestaan op gebouweenheden me functie gemeenschappelijkDeel.  |
|Gebouweenheid ligt in gebouw met status gehistoreerd/nietGerealiseerd |Ticketing error | GebouwStatusNietInGeplandInAanbouwOfGerealiseerd|Deze actie is enkel toegestaan binnen een gepland, inAanbouw of gerealiseerd gebouw.  |
|Status gebouweenheidId gehistoreerd/nietGerealiseerd|Ticketing error|GebouweenheidNietGerealiseerdOfGehistoreerd | Deze actie is enkel toegestaan op gebouweenheden met status 'gepland' of 'gerealiseerd'. |
|Verwijderd gebouweenheidId meegegeven |Ticketing error |VerwijderdeGebouweenheid  |Verwijderde gebouweenheid.  |

#### Koppel een adres aan een gebouweenheid

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouweenheidId meegegeven   |Error 400  |/ |De waarde 'gebouweenheidId' is ongeldig.  |
|Het veld adresId niet meegegeven of met waarde leeg of null meegegeven|Error 400|JsonInvalid|Json is not valid.|
|Ongeldige waarde bij adresId / verwijderd adresId meegegeven |Error 400|GebouweenheidAdresOngeldig|Ongeldig adresId.|
|AdresId met status afgekeurd/gehistoreerd meegegeven|Error 400|GebouweenheidAdresAfgekeurdOfGehistoreerd| Het adres is afgekeurd of gehistoreerd.|
|Onbestaand gebouweenheidId meegegeven  |Error 404|/  |/  |
|Status gebouweenheidId gehistoreerd/nietGerealiseerd|Ticketing error|GebouweenheidNietGerealiseerdOfGehistoreerd| Deze actie is enkel toegestaan op gebouweenheden met status 'gepland' of 'gerealiseerd'.|
|Verwijderd gebouweenheidId meegegeven |Ticketing error|VerwijderdeGebouweenheid|Verwijderde gebouweenheid.|
  
#### Ontkoppel een adres van een gebouweenheid

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouweenheidId meegegeven   |Error 400  |/ |De waarde 'gebouweenheidId' is ongeldig.  |
|Het veld adresId niet meegegeven of met waarde leeg of null meegegeven|Error 400|JsonInvalid|Json is not valid.|
|Ongeldige waarde bij adresId / verwijderd adresId meegegeven |Error 400|GebouweenheidAdresOngeldig|Ongeldig adresId.|
|Onbestaand gebouweenheidId meegegeven  |Error 404|/  |/  |
|Verwijderd gebouweenheidId meegegeven |Ticketing error|VerwijderdeGebouweenheid|Verwijderde gebouweenheid.|
  
## Percelen

#### Koppel een adres van een perceel

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Het veld adresId niet meegegeven of met waarde leeg of null meegegeven   |Error 400  |JsonInvalid  |Json is not valid.  |
|Ongeldige waarde bij adresId / verwijderd adresId meegegeven |Error 400 |PerceelAdresOngeldig  |Ongeldig adresId.  |
|AdresId met status afgekeurd/gehistoreerd meegegeven|Error 400|PerceelAdresAfgekeurdOfGehistoreerd |Het adres is afgekeurd of gehistoreerd.|
|Onbestaand perceelId meegegeven  |Error 404 |/  |/  |
|Status perceelId gehistoreerd|Ticketing error|PerceelGehistoreerd|Deze actie is enkel toegestaan op percelen met status 'gerealiseerd'.|
|Verwijderd perceelId meegegeven |Ticketing error |VerwijderdPerceel  |Verwijderd perceel.  |

#### Ontkoppel een adres van een perceel

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Het veld adresId niet meegegeven of met waarde leeg of null meegegeven|Error 400|JsonInvalid|Json is not valid.|
|Ongeldige waarde bij adresId / verwijderd adresId meegegeven |Error 400|PerceelAdresOngeldig|Ongeldig adresId.|
|Onbestaand perceelId meegegeven  |Error 404|/  |/  |
|Verwijderd perceelId meegegeven |Ticketing error|VerwijderdPerceel|Verwijderd perceel.|
