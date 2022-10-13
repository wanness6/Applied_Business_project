# 1 Project inleiding
<br><h3>BluePrint: The Customer Link</h3>
<br>Wannes Strauven & Max Loubry
<br>Traject: Bachelor Toegepaste Informatica
<br>3ITBUS
<br>Alec Wuyts, Peter Zajc

# 2 Opdrachtgever
Voor het vak Applied Business Project kregen wij van opdrachtgever Alec Wuyts de
opdracht om een simpele Salesforce package te maken. <br>Wij worden voor dit project begeleid en ondersteund door Peter Zajc.

# 3 Samenvatting
De klant Maakt gebruik van een SalesForce platform en heeft ons de taak gegeven om zijn platform-ervaring te verbeteren met wat meer mogelijkheden.
Hierdoor gaat hij en zijn medewerkers beter werk kunnen verrichten en grote fouten vermijden. 
We zijn welkom om te werken op zijn kantoor en maken hier wekelijks gebruik van om samen te kunnen zitten met de klant. 

# 4 Situatie As-Is 
De klant kan in zijn Salesforce platform gebruik maken van de Tracking history, die de aanpassingen van fields in een object bijhoudt en laat zien wanneer, wie
deze heeft aangepast. 

![](AS-IS-AD.png)
Hij kan op een object aanduiden welke fields hij wilt tracken en deze zullen dan als ze aangepast worden bijgehouden en getoont worden in de apps die gebruikt worden door de klant.

![](AS-IS-AD2.png)

# 5 Probleemstelling
De functie History tracking heeft echter enkele uitzonderingen waar je als gebruiker rekening mee moet houden (zie Salesforce: Field History Tracking). 
Zo zal de functie niet meer dan 20 fields tegelijkertijd kunnen tracken.
Ook kan de field die getrackt wordt niet bestaan uit meer dan 255 characters, zo kunnen long text areas en andere grote waarden niet worden bijgehouden.
als de klant dan beschrijvingen van objecten of andere grote waardes wil bijhouden gaan die volgens de standaard regels van tracking history niet.

![](Probleemstelling.png)

# 6 Situatie To-Be
Zoals er in het As-Is onderdeel staat van het document gaan we ervoor zorgen dat de limitaties worden overschreden met een salesforce applicatie.

## 6.1 Projectdefinitie
De limitatie op de grootte van de waarde is lastig als je beschrijvingsaanpassingen wilt documenteren in de tracking history.
de doelstelling is de gebruiker de keuze te laten maken om de limitatie van history tracking uit te zetten. Salesforce zelfhoudt dit tegen maar we gaan
dit via een applicatie omzeilen. de gebruiker zal een kunnen kiezen of ze wel of niet gebruik gaan maken van de limitatieomzeiling door dit aan te duiden voor
hun gekozen standaard of custom objecten. 

## 6.2 Scope
### 6.2.1 Functionaliteiten
- standaard en custom objecten kiezen.
- fields aanduiden.
- limitatie keuze aanduiden.
- bijhouden van de waardes.

### 6.2.2 use cases
gebruiker maakt keuze in de applicatie, deze kiest een object op welke de tracking moet gebeuren en welke fields hij graag wilt. 
Daarnaast kan hij ook aanduiden of ze de limiet willen overschrijden.

![](use_case.png)
![](usecaseinfo.png)

## 6.3 Nice to have
- Waarschuwing weergeven na keuze.
- Salesforce admin raadplegen voor extra opslag.

## 6.4 Assumpties
- De gebruiker heeft een geldige salesforce licentie.
- De beveiliging van de salesforce setup niet gewijzigd worden.

## 6.5 Niet in scope
- Verdere opleidingen worden niet gegeven.
- Verdere onderhoud van de applicatie zal niet worden voorzien na de oplevering.
- andere limitaties van salesforce over tracking worden niet verwerkt.

# 7 Planning
| **Onderdeel**            | **Deadline**   |
| -------------------- | -----------|
| Kick-off & Interview | `30/09/2022` |
| Blueprint | `14/10/2022` |
| Mockups | `14/10/2022` |
| **Tussentijdse evaluatie** | **`18/11/2022`** |
| Development | `23/12/2022` |
| Testing | `23/12/2022` |
| **Finale oplevering** | **`23/12/2022`** |

## Hoofdlijnen

## Toelichting fases


# 8 Functioneel design
Salesforce biedt de mogelijkheid om zeer efficiënt kleine applicaties te bouwen a.d.h.v. no-
code, daarom wordt er gebruik gemaakt van Salesforce en Figma (een design tool) om mock-
ups te maken. 

## 8.1 limitaties overschrijden.
een gebruiker kan via de gebouwde applicatie kiezen voor welke objecten hij/zij gebruik gaat maken van de limitatie. 
De gerbuiker kan nog steeds de gekozen fields aanduiden en kiezen of deze mag overschreden worden.
dit zal per gebruiker mogelijk zijn en deze regels van limitatie overschrijding zullen enkel als hij deze heeft aangeduid gelden.


# 9 Technisch design
## 9.1 gebruikte technologieën
### 9.1.1 Lightning Web Components (LWC) 
LWC is een front-end framework binnen Salesforce. Met dit framework 
kan er een UI gebouwd worden voor een applicatie. Het bouwen van de 
UI kan met html- en javascript code. Het is een vernieuwde versie van 
de  originele  Lightning  Components,  ook  Aura  Components  genoemd. 
De reden dat Salesforce een nieuw framework heeft gemaakt, is dat ze 
mee  moesten  gaan  met  de  nieuwste  technologieën.  LWC  gebruikt  nu 
Web Components technologieën en DOM rendering die zeer handig zijn 
voor  de  moderne  single-page  applicaties.  Ze  zijn  veel  sneller,  veiliger, 
gemakkelijker om mee te werken, herbruikbaar, bieden mobiele 
ondersteuning, enzovoort. (Voor meer informatie zie Christophe 
Coenraets. Introducing Lightning Web Components).

### 9.1.2 Apex 
Apex is een object georiënteerd programmeertaal dat in combinatie 
met een API calls kan uitvoeren op de Salesforce servers. De manier 
van code schrijven lijkt vrij goed op Java en gedraagt zich als database 
stored procedures. Business logica kan zo worden toegepast. 
Bijvoorbeeld een delete statement uitvoeren bij het drukken op een 
knop. (Voor meer informatie zie Salesforce. What is Apex?)

# 10 Beschrijving van de mogelijke interfaces
We maken enkel gebruik van Salesforce en de gegevens van de gebruiker intern op de opslag van hun platform. 

# 11 Beschrijving van eventuele datamigratie
er zal geen datamigratie plaatsvinden. de applicatie gebruikt de plaatselijke data aanwezig.

# 12 Beschrijving van eventuele impact op de huidige infrastructuur
De applicatie gaat binnen een Salesforce omgeving gelanceerd worden, dus er zal geen 
server worden voorzien om de applicatie te draaien. Verder is het ook een component die los 
hangt van alle andere componenten, waardoor er geen conflicten ontstaan.

# 13 Analyse van security en eventuele autorisatierollen
Salesforce heeft een security model van zichzelf. dit model werkt op 3 lagen Object, Field en record en elke laag heeft zijn eigen
manier om data access toe te passen.
- Object
  - Object permissions
- Field
  - Field permissions
- Record
  - Org-wide defaults
  - Role hierarchy
  - Sharing rules
  - Manual sharing

# Documentatie
Er zal een test worden voorzien na het maken van de applicatie en een user manual om de gebruiker van de applicatie goed wegwijs te maken.
