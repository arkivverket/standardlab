# Minimumsmodell – eksempler på bruk

<!-- MarkdownTOC -->

- [Eksempel: Bompenger](#eksempel-bompenger)
	- [Variant 1: Dokumentbasert innhold](#variant-1-dokumentbasert-innhold)
	- [Variant 2: Strukturert innhold](#variant-2-strukturert-innhold)
- [Eksempel: Sensordata med verdi over tid](#eksempel-sensordata-med-verdi-over-tid)
- [Eksempel: Dokumentasjon fra en prosess - Gjennomføre skriftlig eksamen](#eksempel-dokumentasjon-fra-en-prosess---gjennomf%C3%B8re-skriftlig-eksamen)
- [Eksempel: Bruk ved anskaffelse](#eksempel-bruk-ved-anskaffelse)
- [Eksempel: Leverandør av løsningen for skoleskyss](#eksempel-leverand%C3%B8r-av-l%C3%B8sningen-for-skoleskyss)
	- [Om eksempelet](#om-eksempelet)
	- [Kort om løsningen](#kort-om-l%C3%B8sningen)
	- [Arkivplikten](#arkivplikten)
	- [Kommunikasjon med foresatte](#kommunikasjon-med-foresatte)
	- [Registrering](#registrering)
	- [Aggregering](#aggregering)

<!-- /MarkdownTOC -->


## Eksempel: Bompenger

For å illustrere hvordan modellen kan brukes, har vi laget et tenkt eksempel på hvordan den kan brukes i et system som håndterer bompasseringer. Begge eksempler bygger på følgende scenario:

- Bompengeinnkrevingen skjer ved registrering av passering bomstasjon. Det samles opp passeringer i en periode og man får samlefaktura for dette.
- Bompengeselskapet har forvaltningsmessig behov for å ivareta grunnegenskaper ved dokumentasjonen (APIA) som skapes i denne prosessen over en viss tid.
- De tar i bruk minimumsmodellen

### Variant 1: Dokumentbasert innhold

- Ved hver bompassering tas det et bilde av bilen som passerer
- I dokumentasjonssystemet opprettes det en registrering for hver passering, som har bildet som informasjonsinnhold
- Historikken for registreringen inneholder informasjon om når passeringen skjedde (=tidspunkt for en inntruffet hendelse av typen «opprettelse») og (indirekte) hvor det skjedde (=utfører for opprettelsen, dvs. kameraet som registrerte)
- Systemet oppretter også en aggregering for passeringer for den enkelte bil for faktureringsperioden
- Hver gang bilen passerer lages det ny registrering som har aggregeringen som «forelder»
- Ved fakturering lages det en registrering med aggregeringen som forelder. Denne inneholder fakturaen som pdf som dokumentinnhold. Bompengeselskapet har valgt å ha registreringstypen «faktura» for enklere å finne igjen alle fakturaer

### Variant 2: Strukturert innhold

- Ved hver bompassering leses data fra autopass-brikken til bilen som passerer av en sensor
- I dokumentasjonssystemet opprettes det en registrering for hver passering, som har data om passeringen som informasjonsinnhold
- Historikken for registreringen inneholder informasjon om når passeringen skjedde (=tidspunkt for en inntruffet hendelse av typen «opprettelse») og hvordan det skjedde (=utfører for opprettelsen, dvs. systemet som registrerte)
- Systemet oppretter også en aggregering for passeringer for den enkelte bil for faktureringsperioden
- Hver gang bilen passerer lages det ny registrering som har aggregeringen som «forelder»
- Ved fakturering lages det en registrering med aggregeringen som forelder. Denne inneholder fakturaen som strukturerte data som dokumentinnhold. Bompengeselskapet har valgt å ha registreringstypen «faktura» for enklere å finne igjen alle fakturaer

## Eksempel: Sensordata med verdi over tid

Dette hypotetiske eksempelet viser hvordan data i en database som ikke følger modellen kan avbildes mot modellen. Utgangspunktet er et scenario der det er plassert ut sensorer som måler f.eks. vannivå og vanntemperatur i vassdrag. Disse sensorene rapporterer jevnlig inn i et system som tar vare på opplysningene. Opplysningene brukes blant annet til å observere endringer over tid i de ulike verdiene. NVE som eier av systemet ønsker å sikre autentisitet, integritet og pålitelighet for måledataene, og tilpasser systemet til å dekke minimumsmodellen

Hver innrapporterte måling kan regnes som en registrering i systemet. Systemet lagrer data i en database med feltene:

- MålingID
- Sensor
- Tidspunkt
- Vannnivå
- Vanntemperatur

Dette kan avbildes til klassen `registrering` i minimumsmodellen slik:

- `MålingID` er egnet som `identifikator` for registreringen.
- `Tittel` for registreringen finnes ikke i systemet, men kan lages automatisk på formatet «Måling for `sensor` – `tidspunkt`»
- Måledataene er `informasjonsinnhold` i registreringen(e)
- Hvis ønskelig kan `type` benyttes til å skille ulike data  
Istedenfor en registrering med `informasjonsinnhold` om både vannivå og vanntemperatur, kan det opprettes en registrering av type «vannivå» og en annen registrering av type «vanntemperatur». I et slikt tilfelle kan tittel også berikes med informasjon om typen registrering - f.eks på formatet "Måling av `type` for `sensor` - `tidspunkt`»
- De intrufne hendelsene som ligger i `historikk` kan få `identifikator` opprettet automatisk. Den vanligste `Type` for intrufne hendelser vil være «opprettet», `tidspunkt` er navngitt likt i databasen og `utfører` av hendelsen er `sensor` i databasen.

Det kan opprettes en `aggregering` når det er fornuftig med en sammenstilling av flere registreringer. Et eksempel på en slik aggregering kan være «Målinger av vannivå under vårflommen i Numedalslågen 2022». Den kan se slik ut:

- Alle registreringer av typen «vannivå», for sensorer i Numedalslågen og tidspunkt for opprettet er innenfor relevant periode gjøres til barn av aggregeringen – f.eks. gjennom en automatisert regel
- `Identifikator` tildeles automatisk
- `Tittel` settes manuelt
- `Historikk` dokumenterer hvem som opprettet sammenstillingen (som egenskapen `utfører`) og når (som egenskapen `tidspunkt`)

En slik aggregering gir lettere tilgang til informasjon om den spesifikke flommen. Aggregeringen kan ha `type` «rapport om flom», slik at det er lettere å finne igjen informasjon om flere flommer.

## Eksempel: Dokumentasjon fra en prosess - Gjennomføre skriftlig eksamen

Dette eksempelet viser hvordan man kan bruke minimumsmodellen til å dokumentere prosesser som skaper dokumentasjon. Utgangspunktet er et scenario der man skal ta vare på dokumentasjonen som skapes ved å gjennomføre skriftlig eksamen på en videregående skole. Dette er en strukturert prosess som skaper dokumentasjon av både kortvarig og langvarig dokumentasjonsverdi. Skolen som eier systemet har behov for å sikre autentisitet, integritet og pålitelighet for dokumentasjonen, og tilpasser systemet til å dekke minimumsmodellen. 

Skolen har behov for å dokumentere flere aktiviteter som sammenlagt utgjør hele prosessen med å gjennomføre skriftlig eksamen. Alle aktivitetene registreres i systemet manuelt. For hver registrering må alle de obligatoriske egenskapene for en registrering være med, herunder `identifikator`, `tittel` og `historikk`. Det vil i tillegg være behov for å registrere følgende egenskaper og støtteklasser for de ulike aktivitetene. Det lages en aggregering for hver samlede eksamensgjennomføring: 

Lærestedet tilgjengeliggjør en oppgave som elevene skal svare på innen en frist

- Oppgavetekst med informasjon om formaliteter `innholdsinformasjon`
- Tidspunkt for tilgjengeliggjøring `inntruffet hendelse`
- Frist for innlevering `planlagt hendelse` på aggregeringen

Elevene leverer besvarelse for vurdering

- Oppgavebesvarelse `innholdsinformasjon`
- Tidspunkt for innlevering, og hvem som leverte `inntruffet hendelse`

Vurdering av innlevering er et vedtak som kan påklages – fastsettelse av karakter

- Karakter `innholdsinformasjon` 
- Tidspunkt for kunngjøring av vurdering `inntruffet hendelse`
- Frist for klage `planlagt hendelse` på aggregeringen

Klage på karakter

- Klage `innholdsinformasjon` 
- Tidspunkt for levering av klage `inntruffet hendelse`
- Behandlingsfrist `planlagt hendelse` på aggregeringen

Endelig fastsettelse av karakter

- Vedtak `innholdsinformasjon` 
- Tidspunkt `inntruffet hendelse`

Felles for all registreringene er at de er del av en dokumentasjonsprosess der dokumentfangst er en `inntruffet hendelse`, bevaringstid (overføring eller kassering) er en `planlagt hendelse` og overføring eller kassasjon er en `inntruffet hendelse`. 

Alle registreringene kan inngå i flere ulike aggregeringer samtidig. Aggregeringene kan være permanente eller midlertidige. 

Permanente aggregeringer kan for eksempel være:

- Samlet eksamensgjennomføring for alle elever samlet
- Samlet eksamensgjennomføring per elev

Midlertidige aggregeringer (som ikke registreres i systemet) kan for eksempel være: 

- Et enkelt søkeresultat som utføres etter behov, der aggregeringen opphører når søkeresultatet lukkes i systemet.

## Eksempel: Bruk ved anskaffelse

Eksempelet viser hvordan minimumsmodellen kan være svar på brukstilfellet _«Som bestiller av dokumentasjonsløsning i forvaltningen ønsker jeg at standarden stiller krav til systemer slik at jeg kan vite at løsningen jeg anskaffer sørger for at riktige metadata for å dekke (sentrale) faglige krav til arkiv er ivaretatt for informasjonsobjekter i løsningen når jeg skal anskaffe (utvikling av) nytt system for å sikre at løsningen er egnet til at vi som organisasjon oppfyller våre plikter ved å bruke den»_

> **⚠️ Merk:** Eksempelet under vil kunne falle inn under journalpliktig dokumentasjon. I et slikt tilfelle vil det etter gjeldende lovverk ikke være anledning til å bruke minimumsmodellen, siden Noark vil være pålagt standard. Minimumsmodellen er ikke ment å være utfyllende for alle metadata som er relevant i en offentlig journal.

Gran kommune har besluttet å anskaffe et nytt system for strømlinjeforming av prosessen med å gjennomføre høringer. Kommunen ønsker å sikre at de ivaretar autentisitet, pålitelighet, integritet og anvendbarhet for informasjonen som deles og samles inn i dette systemet, og vil bruke minimumsmodellen som et verktøy for å sikre dette.

De vurderer at ivaretakelse av både aggregeringer (samlinger av svar knyttet til en bestemt høring) og registreringer (det enkelte høringssvar) er nyttig i systemet som skal anskaffes. De gjør deretter en vurdering av hvilke av de ikke-obligatoriske egenskapene som er relevant for systemet, og kommer fram til at de fleste er relevant, men at de ikke har behov for `relasjoner`. De vurderer også hvor viktig de ulike egenskapene er, og kommer fran til at støtte for `planlagte hendelser` anses som mindre viktig enn øvrige egenskaper, siden dette kan håndteres manuelt ved overgang til et nytt system eller til langtidsbevaring.

De ser også at det er relevant å stille noen krav til hvordan modellen brukes, for eksempel til format på informasjonsinnhold og hvordan man holder oversikt over hvem som har sendt inn hvilke svar.  

Som følge av denne vurderingen stiller de følgende krav i kravspesifikasjonen for anskaffelsen, **i tillegg til** kravene de ellers ville ha stilt til systemet:

> **⚠️ Merk:** Kravene under er kun ment som illustrasjon, ikke et forslag til kravspesifikasjon.

1. Systemet skal håndtere registreringer og aggregeringer, jf. minimumsmodell for metadata i dokumentasjonssystemer
2. Datamodellen til systemet skal inneholde metadata som dekker alle obligatoriske egenskaper, samt egenskapene type og informasjonsinnhold, jf. minimumsmodell for metadata i dokumentasjonssystemer, på et vis som etterlever funksjonelle krav i samme modell
3. Datamodellen til systemet bør inneholde metadata som dekker egenskapen planlagte hendelser, jf. minimumsmodell for metadata i dokumentasjonssystemer, på et vis som etterlever funksjonelle krav i samme modell
4. Systemet skal støtte at både strukturerte data (fra et nettskjema) og filer (mottatt på e-post eller som vedlegg til nettskjema) skal kunne angis som informasjonsinnhold i registreringer ved utveksling og uttrekk av informasjon.
5. For alle svar på en høring skal den (personen eller organisasjonen) som sendte svaret være registrert i datamodellen, slik at det kan regnes som utfører på den intrufne hendelsen «opprettet» i historikken

For å kunne vurdere hvor godt kravene er dekket, ber de om vurderingsgrunnlag.

- Til krav 1 ber kommunen om beskrivelse av hvordan klasser i systemet tilsvarer klasser i modellen.
- Til krav 2 og 3 ber kommunen om en mappingtabell mellom datafelter i systemets datamodell og egenskapene i minimumsmodellen, samt en beskrivelse av hvordan de funksjonelle kravene til egenskapene ivaretas.
- Til krav 4 ber kommunen om eksempel på utvekslingsformat for data fra systemet som viser hvordan ulike typer informasjonsinnhold håndteres.
- Til krav 5 trenger ikke kommunen utdypelse utover en bekreftelse på at kravet er dekket. 

På denne måten sikrer kommunen at riktige metadata blir ivaretatt, og at sentrale funksjonelle krav er dekket – samt at dette kan verifiseres mer enn bare å være en lovnad fra potensielle leverandører.

## Eksempel: Leverandør av løsningen for skoleskyss

### Om eksempelet

Dette eksemplet viser hvordan en leverandør av løsninger for bl.a. offentlige virksomheter kan bruke minimum informasjonsmodell for å sikre at det er lett å vise til sine nåværende og fremtidige kunder at løsninger ivaretar arkivplikten etter den nye arkivloven. Minimumsmodellen kan også brukes for enklere utveksling av opplysninger mellom løsninger. 

### Kort om løsningen

«Storevik Software» jobber med løsninger for å holde oversikt over aktuelle og mulige brukere, og å holde kontakt med dem ([Kunderelasjonshåndtering](https://no.wikipedia.org/wiki/Kunderelasjonsh%C3%A5ndtering)). En av deres løsninger heter «KvikkKontakt» og leveres som en tjeneste i sky. KvikkKontakt selges til både offentlige og private virksomheter, og har en tilpasning for kommunale behov. Storevik Software valgte å spisse KvikkKontakt for skoleskyss i fylkeskommunene. Løsningen skal sikre at kommunikasjon om skoleskyss mellom ansatte i fylkeskommunen og disse aktørene skulle flyte lett og effektivt: 

* Elever 
    * Barn 
    * Barns foresatte 
* Skoler 
    * Skolens administrasjons 
    * Kontaktlærere til elever 
* Leverandører av skysstjenester 
    * Sjåfører 
    * Planleggere av trafikk  

### Arkivplikten 

Storevik Software vurderte at det kun er deler av denne løsningen kommer å være underlagt arkivplikten, og det var delene som dekket kommunikasjon med skoler og leverandører av skysstjenesten. 

Leverandøren ønsker at kundenes behov i størst mulig grad skal ivaretas av deres løsninger, og de har verken arkivmodul i dag eller planer om å utvikle en. Derfor vil de utvikle KvikkKontakt slik at arkivplikten ivaretas i løsningen, eller ved å bruke arkivløsning kunden disponerer i dag. 

Leverandør bygger løsningen i henhold til minimums informasjonsmodell for å sørge at KvikkKontakt ivaretar arkivplikten. 

### Kommunikasjon med foresatte 

Vi skal gå dypere i kommunikasjon mellom ansatte hos fylkeskommunen og barns foresatte for å illustrere hvordan arkivplikten ivaretas i der. Arkivplikten ivaretas på lignende måte i andre typer kommunikasjon.  

De viktigste informasjonselementene ved kommunikasjon mellom ansatte i fylkeskommune er modeller for aktører og meldinger (vi velger å følge UML klassediagram-notasjon her), som vises under. 

![Aktør modellen](/standarder/figurer/leverandoer-fig-1.png)

*Fig. 1: Aktørmodellen i KvikkKontakt*

Det er mulig å sende tekstmeldinger og beskjeder om at en elev trenger ikke skyss (melding om fravær). Det er kun mulig å ha én avsender og én mottaker per melding. Dette gjenspeiles i informasjonsmodellen for meldinger. 

![Meldingsmodell i KvikkKontakt](/standarder/figurer/leverandoer-fig-2.png)

*Fig. 2: Meldingsmodell i KvikkKontakt*

Siden minimumsinformasjonsmodell fra Arkivverket er utformet som en semantisk modell, er det mulig å definere koblinger fra KvikkKontakt sine modeller til minimumsmodellen. 

### Registrering 

Storevik Software bestemmer at både vanlig tekstmelding og melding om fravær skal være registreringen i minimumsmodellen. Alle meldinger som er knyttet til foresatt og elev skal være aggregeringer. Her er komplett oversikt over egenskaper ved tekstmelding og melding om fravær. 

![Egenskaper ved meldinger](/standarder/figurer/leverandoer-fig-3.png)

*Fig. 3: Egenskaper ved meldinger*

Storevik Software definerer kobling mellom de aktuelle meldingstypene og registrering på en slik måte. 

![Kobling mellom melding om fravær og registrering](/standarder/figurer/leverandoer-fig-4.png)

*Fig. 4: Kobling mellom melding om fravær og registrering*

Det er ganske innlysende hvordan identifikator, tittel og informasjonsinnhold i Registrering ble hentet fra meldingen om fravær. Egenskapen «type» i Registreringen tas fra typen av meldingen. I dette tilfelle defineres alle meldinger med egenskap type «Leave». Historikk av en melding beskrives på følgende måte: 

* **Opprettelse**
    * Hendelse av type «Opprettelse» skapes basert på verdi i egenskap «`created`» på Leave. 
    * Identifikator skapes automatisk 
    * Tittel fylles ut som «Opprettelse av melding om fravær fra `<sender>` til `<receiver>` den `<created>`» 
    * Tidspunkt settes på verdi av `created` egenskap på `Leave`
    * Utfører settes til verdi av egenskap `creator` på `Leave`
 * **Utsending**
    * Hendelse av type «Utsending» skapes basert på verdi i egenskap «`sent`» på `Leave`.
    * Identifikator skapes automatisk 
    * Tittel fylles ut som «Utsending av melding om fravær fra `<sender>` til `<receiver>` den `<sent>`» 
    * Tidspunkt settes på verdi av `sent` egenskap på `Leave`
* **Lest**
    * Hendelse av type «Lest» skapes basert på verdi i egenskap «`read`» på Leave. 
    * Identifikator skapes automatisk 
    * Tittel fylles ut som «Melding om fravær fra `<sender>` til `<receiver>` har vært lest den `<read>`» 
    * Tidspunkt settes på verdi av `read` egenskap på `Leave`

### Aggregering 

Det er flere typer aggregeringer, hvor en av de er alle meldinger sendt fra en bestemt foresatt. Det er da relevant å være bevisst på hvilke egenskaper foresatt og elev har i KvikkKontakt.

![Egenskaper ved elever og foresatte](/standarder/figurer/leverandoer-fig-5.png)

*Fig. 5: Egenskaper ved elever og foresatte*

Det er en kobling fra foresatte til elever som viser hvem er vedkommende er foresatt for.

Det er viktig å legge merke til at selve objekt av type Foresatt ikke har noen opprettelsesdato, og minimumsmodell krever at Aggregering skal ha en Hendelse av type Opprettet. Vi løser dette ved å presisere at aggregering er en samling av meldinger som er blitt sendt eller mottatt av en foresatt. Denne aggregeringen representerer ikke selve foresatt, men meldingen til foresatt. Vi går mer i detalj på dette senere. 

Overordnet struktur for aggregering for alle meldinger for en bestemt foresatt kan se slik ut. 

![Aggregering av meldinger for en foresatt](/standarder/figurer/leverandoer-fig-6.png)

*Fig. 6: Aggregering av meldinger for en foresatt*

Egenskapene ved aggregering er blitt fylt ut på følgende måte: 

 * Identifikator baserer seg på id til foresatt. Den følger mønster «`messages-<id>`» 
 * Tittel følger mønster «Alle meldinger for foresatt `<title>`» 
 * Type er satt til «Meldinger til foresatt» 
 * Historikk inneholder 1 hendelse av opprettelse av aggregering. Det skapes basert på de aktuelle meldingene som er koblet til foresatt. Vi tar det første tidspunktet `created` for alle meldinger som hører hjemme under foresatt og definerer dette som opprettelsestidspunktet for aggregering 
 * Verdi av feltet «inneholder» er fylt med referanser til registreringer som representerer meldinger som hører hjemme under den aktuelle foresatt. Det er viktig å huske at her peker vi på registreringer, og ikke på selve meldingene. 
