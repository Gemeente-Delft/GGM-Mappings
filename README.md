# Gemeentelijk Gegevensmodel – Mappings

**Deze repository is nog in ontwikkeling kijk voor de reeds bestaande mappings op de [WieWatStatus-lijst](https://wiewatstatus.web.app/)**

---

Welkom bij de GGM-MappingsRepository.
In deze repository verzamelen en beheren we mappings tussen het [Gemeentelijk Gegevensmodel (GGM)](www.gemeentelijkgegevensmodel.nl) en de gegevensstructuren van leverancierssystemen.

Het doel is om gezamenlijk te werken aan een gedeelde en herbruikbare set mappings, zodat gegevens eenduidig uitwisselbaar worden tussen gemeenten en hun leveranciers.

## Wat is een mapping?

Een mapping is een vertaaltabel die aangeeft hoe gegevens uit een leveranciersapplicatie aansluiten op de standaarddefinities van het GGM.  

Een voorbeeld:  

| GGM-objecttype | GGM-attribuut   | Tabel in leverancierssysteem | Veldnaam in applicatie | Aanvullende logica
|----------------|-----------------|---------------------|------------------------|---------------------|
| Inwoner        | Geboortedatum   | Tabel Persoon       | birthDate              | vertaal van YYYYMMDD naar DDMMYYYY |
| Inwoner        | Adres           | Tabel Adres.        | citizen_address        | |

Door mappings op te stellen wordt duidelijk:  
- hoe gegevens uit verschillende systemen onderling te begrijpen zijn;  
- welke velden overeenkomen, maar soms anders heten of anders gestructureerd zijn;  
- waar verschillen of hiaten zitten die aandacht vragen bij implementatie.  

## Waarom mappings?

- Gemeenten werken met tientallen systemen die allemaal eigen definities en veldnamen gebruiken.  
- Zonder mapping is gegevensuitwisseling foutgevoelig en kostbaar: elke koppeling vraagt maatwerk.  
- Met mappings ontstaat **een eenduidige vertaling** van leveranciersdata naar het GGM.  

Dit levert voordelen op:  
- **Herbruikbaarheid**: een mapping die één keer is opgesteld, kan door meerdere gemeenten en leveranciers worden gebruikt.  
- **Kwaliteit**: door feedback uit de community worden mappings steeds vollediger en consistenter.  
- **Efficiëntie**: mappings voorkomen dat elke gemeente of leverancier opnieuw dezelfde analyse moet uitvoeren.  
- **Transparantie**: alle mappings zijn open beschikbaar en traceerbaar.  

## Repository-structuur

De mappings zijn georganiseerd volgens de volgende structuur:

```
mappings/GGM-Domein/GGM-Deeldomein/Leveranciersysteem/
```

- **GGM-Domein**: het hoofdonderdeel van het Gemeentelijk Gegevensmodel waar de mapping betrekking op heeft.
- **Deeldomein**: een specifiek deelgebied binnen het domein, bijvoorbeeld onder sociaal domein: Wmo, Schulden, Inkomen.
- **Leveranciersysteem**: de naam van het leverancierssysteem waarvan de data wordt gemapt.

In elke map bevindt zich minimaal:

- `mapping.xlsx`: het Excel-bestand met de daadwerkelijke vertaaltabel tussen het leverancierssysteem en het GGM.
- `README.md`: een toelichting en aanvullende informatie over de specifieke mapping in deze map.

## Hoe bijdragen?

1. Maak een kopie van de mapping-template uit `templates/Mapping-Template.xlsx`.  
2. Vul de mapping in voor jouw applicatie of module.  
3. Plaats het ingevulde Excel-bestand in een map onder `mappings/leverancierX/vX.Y/`.  
4. Dien een Pull Request in met een korte toelichting (leverancier, systeem, versie).  
5. De Expertgroep GGM beoordeelt de mapping.  
6. Na goedkeuring wordt de mapping opgenomen in `main` en kan deze breed worden gebruikt.  

Meer detail over het aanleverproces staat in [CONTRIBUTING.md](CONTRIBUTING.md).

## Licentie

De GGM mappings zijn beschikbaar onder de [EUPL v1.2 licentie](LICENSE.md). Dit betekent dat zij vrij gebruikt, hergebruikt en gedeeld mogen worden, mits onder vermelding van de bron en met inachtneming van de licentievoorwaarden. Leveranciers mogen de mappings gebruiken binnen deze kaders, bijvoorbeeld voor toepassing in hun software of documentatie. Voorwaarde hierbij is dat gebruik plaatsvindt in lijn met het co-creatieproces zoals hierboven beschreven, waarbij per applicatie samenwerking en toetsing plaatsvindt tussen community en leverancier. Zo borgen we gezamenlijk kwaliteit, transparantie en herbruikbaarheid van de mappings.