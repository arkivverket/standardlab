# Autentisitetsstøtte

[![Generic badge](https://img.shields.io/badge/Status-Kladd-red.svg)](https://shields.io/)

<!-- MarkdownTOC -->

- [Standard](#standard)
	- [Normeringsgrad](#normeringsgrad)
	- [Nivå](#niv%C3%A5)
	- [Målgruppe\(r\)](#m%C3%A5lgrupper)
	- [Disposisjon/temaer som skal dekkes](#disposisjontemaer-som-skal-dekkes)
		- [Begrep](#begrep)
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


## Standard

> Dette er vår hypotese til form på standard (inkludert en tidligversjon av disposisjon). Den vil bli fylt med innhold fortløpende.

### Normeringsgrad

Dette behovet skal dekkes av retningslinje eller veileder. Påbudt standard er mest sannsynlig ikke aktuelt, og vi kan vurdere å bruke anbefalt standard.

### Nivå

Praktisk veiledning til hvordan autentisitet kan ivaretas i systemer og prosesser. Ikke krav/spesifikasjoner på teknologisk nivå, men kanskje innhold i logisk informasjonsmodell.
<!-- Dette er fortsatt ganske uklart for oss, men det blir nok klarere etterhvert -->

### Målgruppe(r)

- Ansvarlige for dokumentasjonsforvaltning/arkiv hos arkivskaper
- De som gjør kravspesifisering i forbindelse med anskaffelse/utvikling av systemer som behandler dokumentasjon
- Forretningsressurser hos systemutviklere

### Disposisjon/temaer som skal dekkes

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

#### Begrep

* **Autentisitet**: tolkes som evne av dokumentasjon til å fremstå og fungere troverdig nok for sine formål
* **Autentisitetsstøtte**: tba
* **Dokumentasjon**: Informasjon som kan brukes som bevis for en handling
* **Løsning**: Sammensetning av tekniske systemer og organisatoriske enheter som er sett på som en helhet. En løsning reliserer som regel en eller flere tjenester innen en virksomhet.
* **Overgang mellom løsninger**: Prosess når dokumentasjon overføres mellom løsninger. Kan også bli sett på en hendelser. Hendelsene kan sendes på tvers av virksomheter.
* **Autentisitet i ro**: Ivaretagelse av autentisistet så lenge dokumentasjon befinner seg innen en løsning
* **Autentisitet i bevegelse**: Ivaretagelse av autentisitet når dokumentasjon overføres mellom løsninger
* **Observatør**: Fordeling i løsninger og overganger mellom de avhenger av hvilken rolle og ekspertise som utformer oversikt over virksomheters løsninger og overganger mellom de. Teknisk utvikler kommer å ha en annen perspektiv enn saksbehander eller leder i virsomheten

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
