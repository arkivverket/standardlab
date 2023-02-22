# Løsningshypotese – behovsgruppe informasjonsmodell og API

[![Generic badge](https://img.shields.io/badge/Status-Kladd-red.svg)](https://shields.io/)

> Merk: Dette er kun på hyptese-stadiet. Vesentlige endringer kan forekomme.

Det er lite sannsynlig at best egnede løsning på behovene beskrevet i GitHub som issue [#5](https://github.com/arkivverket/standardlab/issues/5), [#21](https://github.com/arkivverket/standardlab/issues/21) og [#45](https://github.com/arkivverket/standardlab/issues/45) er å lage ett sammenhengende produkt. Det er heller ikke antatt hensiktsmessig å lage ett produkt per behov. Vi ser derfor for oss å lage en pakke bestående av tre (eller fire) normerende produkter.

1. [Informasjonsmodell for dokumentasjonssystemer](#informasjonsmodell-for-dokumentasjonssystemer)
2. [Beste praksis for bruk av informasjonsmodell](#beste-praksis-for-bruk-av-informasjonsmodell)
3. [Beste praksis for grensesnitt for utveksling mellom dokumentasjonssystemer](#beste-praksis-for-grensesnitt-for-utveksling-mellom-dokumentasjonssystemer)
4. [Standardisert(e) grensesnitt og utvekslingsformat(er) for dokumentasjon](#informasjonsmodell-for-dokumentasjonssystemer)[^1]

På grunn av interne avhengigheter bør produkt 1 utvikles til en MVP (minste verdiskapende produkt) foreligger før vi går i gang med utvikling av øvrige produkter.

## Informasjonsmodell for dokumentasjonssystemer

Dette normerende produktet er antatt å bli en de facto obligatorisk standard for enkelte typer systemer (systemer som er lagd for å forvalte dokumentasjon/arkiv), og deler av produktet vil også kunne være en anbefalt standard for andre typer systemer. Gevinstene ved at informasjonsmodellen er lik på tvers av virksomheter og systemer er antatt å være så stor at etterlevelse ikke vil trenge å være de jure obligatorisk for at den skal følges. Gevinstene handler både om å lette utveksling mellom systemer og å forenkle for depotinstitusjoner.

For å ta hensyn til systemer og grensesnitt som allerede brukes, bør vi ta utgangspunkt i eksisterende informasjonsmodell ([Noark metadatakatalog](https://www.arkivverket.no/forvaltning-og-utvikling/noark-standarden/noark5-standarden/_/attachment/download/9f16ce02-80e7-48d4-b6ac-a01bcaa27858:e31d3dd2f0b988cda2d254d9e1f3004b668bca4c/Noark%205%20v%205%20vedl1%20Metadatakatalog.pdf)). Dette vil redusere sannsynlighet for uholdbart store investeringsbehov hos leverandører (både av felleskomponenter og av systemer) og forvaltningen.

Endringer som vil skje fra dagens situasjon vil i hovedsak falle i kategoriene[^2]:

- Obligatoriske / betinget obligatoriske elementer blir frivillige
- Uhensiktsmessige elementer blir fjernet
- Nye elementer blir lagt til
- Flere elementer får kodeverk (i dagens metadatakatalog omtalt som «obligatoriske verdier»)
- Tydeliggjøring av definisjoner, kilder mv.

Informasjonsmodellen vil fortsatt være på konseptuelt nivå. Vi skal så langt det er forsvarlig tilrettelegge for at informasjonsmodellen skal kunne uttrykkes i flere hensiktsmessige formater. Vi kan[^3] lage schema i ulike formater for hvordan vi ser for oss at datamodellen bør være som følge av informasjonsmodellen. Aktuelle formater er i så fall antatt å være JSON Schema og XML Schema (alternativt: Relax NG), og kanskje også RDF Schema/OWL (alternativt: SHACL).

Som del av arbeidet vil vi også vurdere om informasjonsmodellen kan/bør uttrykkes i tråd med [Spesifikasjon for beskrivelse av informasjonsmodeller (ModellDCAT-AP-NO)](https://data.norge.no/specification/modelldcat-ap-no). Dette vil i så fall kunne være med på å tilrettelegge for gjenbruk av elementer fra andre datamodeller inn i datamodeller bygget på vår informasjonsmodell.

Det vil også vurderes om de obligatoriske (og kanskje også betinget obligatoriske) elementene lar seg mappe mot [CITS ERMS](https://dilcis.eu/content-types/cserms) – en felleseuropeisk informasjonstypespesifikasjon for elektroniske dokumentasjonssystemer. Dette vil i så fall kunne åpne for at leverandører som har utviklet systemer i tråd med CITS ERMS enklere vil kunne tilby produkter til norsk forvaltning.

Produktet skal kunne brukes til å dekke følgende brukerhistorier:

- Som bestiller av dokumentasjonsløsning i forvaltningen ønsker jeg å bruke standarden som kilde til krav i kravspesifikasjon når jeg skal anskaffe (utvikling av) nytt system for å sørge at innkjøp oppfyller mine plikter
- Som bestiller av dokumentasjonsløsning i forvaltningen ønsker jeg å bruke standarden som kravsett når jeg skal anskaffe (utvikling av) nytt system for å bruke minst mulig tid på å lage egne krav[^4]
- Som systemansvarlig for dokumentasjonssystem i forvaltningen ønsker jeg å verifisere at krav (f.eks. regelverk) er ivaretatt når jeg skal utvikle / gjøre oppsett av løsning for å sikre at løsningen er egnet til at vi som organisasjon oppfyller våre plikter ved å bruke den
- Som systemansvarlig for dokumentasjonssystem i forvaltningen ønsker jeg å følge opp krav mot leverandør på en måte som gir felles forståelse av kravene når jeg skal utvikle / gjøre oppsett av løsning for å sikre at løsningen tilfredsstiller kravene
- Som leverandør av felleskomponent/fellesløsning ønsker jeg å sikre at krav (f.eks. regelverk) er ivaretatt når jeg skal (videre-)utvikle datamodell(er) som brukes i mitt system for å sikre at min løsning kan spille sammen med andre arkivløsninger
- Som leverandør av felleskomponent/fellesløsning ønsker jeg å oppnå/opprettholde interoperabilitet med systemer som følger standarden når jeg skal (videre-)utvikle datamodell(er) som brukes i mitt system for å sikre effektiv utveksling av dokumentasjon
- Som leverandør av felleskomponent/fellesløsning ønsker jeg å bruke informasjonsmodeller fra standarden når jeg skal (videre-)utvikle mitt produkt for å tilrettelegge for at dokumentasjon har god gjenfinnbarhet for sluttbrukere
- Som utvikler hos leverandør av dokumentasjonssystem ønsker jeg å ivareta sammenheng med modeller i standarden når jeg skal (videre-)utvikle intern datamodell for å verifisere at (minimums-)krav for å oppnå interoperabilitet med andre systemer og dekke faglige krav er ivaretatt

Produktet skal også bidra til å løse følgende brukerhistorier:

> Merk: Ikke alle brukerhistorier er absolutte krav for en første versjon av produktet.

- Som saksbehandler i forvaltningen ønsker jeg at (datamodellen til) systemet jeg skal bruke er designet slik at jeg kan kunne bruke søk i relevante metadatafelter når jeg skal søke i dokumentasjon for å kunne løse de daglige oppgavene mine som er avhengig av gjenfinning av informasjon
- Som saksbehandler i forvaltningen ønsker jeg at (datamodellen til) systemet jeg skal bruke er designet slik at jeg kan gjøre egnede avgrensinger av søk når jeg skal søke i dokumentasjon for å effektivt finne igjen dokumentasjon
- Som bestiller av dokumentasjonsløsning i forvaltningen ønsker jeg at det finnes sertifiseringsløsninger eller -ordninger slik at jeg kan verifisere at en tilbudt løsning er i tråd med standarden når jeg skal anskaffe (utvikling av) nytt system for å være sikker på at løsningen følger standarden
- Som bestiller av dokumentasjonsløsning i forvaltningen ønsker jeg at standarden stiller krav til systemer slik at jeg kan vite at løsningen jeg anskaffer kan "snakke med" tilsvarende løsninger hos andre virksomheter når jeg skal anskaffe (utvikling av) nytt system for å sikre at løsningen vil passe inn i virksomhetens løsningsarkitektur
- Som bestiller av dokumentasjonsløsning i forvaltningen ønsker jeg at standarden stiller krav til systemer slik at jeg kan vite at løsningen jeg anskaffer kan "snakke med" aktuelle felleskomponenter som brukes i og av forvaltningen når jeg skal anskaffe (utvikling av) nytt system for å sikre at løsningen vil passe inn i virksomhetens løsningsarkitektur
- Som bestiller av dokumentasjonsløsning i forvaltningen ønsker jeg at standarden stiller krav til systemer slik at jeg kan vite at løsningen jeg anskaffer sørger for at riktige metadata for å dekke (sentrale) faglige krav til arkiv er ivaretatt for informasjonsobjekter i løsningen når jeg skal anskaffe (utvikling av) nytt system for å sikre at løsningen er egnet til at vi som organisasjon oppfyller våre plikter ved å bruke den
- Som sluttbruker av arkiv ønsker jeg at systemene i offentlig sektor har funksjonalitet for og brukes slik at jeg kan finne relevant dokumentasjon for mitt søk når jeg skal søke i postlister og publisert dokumentasjon (på tvers av flere virksomheter) for å forstå forvaltningens handlinger gjennom dokumentasjon
- Som sluttbruker av arkiv ønsker jeg at systemene i offentlig sektor har funksjonalitet for og brukes slik at jeg kan se sammenhengen mellom dokumentasjon fra flere virksomheter når jeg skal søke i postlister og publisert dokumentasjon (på tvers av flere virksomheter) for å følge saksgangen på tvers av organer
- Som sluttbruker av arkiv ønsker jeg at registrering og overføring av dokumentasjon fungerer slik at jeg kan finne relevant dokumentasjon for mitt søk når jeg skal søke i dokumentasjon som er avlevert til depotinstitusjon for å forstå forvaltningens handlinger gjennom dokumentasjon
- Som leverandør av felleskomponent/fellesløsning ønsker jeg at det finnes sertifiseringsløsninger eller -ordninger slik at jeg kan bevise etterlevelse av standarden når jeg skal "selge" min løsning for å sikre kunder at det er mulig å utveksle dokumentasjon med løsningen og dokumentasjon er forsvarlig ivaretatt
- Som leverandør av felleskomponent/fellesløsning ønsker jeg at standarden inneholder formuleringer om mål og gevinster slik at jeg kan argumentere for verdien av etterlevelse av standarden når jeg skal "selge" min løsning for å sikre kunder at det er mulig å utveksle dokumentasjon med løsningen, og at dokumentasjon er forsvarlig ivaretatt
- Som selger hos leverandør av dokumentasjonssystem ønsker jeg at det finnes sertifiseringsløsninger eller -ordninger slik at jeg kan bevise etterlevelse av standarden når jeg skal selge min løsning for å overbevise kunder om kvalitet på min løsning
- Som selger hos leverandør av dokumentasjonssystem ønsker jeg at standarden inneholder formuleringer om mål og gevinster slik at jeg kan bruke etterlevelse av standarden som argumentasjon når jeg skal selge min løsning for å overbevise kunder om at de kommer å etterleve sine plikter med min løsning
- Som depotinstitusjon ønsker jeg at arkiv fra ulike men likeartete kilder (dokumentasjonssystem) skal kunne tilgjengeliggjøres på enklest mulig måte, uten for mange spesialtilpasninger per (kilde)system slik at jeg kan søke på tvers av flere datasett/uttrekk når jeg skal finne igjen dokumentasjon og lage sammenstillinger for å bruke minst mulig tid på oppgaven
- Som depotinstitusjon ønsker jeg at arkiv fra ulike men likeartete kilder (dokumentasjonssystem) skal kunne tilgjengeliggjøres på enklest mulig måte, uten for mange spesialtilpasninger per (kilde)system slik at jeg kan kjenne strukturen på avleveringen når jeg skal gjøre vedlikehold på avlevert dokumentasjon for å sikre at den ivaretas og at ingenting går tapt
- Som depotinstitusjon ønsker jeg at arkiv fra ulike men likeartete kilder (dokumentasjonssystem) har likest mulig struktur slik at jeg kan legge til grunn at strukturen er (relativt) lik på tvers av datasett/uttrekk når jeg skal gjøre vedlikehold på avlevert dokumentasjon for å automatisere vedlikeholdet mest mulig

## Beste praksis for bruk av informasjonsmodell

Dette normerende produktet er antatt å bli et sett retningslinjer eller veiledning. Det er antatt å være lite hensiktsmessig å stille obligatoriske krav hvordan informasjonsmodellen brukes. Så lenge systemene er i stand til å levere informasjon i tråd med informasjonsmodellen (og de kravene som er spesifisert i den), bør systemet kunne regnes som godt nok til at krav til bruk av informasjonsmodell er oppfylt[^5].

Eksempler på innhold i dette produktet kan være:

- Hvordan bør ulike felter være fylt ut for å lette gjenfinning (både innad i systemet og på tvers av flere systemer og virksomheter)
- Når er det hensiktsmessig å bruke ulike valgfrie felter
- Hvordan kan man supplere den standardiserte informasjonsmodellen med andre felter når dette er hensiktsmessig for virksomhetens/domenets egne behov
- Hvilke felter er det viktigst å ha et kvalitetssikringsregime for bruken av

Listen vil suppleres/justeres som følge av arbeidet med informasjonsmodellen.

Produktet skal kunne brukes til å dekke (eller i det minste gjøre det enklere å dekke) følgende brukerhistorier:

- Som systemansvarlig for dokumentasjonssystem i forvaltningen ønsker jeg å tilrettelegge systemet for automatisering når jeg skal utvikle / gjøre oppsett av løsning for å unngå unødvendig arbeidsbelastning på brukerne av systemet
- Som systemansvarlig for dokumentasjonssystem i forvaltningen ønsker jeg å gjøre tilpasninger av datamodellen når jeg skal utvikle / gjøre oppsett av løsning for å ha en løsning som er godt tilpasset til virksomhetens oppgaveløsing og informasjonsstrukturer
- Som saksbehandler i forvaltningen ønsker jeg at systemet jeg skal bruke er designet slik at jeg kan forholde meg til kun de metadatafeltene jeg må forholde meg til når jeg skal registrere et informasjonsobjekt i systemet for å slippe å ta stilling til (og registrere) felt jeg ikke ser verdien av at registreres
- Som systemansvarlig for dokumentasjonssystem i forvaltningen ønsker jeg at systemet har funksjonalitet slik at jeg kan definere interne regler (eller beste praksis) for bruk av systemet når jeg skal utvikle / gjøre oppsett av løsning for å sikre enhetlig bruk som gir søkbare resultater
- Som arkivfaglig fagperson i forvaltningen ønsker jeg at systemet har funksjonalitet slik at jeg kan kunne gjøre effektiv redigering av metadata når jeg skal gjøre kvalitetssikring av registreringer for å sikre at beste praksis er fulgt og at ekstern og intern gjenfinnbarhet er ivaretatt
- Som sluttbruker av arkiv ønsker jeg at nødvendige metadata finnes på registreringer slik at jeg kan være selvbetjent når jeg skal få partsinnsyn eller innsyn i personopplysninger for å effektivt få tilgang til dokumentasjonen og opplysninger

Listen vil suppleres/justeres som følge av arbeidet med informasjonsmodellen.

## Beste praksis for grensesnitt for utveksling mellom dokumentasjonssystemer

Dette normerende produktet er antatt å bli et sett retningslinjer eller veiledning. Enkelte anbefalinger i produktet vil likevel kunne være de facto obligatoriske, fordi det å ikke følge dem vil føre til at elementer som er obligatoriske i informasjonsmodellen går tapt eller at krav stilt som følge av standardisering av andre behov ikke er dekket.

Eksempler på innhold i dette produktet kan være:

- Anbefalte funksjonelle krav til hvordan utvekslingen skal skje
  - Ved utveksling av enkeltelementer
  - Ved utveksling av pakker av flere elementer
  - Ved utveksling av samlede arkiver (f.eks. ved systembytter eller overføring til depot)
- Beste praksis for hvordan grensesnitt bør være utformet, kanskje inkludert anbefalinger rundt teknologivalg
- Anbefalinger rundt allerede eksisterende grensesnitt og hvordan de kan være egnet for denne bruken

Listen vil suppleres/justeres som følge av arbeidet med produkt 1.

Produktet skal kunne brukes til å dekke (eller i det minste gjøre det enklere å dekke) følgende brukerhistorier:

- Som systemansvarlig for dokumentasjonssystem i forvaltningen ønsker jeg å tilrettelegge systemet for automatisering når jeg skal utvikle / gjøre oppsett av løsning for å unngå unødvendig arbeidsbelastning på brukerne av systemet
- Som saksbehandler i forvaltningen ønsker jeg at systemet jeg skal bruke er designet slik at jeg kan forholde meg til kun de metadatafeltene jeg må forholde meg til når jeg skal registrere et informasjonsobjekt i systemet for å slippe å ta stilling til (og registrere) felt jeg ikke ser verdien av at registreres
- Som bestiller av dokumentasjonsløsning i forvaltningen ønsker jeg at standarden stiller krav til systemer slik at jeg kan vite at løsningen jeg anskaffer kan snakke med andre, relevante løsninger i egen virksomhet når jeg skal anskaffe (utvikling av) nytt system for å sikre at løsningen vil passe inn i virksomhetens løsningsarkitektur
- Som sluttbruker av arkiv ønsker jeg at registrering og overføring av dokumentasjon fungerer slik at jeg kan stole på at arkivkvaliteten er sikret over tid når jeg skal søke i dokumentasjon som er avlevert til depotinstitusjon for å vite at jeg kan stole på dokumentasjonen (ha tillit til den)
- Som leverandør av felleskomponent/fellesløsning ønsker jeg å lage grensesnitt som følger standarden når jeg skal (videre-)utvikle mitt produkt for å oppnå effektiv utveksling av dokumentasjon mellom løsninger
- Som utvikler hos leverandør av dokumentasjonssystem ønsker jeg å følge standarden når jeg skal utvikle API-er inn og ut av systemet for å oppnå effektive integrasjoner mellom løsninger

Listen vil suppleres/justeres som følge av arbeidet med informasjonsmodellen.

## Standardisert(e) grensesnitt og utvekslingsformat(er) for dokumentasjon

Dersom det er behov for det, kan Arkivverket komme med et normerende produkt som sier noe om hvilke grensesnitt som skal/bør benyttes for utveksling av dokumentasjon. Dette vil enten kunne være utvikling av egne grensesnitt, eller at man peker på allerede eksisterende grensesnitt som forvaltes av andre og sier at det er disse som skal/bør benyttes. Eksempler på slike gjenbruksformater kan være [Arkivmelding](https://docs.digdir.no/docs/eFormidling/Utvikling/Dokumenttyper/standard_arkivmelding) fra eFormidling/Digitaliseringsdirektoratet og [FINT](https://www.fintlabs.no/#/)s felles API-er. Det kan også være relevant å peke på domenespesifikke standarder som for eksempel [Arkivlett](https://www.ks.no/fagomrader/digitalisering/felleslosninger/verktoykasse-plan--og-byggesak/verktoy/sammenhengende-tjenester---integrasjoner/arkivlett/) fra KS.

Det er ikke laget brukerhistorier som er tenkt dekket av dette produktet (ennå), men dette vil bli gjort hvis det avdekkes behov for denne typen produkt.

[^1]: Det er usikkert om StandardLab vil gjøre dette. Behov må i så fall verifiseres med sentrale målgrupper
[^2]: Listen er ikke ment å være uttømmende – andre endringer vil også kunne forekomme
[^3]: Det er usikkert om StandardLab vil gjøre dette. Behov må i så fall verifiseres med sentrale målgrupper
[^4]: Denne brukerhistorien er ikke et SKAL-krav, mer noe vi oppfatter som et ønske hos enkelte aktører
[^5]: Andre funksjonelle krav vil dog måtte oppfylles, som følge av at andre behov for standardisering blir dekket
