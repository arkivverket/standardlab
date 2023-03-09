# Minimumsmodell – informasjonsmodell for dokumentasjonssystemer

[![Generic badge](https://img.shields.io/badge/Status-Kladd-red.svg)](https://shields.io/)

> Merk: Dette er kun på hypotese-stadiet. Vesentlige endringer kan forekomme.

Denne modellen er ment å være MVP for informasjonsmodell for dokumentasjonssystemer.

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
- Sørger for at **nødvendige** egenskaper for at objekter skal regnes som dokumentasjon (ref. Arkivfaglige hensyn i forslag til ny Arkivlov (§4) / karakteristikker fra ISO 15489 kap 5.2.2 - APIA) er på plass
- Peker på de konkrete metadataene som er **nødvendige** for at en skal kunne fastslå at egenskapene er ivaretatt

## Tilnærming

- Vi starter fra grunnen med å definere metadatabehovene
- ISO 23081-2 vil benyttes som første kilde til hvilke typer metadata som er nødvendig
- Implementeringer av denne standarden (inkl. Noark metadatakatalog) vil brukes som inspirasjon til hvordan behovet kan løses i praksis
