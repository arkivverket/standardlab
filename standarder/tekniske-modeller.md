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

Tekniske modeller viser hvordan det er mulig å gå frem for å tilpasse den semantiske modellen til bruk i et eller annet konrekt tilfelle. Teknisk modell detaljerer videre semantisk modell, og gjør det mulig å oppnå faktisk interoperabilitet mellom løsninger som tar vare på dokumentasjon.

StandardLab teamet har utarbeidet 3 eksempler på hvordan det er mulig å bygge opp teknisk modell uten å ha konkret tilfelle å forholde seg til. Følgende forutsetninger har vært tatt:

* Tekniske modeller baserer seg på semantisk modell som er beskrevet her: [infomodell-mvp.md](infomodell-mvp.md)
* Sammenheng mellom den semantiske og den tekniske modeller er innlysende. Det er ingen behov for støttemateriale som gjør kobling mellom klasser og egenskaper entydig
* Modell er formulert i [UML klassediagramm](https://en.wikipedia.org/wiki/Unified_Modeling_Language) notasjon. En av modelleту bruker OCL ([Object Constraint Language](https://en.wikipedia.org/wiki/Object_Constraint_Language))
* Norsk språk brukes i navn på både klasser og egenskaper
* Typestruktur tilsvarer en eller annen moder objektorientert språk, uten å peke tydelig på noe konkret språk

## En-til-en

Denne modellen ligger seg tettest inn til den semantiske modellen. Ingen av verktøy som er tilgjengelige for objektorientert modellering er brukte. Det er ganske lett å kjenne igjen klasser `Registrering` og `Aggregering` og begge støtteklassene.

Mengde piler i diagrammen er betydelig større, siden arv er ikke brukt. De fleste koblingene som kunne ha gått til både `Registrering` og `Aggregering` er blitt doblet opp.

Det er nødvendig til å bruke Object Contraint Language for å vise at selv om det er mulig at `Aggregering` innholder ingen `Registrering` eller ingen `Aggregering`, den er nødt til å inneholde en av de.

Alt dette gjør modell detaljer, og noe tungt å vedlikeholde.

![Teknisk modell: En-til-en](/standarder/figurer/teknisk-modell-1.png)

## Noe generalisert

Bruk av [arv](https://en.wikipedia.org/wiki/Inheritance_(object-oriented_programming)) og [abstrakt klasse](https://en.wikipedia.org/wiki/Abstract_type) gir oss mulighet for å tegne kortere og mer konsist diagramm.

Støtteklassene (`InntruffetHendelse` og `PlanlagtHendelse`) abstraheres fremdeles ikke, og er sett på som 2 helt uavhengige klasser.

![Teknisk modell: Noe generalisert](/standarder/figurer/teknisk-modell-2.png)


## Generalisert til det ytterste



![Teknisk modell: Generalisert](/standarder/figurer/teknisk-modell-3.png)