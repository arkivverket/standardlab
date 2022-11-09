# Autentisitetsstøtte

[![Generic badge](https://img.shields.io/badge/Status-Kladd-red.svg)](https://shields.io/)

<!-- MarkdownTOC -->

- [Standard](#standard)
	- [Normeringsgrad](#normeringsgrad)
	- [Hypotese for løsning](#hypotese-for-l%25C3%25B8sning)
		- [Begrep](#begrep)
	- [Åpne spørsmål](#%25C3%25A5pne-sp%25C3%25B8rsm%25C3%25A5l)
		- [Begrensninger](#begrensninger)
- [Rammer](#rammer)
	- [Gjenbrukskilder](#gjenbrukskilder)
	- [Opprinnelig behovsbeskrivelse](#opprinnelig-behovsbeskrivelse)
	- [Oppdatert/utdypet målbeskrivelse](#oppdatertutdypet-m%25C3%25A5lbeskrivelse)
	- [Oppdaterte/utdypede suksesskriterier](#oppdaterteutdypede-suksesskriterier)
		- [Testkriterier før normering](#testkriterier-f%25C3%25B8r-normering)
		- [KPIer etter normering](#kpier-etter-normering)

<!-- /MarkdownTOC -->


## Standard

> Innhold er ennå ikke produsert. Det første som vil deles er vår hypotese til form på standard (inkludert en tidligversjon av disposisjon).

### Normeringsgrad

Dette behovet skal dekkes av retningslinje eller veileder. Påbudt standard er ikke aktuelt, og vi kan vurdere å bruke anbefalt standard.

### Hypotese for løsning

#### Begrep

* **Autentisitet**: tolkes som evne av dokumentasjon til å fremstå og fungere troverdig nok for sine formål
* **Dokumentasjon**: Informasjon som kan brukes som bevis for en handling
* **Løsning**: Sammensetning av tekniske systemer og organisatoriske enheter som er sett på som en helhet. En løsning reliserer som regel en eller flere tjenester innen en virksomhet.
* **Overgang mellom løsninger**: Prosess når dokumentasjon overføres mellom løsninger. Kan også bli sett på en hendelser. Hendelsene kan sendes på tvers av virksomheter.
* **Autentisitet i ro**: Ivaretagelse av autentisistet så lenge dokumentasjon befinner seg innen en løsning
* **Autentisitet i bevegelse**: Ivaretagelse av autentisitet når dokumentasjon overføres mellom løsninger
* **Observatør**: Fordeling i løsninger og overganger mellom de avhenger av hvilken rolle og ekspertise som utformer oversikt over virksomheters løsninger og overganger mellom de. Teknisk utvikler kommer å ha en annen perspektiv enn saksbehander eller leder i virsomheten

### Åpne spørsmål

* Hvor omfattende er behovet for autentisitet fra arkiv perspektiv? Dvs alt
* Hvordan behovet for 

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

[^1]: Teknologiskifter behandles som en prosess i denne sammenhengen
