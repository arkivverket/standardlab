# Autentisitetsstøtte

[![Generic badge](https://img.shields.io/badge/Status-Kladd-red.svg)](https://shields.io/)

<!-- MarkdownTOC -->

- [Standard](#standard)
	- [Normeringsgrad](#normeringsgrad)
	- [Hypotese for videre arbeid](#hypotese-for-videre-arbeid)
	- [Åpne spørsmål](#%C3%A5pne-sp%C3%B8rsm%C3%A5l)
- [Rammer](#rammer)
	- [Gjenbrukskilder](#gjenbrukskilder)
	- [Opprinnelig behovsbeskrivelse](#opprinnelig-behovsbeskrivelse)
	- [Oppdatert/utdypet målbeskrivelse](#oppdatertutdypet-m%C3%A5lbeskrivelse)
	- [Oppdaterte/utdypede suksesskriterier](#oppdaterteutdypede-suksesskriterier)

<!-- /MarkdownTOC -->


## Standard

> Innhold er ennå ikke produsert. Det første som vil deles er vår hypotese til form på standard (inkludert en tidligversjon av disposisjon).

### Normeringsgrad

Dette behovet skal dekkes av retningslinje eller veileder. Påbudt standard er mest sannsynlig ikke aktuelt, og vi kan vurdere å bruke anbefalt standard.

### Hypotese for videre arbeid

#### Målet med normeringsprodukt

> Vi skriver "standard" her, men mener "normeringsprodukt"

Ønsket resultat av stanard:
* Lesere vet hvor de har behov for autentisitet av dokumentasjon i sitt arbeid
* Lesere kan beskrive hva de skal gjøre for å sikre autentisitet i sitt arbeid
* Lesere har en ideé om hvor de skal se etter mer informasjon for å sikre autentisitet i sitt arbeid
* Lesere vet hvordan de skal gå frem for å gi tilbakemelding på standard
* Lesere vet hvor de skal gå om det er mer ifm bruk av standard de lurer på
* Standard dekker alle tilfeller når autentisitet er relevant innen StdLabs virkeområde

#### Temaer som skal dekkes

* Når er denne standarden nyttig?
	* Brukerhistorier - eksempler
	* Autentisitet som opplved kvalitet ved dokumentasjon
	* Begrepene
	    * Observatør
	    * Dokumentasjon
	    * Løsning
* Sikre autentisitet
	* Oversikt over løsninger og overganger
	    * Perspektiv på oversikt
	    * Risikovurdering
	    * Forslag til måter å gå frem på
	    * Eksempler av beskrivelser av oversikt
	* Autentisitet innen en løsning
		* Informasjonssikkerhet
		* Teknologiske overganger
* Dra nytte av autentisitet
	* Autentisitet ved overføring mellom løsninger
		* Handlinger som krever overføring mellom løsninger
		* 

#### Begrep

* **Autentisitet**: tolkes som evne av dokumentasjon til å fremstå og fungere troverdig nok for sine formål
* **Dokumentasjon**: Informasjon som kan brukes som bevis for en handling
* **Løsning**: Sammensetning av tekniske systemer og organisatoriske enheter som er sett på som en helhet. En løsning reliserer som regel en eller flere tjenester innen en virksomhet.
* **Overgang mellom løsninger**: Prosess når dokumentasjon overføres mellom løsninger. Kan også bli sett på en hendelser. Hendelsene kan sendes på tvers av virksomheter.
* **Autentisitet i ro**: Ivaretagelse av autentisistet så lenge dokumentasjon befinner seg innen en løsning
* **Autentisitet i bevegelse**: Ivaretagelse av autentisitet når dokumentasjon overføres mellom løsninger
* **Observatør**: Fordeling i løsninger og overganger mellom de avhenger av hvilken rolle og ekspertise som utformer oversikt over virksomheters løsninger og overganger mellom de. Teknisk utvikler kommer å ha en annen perspektiv enn saksbehander eller leder i virsomheten

### Åpne spørsmål

* Hva er omfanget av autentisitet for StdLab?

#### Begrensninger

* Overgang fra løsninger hvor informasjonen er blitt skapt til løsninger hvor den skal tas vare på på lang sikt er ikke sett på som noe spesielt overgang. Det tolkes på samme måte som overgang mellom de forskjellige løsningene hvor informasjonen skapes og brukes


---

## Rammer

### Gjenbrukskilder

- ISO 13008: Information and documentation — Digital records conversion and migration process
- ISO 15801: Document management — Electronically stored information — Recommendations for trustworthiness and reliability
- ISO 16175: Information and documentation — Processes and functional requirements for software for managing records
- ISO 18829: Document management — Assessing ECM/EDRM implementations — Trustworthiness
- ISO 23081: Information and documentation — Records management processes — Metadata for records

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