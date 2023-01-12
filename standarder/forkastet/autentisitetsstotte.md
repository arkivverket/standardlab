# Autentisitetsstøtte :no_entry:

[![Generic badge](https://img.shields.io/badge/Status-Forkastet-darkred.svg)](https://shields.io/)

>Autentisitet er en vesentlig egenskap for arkivmateriale. Hvis vi skal ha tillit til materialets dokumentasjonsverdi, må vi kjenne til dets opphav, dvs. hvem som opprettet det og når det skjedde. Dette ble bekreftet av samtlige gjenbrukskilder teamet vurderte i arbeidet med behovet.
>
>Det vi også erfarte i dette arbeidet, var at det gav liten mening å se på autentisitet som et isolert behov. Autentisitet er en av flere egenskaper ved dokumentasjon, som skal støtte opp under behovet for tillit. De andre egenskapene er integritet, pålitelighet og anvendbarhet. Ingen ISO-standarder eller andre gjenbrukskilder pekte på spesifikke krav som alene støtter opp under autentisitetsstøtte. Det var mulig å identifisere visse metadata for autentisitetsstøtte, men det vil ikke gi så mye mening å definere et sett av metadata kun for dette formålet.  
>
>Det som kjennetegner spesielt ISO-standarder innenfor området Informasjon og dokumentasjon, er at de fremsetter en rekke metoder, tiltak og krav som samlet støtter opp under de grunnleggende egenskapene ved dokumentasjon, nemlig autentisitet, integritet, pålitelighet og anvendbarhet. Dette er ikke isolerte egenskaper som kan behandles hver for seg, men egenskaper som støtter opp under hverandre og samlet bidrar til å peke på hva som skal til for at målgruppen har tillit til dokumentasjon.  
>
>For utviklingen av arkivfaget hadde det vært nyttig og interessant å jobbe videre med et dokument som gikk nærmere inn på autentisitetsstøtte. Vi ser allikevel at et normativt produkt (en standard, veileder eller lignende) som kun fokuserte på dette ville gitt liten verdi i seg selv. En slik standard vil for eksempel ikke kunne erstatte dagens standardisering, men vil i beste fall kunne tydeliggjøre hvordan deler av hva dagens arkivdanningsstandard (Noark) ivaretar det samme behovet. Men det er ikke gitt at det kunne bidratt til en kortsiktig forenkling av dagens standard heller, uten samtidig å støtte de andre egenskapene ved dokumentasjon.  
>
>Det som er produsert frem til nå vil ha verdi i det videre arbeidet, om vi går videre med å se på de grunnleggende egenskapene ved dokumentasjon samlet. Mye av det som er skrevet om autentisitet, gjelder også for de andre egenskapene – hvordan de ivaretas ved fangst og forvaltning av dokumentasjon, over tid, og i stillstand og ved skifte av teknologi.  

Da det som ble produsert ikke er tenkt viderebrukt i denne formen, deles det av effektivitetshensyn som PDF, ikke som redigerbart innhold: [Påbegynt standard - autentisitetsstøtte (PDF)](autentisitetsstotte-innhold.pdf)

Innholdet under linjen er hypotese og rammer som lå til grunn for dokumentet som er produsert.

---

<!-- MarkdownTOC -->

- [Hypotese](#hypotese)
	- [Normeringsgrad](#normeringsgrad)
	- [Nivå](#niv%C3%A5)
	- [Målgruppe\(r\)](#m%C3%A5lgrupper)
	- [Innhold](#innhold)
	- [Åpne spørsmål](#%C3%85pne-sp%C3%B8rsm%C3%A5l)
		- [Begrensninger](#begrensninger)
- [Rammer](#rammer)
	- [Målet med normeringsprodukt](#m%C3%A5let-med-normeringsprodukt)
	- [Gjenbrukskilder](#gjenbrukskilder)
	- [Opprinnelig behovsbeskrivelse](#opprinnelig-behovsbeskrivelse)
	- [Oppdatert/utdypet målbeskrivelse](#oppdatertutdypet-m%C3%A5lbeskrivelse)
	- [Oppdaterte/utdypede suksesskriterier](#oppdaterteutdypede-suksesskriterier)
		- [Testkriterier før normering](#testkriterier-f%C3%B8r-normering)
		- [KPIer etter normering](#kpier-etter-normering)

<!-- /MarkdownTOC -->

## Hypotese

### Normeringsgrad

Dette behovet skal dekkes av retningslinje eller veileder. Påbudt standard er mest sannsynlig ikke aktuelt, og vi kan vurdere å bruke anbefalt standard.

### Nivå

Praktisk veiledning til hvordan autentisitet kan ivaretas i systemer og prosesser. Ikke krav/spesifikasjoner på teknologisk nivå, men kanskje innhold i logisk informasjonsmodell.
<!-- Dette er fortsatt ganske uklart for oss, men det blir nok klarere etterhvert -->

### Målgruppe(r)

- Ansvarlige for dokumentasjonsforvaltning/arkiv hos arkivskaper
- De som gjør kravspesifisering i forbindelse med anskaffelse/utvikling av systemer som behandler dokumentasjon
- Forretningsressurser hos systemutviklere

### Innhold

* Når er denne standarden nyttig?
	* Hva er autentisitet (i kontekst arkiv/dokumentasjonsforvaltning)?
	* Hvorfor standardisert tilnærming til autentisitet? Brukerhistorier - eksempler
	* Mål: Autentisitet som opplevd kvalitet ved dokumentasjon
		* Verdi - for forretning / for langtidsperspektiv
* Kontekst
	* Relaterte egenskaper - sammenheng som gir autentisitet større verdi
	* Forholdet til lovverk - hvilke krav er standarden til hjelp med å dekke
* Rammer
	* Risiko- og verdivurdering (vurdering av behov for autentisitet og sammenhengen med andre verdier)
	* Roller og ansvar
* Hvordan etablere og opprettholde autentisitet
	* Oversikt over løsninger og overganger
	    * Forslag til måter å gå frem på
	    * Eksempler på løsninger og overganger
	* Autentisitet etablere (fra utarbeidet til ferdigstilt)?
		* Prosessmetadata
	* Autentisitet opprettholde i tid (innen en løsning - forretningsmessig bruk)
		* Informasjonssikkerhet
		* Autentisitet for filer vs. autentisitet for metadata - jf. frysing
	* Autentisitet opprettholde gjennom teknologiskifter (transformasjoner og overføringer)
		* Teknologiske overganger
		* Endringslogging
		* Ivaretakelse av metadata
		* Autorisert/uatorisert endring	
* Hvordan bevise, vurdere og verifisere autentisitet
	* Hvordan vurdere autentisitet for dokumentasjon
	* Autentisitetsstøttende metadata (for digitalt skapt dokumentasjon)
	* Endringslogging

### Begrep

Egen fil: [autentisitetsstøtte-begrep.md](autentisitetsstøtte-begrep.md)

### Åpne spørsmål

* Hva er omfanget av autentisitet for StdLab?

#### Begrensninger
<!-- Dette kapittelet vil nok fjernes på et tidspunkt -->

* Overgang fra løsninger hvor informasjonen er blitt skapt til løsninger hvor den skal tas vare på på lang sikt er ikke sett på som noe spesielt overgang. Det tolkes på samme måte som overgang mellom de forskjellige løsningene hvor informasjonen skapes og brukes
* Det som skjer før et dokument er utarbeidet/fanget er ikke noe vi vil forsøke å standardisere

---

## Rammer

### Målet med normeringsprodukt

> Vi skriver "standard" her, men mener "normeringsprodukt"

Ønsket resultat av standard:

* Lesere vet hvor de har behov for autentisitet av dokumentasjon i sitt arbeid, også når den strekker seg over tid
* Lesere kan beskrive hva de skal gjøre for å sikre autentisitet i sitt arbeid, også når den strekker seg over tid
* Lesere har en ideé om hvor de skal se etter mer informasjon for å sikre autentisitet i sitt arbeid
* _Lesere vet hvordan de skal gå frem for å gi tilbakemelding på standard_
* _Lesere vet hvor de skal gå om det er mer ifm bruk av standard de lurer på_
* Standard dekker alle tilfeller når autentisitet er relevant innen StdLabs virkeområde

### Gjenbrukskilder

- ISO 13008: Information and documentation — Digital records conversion and migration process
- ISO 15801: Document management — Electronically stored information — Recommendations for trustworthiness and reliability
- ISO 16175: Information and documentation — Processes and functional requirements for software for managing records
- ISO 18829: Document management — Assessing ECM/EDRM implementations — Trustworthiness
- ISO 23081: Information and documentation — Records management processes — Metadata for records
- ISO 15489: Information and documentation - Records management - Part 1: Concepts and principles
- EN 15898: Conservation of cultural heritage - Main general terms and definitions
- Decentralized Identifiers (DIDs) v1.0 - W3C Recommendation https://www.w3.org/TR/did-core/
- Use Cases and Requirements for Decentralized Identifiers -  W3C Working Group Note 17 March 2021 https://www.w3.org/TR/did-use-cases/


### Opprinnelig behovsbeskrivelse

[Issue #12: Autentisitetsstøtte](https://github.com/arkivverket/standardlab/issues/12)

### Oppdatert/utdypet målbeskrivelse

**Overordnet verdi:** Tillit til informasjonen (autentisitet er en egenskap ved informasjon som vi skal ha tillit til)

**Grunnleggende behov:** Kjenne informasjonens opphav / vite at et informasjonsobjekt (dokument) er hva det gir seg ut for å være

**Tilnærming:** Standardisering av;

1. hvordan autentisitet skal forstås (mål og begrep), 
2. hvordan det skal ivaretas (metoder) og 
3. hvordan det skal kunne bevises (system) 

… som til sammen beskriver hvordan man sørger for autentisitet i relevante prosesser og hvilke metadata informasjonen skal tilføres, på et vis som er uavhengig av format(er) og prosesser [^1]

### Oppdaterte/utdypede suksesskriterier

**Overordnet:** Brukeren av informasjonsobjektet har tillit til at objektet er hva det gir seg ut for å være

#### Testkriterier før normering

- SKAL: Beskrivelse av hva autentisitet er og hvorfor det er viktig er forståelig for relevante brukergrupper (mini-brukerundersøkelse)
- SKAL: Beskrivelse av hvordan autentisitet kan ivaretas i prosesser er forståelig for relevante brukergrupper (mini-brukerundersøkelse)
- SKAL: Metadata for støtte for autentisitet er tilstrekkelige som bevis (faglige vurderinger)
- BØR: Endringer fra dagens krav til metadata oppleves som velbegrunnet (mini-brukerundersøkelse)

#### KPIer etter normering

- Grad av konsensus/aksept av beskrivelser som beste praksis
- Antall løsninger som produserer ønskede metadata

----------

[^1]: Teknologiskifter behandles som en prosess i denne sammenhengen
