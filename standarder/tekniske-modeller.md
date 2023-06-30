# Tekniske modeller

[![Generic badge](https://img.shields.io/badge/Status-Kladd-red.svg)](https://shields.io/)

> Merk: Dette er kun på hypotese-stadiet. Vesentlige endringer kan forekomme.

## Innhold i dokumentet

<!-- MarkdownTOC -->

- [Om tekniske modeller og arbeid med de](#om-tekniske-modeller-og-arbeid-med-de)
- [En-til-en](#en-til-en)
- [Noe generalisert](#noe-generalisert)
- [Generalisert til det ytterste](#generalisert-til-det-ytterste)

<!-- /MarkdownTOC -->

## Om tekniske modeller og arbeid med de

Tekniske modeller viser hvordan det er mulig å gå frem for å tilpasse den semantiske modellen til bruk i et eller annet spesifikt tilfelle. Teknisk modell detaljerer videre semantisk modell, og gjør det mulig å oppnå faktisk interoperabilitet mellom løsninger som tar vare på dokumentasjon.

StandardLab-teamet har utarbeidet 3 eksempler på hvordan det er mulig å bygge opp teknisk modell uten å ha konkret tilfelle å forholde seg til. Følgende forutsetninger har vært tatt:

* Tekniske modeller baserer seg på semantisk modell som er beskrevet her: [infomodell-mvp.md](infomodell-mvp.md)
* Sammenheng mellom den semantiske og den tekniske modeller er innlysende. Det er ingen behov for støttemateriale som gjør kobling mellom klasser og egenskaper entydig
* Modell er formulert i [UML klassediagram](https://en.wikipedia.org/wiki/Unified_Modeling_Language) notasjon. En av modellene bruker OCL ([Object Constraint Language](https://en.wikipedia.org/wiki/Object_Constraint_Language))
* Norsk språk brukes i navn på både klasser og egenskaper
* Typestruktur tilsvarer et eller annet moderne objektorientert språk, uten å peke tydelig på noe konkret språk

## En-til-en

Denne modellen legger seg tettest inntil den semantiske modellen. Ingen av verktøy som er tilgjengelige for objektorientert modellering er brukte. Det er ganske lett å kjenne igjen klassene `Registrering` og `Aggregering` og begge støtteklassene.

Mengde piler i diagram er betydelig større enn for øvrige modeller, siden arv er ikke brukt. De fleste koblingene som kunne ha gått til både `Registrering` og `Aggregering` er blitt doblet opp.

Det er nødvendig til å bruke Object Constraint Language for å vise at selv om det er mulig at `Aggregering` inneholder ingen `Registrering` eller ingen `Aggregering`, er den nødt til å inneholde en forekomst av en av den ene eller andre.

Alt dette gjør modellen detaljert, og noe tung å vedlikeholde. Til gjengjeld er den enklest gjenkjennbar opp mot semantisk modell.

![Teknisk modell: En-til-en](/standarder/figurer/teknisk-modell-1.png)

## Noe generalisert

Bruk av [arv](https://en.wikipedia.org/wiki/Inheritance_(object-oriented_programming)) og [abstrakt klasse](https://en.wikipedia.org/wiki/Abstract_type) gir oss mulighet for å tegne et kortere og mer konsist diagram.

Støtteklassene (`InntruffetHendelse` og `PlanlagtHendelse`) abstraheres fremdeles ikke, og er sett på som 2 helt uavhengige klasser.

![Teknisk modell: Noe generalisert](/standarder/figurer/teknisk-modell-2.png)


## Generalisert til det ytterste

Det er også mulig å generalisere modellen videre ved å definere klassen som er felles stammor for alle andre klasser. Dette gjør modellen mer abstrakt, og innfører avhengigheter som er muligens ikke nødvendige. Eksempel på en er at egenskapen `type` med datatype `String` defineres på `Objekt`. Dette kan gjøre det vanskeligere å definere egne typer for `Aggregering`, `Registerering` og støtteklasser.


![Teknisk modell: Generalisert](/standarder/figurer/teknisk-modell-3.png)