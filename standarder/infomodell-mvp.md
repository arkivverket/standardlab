# Minimumsmodell – informasjonsmodell for dokumentasjonssystemer

[![Generic badge](https://img.shields.io/badge/Status-Kladd-red.svg)](https://shields.io/)

> Merk: Dette er kun på hypotese-stadiet. Vesentlige endringer kan forekomme.

Denne modellen er ment å være MVP for [informasjonsmodell for dokumentasjonssystemer](infomodell-api.md#informasjonsmodell-for-dokumentasjonssystemer).

## Hvorfor minimumsmodell?

Vi så tidlig at det å dekke hele behovet for å utvikle informasjonsmodell for dokumentasjonssystemer ville bli for stort til at det var egnet å løse hele behovet med en gang. Derfor tar vi i bruk en smidig tilnærming ved å levere biter som kan deles fortløpende slik at flere kan gi tilbakemelding på det vi tenker, og gi verdi fort. Samtidig får vi da bygd erfaring på å jobbe med informasjonsmodellen(e), og en bedre forståelse for totalbehovet. En mindre omfattende modell er også antatt å være enklere å vedlikeholde og tilpasse eventuelle endrede behov enn det en større modell vil være.

En slik minimumsmodell må finne riktig balanse mellom behovet for å kunne avgrense nok (slik at det ikke blir for omfattende) og behovet for å ikke avgrense for mye (slik at man lager noe som kan brukes).

### Hvordan har vi avgrenset oss?

Grunnleggende kan man se for seg to ulike tilnærminger til hvordan man kan komme fram til en verdigivende delmengde av den fullstendige informasjonsmodellen:

- **Funksjonsbasert inndeling** – at man deler inn etter hva slags funksjonalitet som er relevant å ha informasjonsmodell for. Eksempelvis: Ivaretakelse av dokumentasjonsverdi / offentlig journal / saksflyt
- **Domenebasert inndeling** – at man deler inn etter hva slags ulike typer systemer som er relevant å ha informasjonsmodell for. Eksempelvis: Møtedokumentasjon / korrespondanse / register eller bygg / kjøretøy / helse

Vi har vurdert det til at det gir mer verdi totalt sett hvis vi legger funksjonsbasert tilnærming til grunn i første runde, og har derfor landet på en modell som ivaretar «noe» for alle dokumentasjonssystemer framfor noe som ivaretar alt for «noen» systemer.

### Hvorfor har vi ikke avgrenset oss mer?

For en funksjonsbasert inndeling vil det være logisk at den første modellen er en grunnmodell eller minimumsmodell. Begge vil være grunnlag som beskriver et minste felles multiplum av egenskaper det må finnes metadata for, og fungerer som grunnlag for ulike utvidelser. Forskjellen på disse modellene (slik vi tolker det) er at en minimumsmodell, i motsetning til en grunnmodell, må være omfattende nok til at den er tilstrekkelig til å dekke noen brukstilfeller. Det er derfor mer verdi i en minimumsmodell enn en grunnmodell.

En konsekvens av at dette skal være en minimumsmodell, ikke en grunnmodell, er at flere egenskaper må være del av modellen. I vår minimumsmodell er dette egenskaper som er betinget obligatoriske eller sterkt anbefalte for å kunne ivareta grunnegenskapene for dokumentasjon (autentisitet, pålitelighet, integritet og anvendbarhet - ref. ISO 15489 kap 5.2.2). Dette er også hovedargumentasjonen for at det er behov for to klasser (registering og aggregering), ikke bare én (dokumentasjonsobjekt).

## Bruksområde

Modellen skal brukes i dokumentasjonssystemer som brukes i offentlig sektor.

_Dokumentasjonssystemer_ er definert som "System som forvalter dokumentasjon over tid" (jf. ISO 30300)

_Dokumentasjon_ er definert som "informasjon som en organisasjon eller person produserer, mottar og vedlikeholder som bevis og som et aktivum, som et ledd i å oppfylle rettslige forpliktelser eller i en forretningstransaksjon" (jf. ISO 30300)

## Noen kjennetegn

- Minste felles multiplum – bør kunne brukes på alt som er dokumentasjon
- En konseptuell modell – stiller ikke krav til implementeringen så lenge nødvendige metadata finnes (og kan nyttiggjøres)
  - «Rike» objekter og relasjoner er begge gyldige måter å håndtere modellen på
  - Krav til implementeringen KAN komme som følge av pålagte grensesnitt, uttrekksformat mv.
- Ikke pålagt hierarki – men likevel støtte for at man kan (og bør?) lage aggregeringer av flere objekter
- Sørger for at **nødvendige** egenskaper for at objekter skal regnes som dokumentasjon (ref. Arkivfaglige hensyn i forslag til ny Arkivlov (§4) / grunnegenskaper for dokumentasjon) er på plass
- Peker på de konkrete metadataene som er **nødvendige** for at en skal kunne fastslå at egenskapene er ivaretatt

## Tilnærming

- Vi starter fra grunnen med å definere metadatabehovene
- ISO 23081-2 vil benyttes som første kilde til hvilke typer metadata som er nødvendig
- For å definere konkrete metadata prøver vi ut to ulike tilnærminger
  1.  Utgangspunkt i kjente metadatastandarder som er konkretiseringer av 23081-2 ([Nederlandske retninglinjer](https://www.nationaalarchief.nl/archiveren/kennisbank/metagegevens-0) og [Australsk standard](https://www.naa.gov.au/information-management/standards/australian-government-recordkeeping-metadata-standard))
  2.  Faglig diskusjon rundt hvilke metadata som er **nødvendige** og relasjon til mer omfattende standarder ([CITS ERMS](https://dilcis.eu/content-types/cserms) og [Noark](https://www.arkivverket.no/forvaltning-og-utvikling/noark-standarden/noark5-standarden))
- Sammenligning og sammenslåing av resultatet fra de to tilnærmingene.

### Hypotese på format / metamodell

Formatet vil ligne noe på Noark metadatakatalog objektsortert - det vil si at utgangspunktet er at det finnes ulike objekttyper/klasser, og for hver objekttype vil det være spesifisert hvilke egenskaper/metadata som skal/bør være definert for det enkelte objekt av typen. Vi ser for oss tre typer/klasser - registering/record (et generisk enkelt informasjonsobjekt), aggregering (en generisk samling av informasjonsobjekter) og hendelse (en beskrivelse av noe som har skjedd (potensielt også skal skje) med en record eller aggregering).

For hver egenskap vil følgende beskrives:

- Identifikator - stabil id for egenskapen - unik innen den gitte konteksten, lik på tvers av språk
- Tittel - navn på egenskapen - kan være ulik mellom språk
- Beskrivelse - utfyllende forklaring på hva egenskapen er - ikke obligatorisk, kan være ulik mellom språk
- Tilsvarende hos andre - mapping til hvordan tilsvarende egenskaper er navngitt/identifisert i andre standarder
- Relasjon til grunnleggende egenskaper - hvordan egenskapen bidrar til APIA
  - Autentisitet
  - Anvendbarhet
  - Pålitelighet
  - Integritet
- Begrunnelse - beskrivelse av hvorfor egenskapen trenger være del av minimumsmodellen

## Klasser og egenskaper

Som nevnt over er det to klasser for dokumentasjonsobjekter - aggregering og registrering. Sammenhengen mellom dem kan illustreres slik:

![Dokumentasjonsobjekter i minimumsmodellen: Aggregering peker på seg selv og på registrering](/standarder/figurer/infomodell-mvp-dokumentasjonsobjekter.png)

**Registrering** er et enkelt informasjonselement som ikke har kobling "nedover". Det er tenkt som "atom" av informasjon. Hva det i praksis er avhenger av oppgaven som løsningen ivaretar.  
**Aggregering** er en samling av registreringer og andre aggregeringer. Aggregeringer skal alltid ha kobling(er) til andre (underliggende) objekter.Det kan variere veldig hva en aggregering er avhengig av hvilke oppgaver som løses.

For både registreringer og aggregeringer har vi støtteklasser for hendelser og planlagte hendelser. Sammenhengen kan illustreres slik:

![Klasser i minimumsmodellen: Aggregering og registrering peker på hendelse og planlagt hendelse](/standarder/figurer/infomodell-mvp-klasser.png)

**Hendelse** er del av endringshistorikk på registrering og aggregering. Det er hendelse eller handling som har skjedd med registrering eller aggregering.Eksempel er opprettelse av registrering eller aggregering.  
**Planlagt hendelse** er hendelse eller handling som skal skje med registrering eller aggregering.Eksempel er kassasjon eller oppheving av skjermingshjemmel.

For hver klasse er det definert hvilke egenskaper det skal finnes metadata for på hvert objekt av klassen:

![Egenskaper i minimumsmodellen: Egenskaper som ligger på de ulike klassene er utlistet](/standarder/figurer/infomodell-mvp-egenskaper.png)

> **Lesehjelp:**  
> Fet: Gjennomtenkt  
> Kursiv: Tenking påbegynt  
> Asterisk: Obligatorisk på det enkelte objekt  
> NB! Alt fortsatt åpent for diskusjon
