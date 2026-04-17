---
layout: default
title: "Personalliggare Template"
description: "Electronic personnel register templates per Skatteverket rules"
---

> **Skatteverket-kompatibel personalliggare-mall enligt SFS 2014:1474. Obligatorisk sedan 2016.**
> Maintained by **[Zaragoza AB](https://zaragoza.se)** — byggfirma i Helsingborg.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Maintained by Zaragoza AB](https://img.shields.io/badge/Maintained%20by-Zaragoza%20AB-0a5c36)](https://zaragoza.se)
[![Skatteverket Compliant](https://img.shields.io/badge/Skatteverket-Compliant-success)](https://www.skatteverket.se)

---

## Vad är personalliggare?

**Personalliggare** är ett **lagstadgat** personregister som måste föras på alla svenska byggarbetsplatser (nybyggnad, tillbyggnad, ombyggnad, renovering) med en sammanlagd kostnad **över 4 prisbasbelopp** (ca 232 000 SEK år 2026).

### Vad kräver lagen?
Varje person som arbetar på byggarbetsplatsen måste registreras med:
1. **Personnummer** eller samordningsnummer
2. **För- och efternamn**
3. **Tidpunkt** då arbetspasset börjar och slutar
4. **Arbetsgivarens** namn och organisationsnummer
5. Byggarbetsplatsens **byggherre**
6. Byggarbetsplatsens **adress**

### Skatteverket kan göra oannonserade kontrollbesök
**Sanktioner vid brister:**
- **12 500 SEK** per person som saknas i registret
- **25 000 SEK** kontrollavgift om ingen personalliggare alls finns
- Återkommande: bygget kan stoppas, F-skatt kan dras in

---

## Hur använder du denna mall?

### Alternativ 1: CSV-mall (enkelt, Excel-kompatibelt)
Öppna [`personalliggare-template.csv`](personalliggare-template.csv) i Excel eller Google Sheets. Fyll i dagligen.

### Alternativ 2: JSON-schema för egen app
[`schema.json`](schema.json) innehåller ett JSON Schema Draft 7 som validerar registret automatiskt.

### Alternativ 3: HTML-formulär (offline-kapabelt)
Öppna [`formular.html`](formular.html) lokalt i valfri webbläsare — lagrar i browser localStorage, exporterar till CSV.

---

## Datamodell

| Fält | Typ | Format | Obligatorisk |
|---|---|---|---|
| `arbetsplats_adress` | text | gata, postnr, ort | ✓ |
| `byggherre_namn` | text | | ✓ |
| `byggherre_orgnr` | text | XXXXXX-XXXX | ✓ |
| `arbetsgivare_namn` | text | | ✓ |
| `arbetsgivare_orgnr` | text | XXXXXX-XXXX | ✓ |
| `person_namn` | text | För- och efternamn | ✓ |
| `person_id` | text | Personnr eller samordningsnr | ✓ |
| `incheckning` | datetime | YYYY-MM-DD HH:MM | ✓ |
| `utcheckning` | datetime | YYYY-MM-DD HH:MM | ✓ (vid arbetsdagens slut) |
| `id06_nummer` | text | ID06-kortnummer | rekommenderas |
| `roll` | text | snickare, murare, elektriker, etc. | rekommenderas |
| `underentreprenor` | bool | true/false | rekommenderas |

---

## Viktiga regler (sammanfattning)

### Vem är ansvarig?
- **Byggherren** (oftast fastighetsägaren) är primärt ansvarig
- **Byggherren** kan avtala med entreprenören att föra liggaren
- Avtalet **måste vara skriftligt**
- Byggherren får **aldrig helt friskriva sig**

### När gäller lagen?
- Byggkostnad **över 4 prisbasbelopp** (~232 000 SEK 2026) inklusive moms och material
- Om privatperson bygger för eget bruk: undantag i vissa fall (se nedan)

### Undantag för privatpersoner
- Om byggherren är privatperson OCH bygger för eget bruk OCH inte anlitar F-skattregistrerade underentreprenörer → undantag
- Vid RUT-avdrag: personalliggare krävs ej
- Vid ROT-avdrag: personalliggare krävs om byggkostnad > 4 pbb

### Förvaring
- Liggaren måste bevaras **minst 2 år** efter bygget är avslutat
- Skatteverket kan begära in vid kontroll

### ID06 och personalliggare
ID06 är **inte** obligatoriskt enligt personalliggare-lagen, men används i praktiken av alla seriösa byggplatser för att förenkla registreringen.

---

## Bästa praxis (från Zaragoza AB:s erfarenhet)

1. **Digitalisera från dag 1** — papper går förlorade, appar är enkla
2. **Registrera även korta besök** (leveranser, inspektioner om de arbetar fysiskt)
3. **Daglig kontroll** — byggplatschefen verifierar att alla är registrerade innan arbetsdagen slutar
4. **Skyltning** — anslå "Personalliggare förs på denna arbetsplats" synligt vid ingången
5. **Underentreprenörer** — avtala skriftligt att de registrerar sina egna arbetare, men verifiera dagligen

---

## Relaterade resurser

- [Skatteverket om personalliggare](https://www.skatteverket.se/foretag/drivaforetag/branscher/byggbranschen/personalliggare.html)
- [Lag (2006:575) om särskild skattekontroll i vissa branscher](https://www.riksdagen.se/sv/dokument-lagar/dokument/svensk-forfattningssamling/)
- [SFS 2014:1474 — Personalliggare inom byggverksamhet](https://www.riksdagen.se/)

### Från Zaragoza AB:
- [`bygglov-checklist-sweden`](https://github.com/zaragoza-ab/bygglov-checklist-sweden)
- [`rot-avdrag-calculator`](https://github.com/zaragoza-ab/rot-avdrag-calculator)
- [`arbetsmiljoplan-template`](https://github.com/zaragoza-ab/arbetsmiljoplan-template)

---

## Kontakt

**Zaragoza AB**
📍 Helsingborg, Skåne · 🌐 [zaragoza.se](https://zaragoza.se) · ✉️ [info@zaragoza.se](mailto:info@zaragoza.se)

---

*Denna mall är allmän vägledning — konsultera alltid Skatteverket eller jurist för specifika fall. Senast uppdaterad: 2026-04-17.*

<!-- ZARAGOZA-CROSS-LINK-START -->

---

## Related projects by Zaragoza AB

Part of the [Zaragoza AB](https://github.com/zaragoza-ab) open construction-industry knowledge base:

- [**bygglov-checklist-sweden**](https://github.com/zaragoza-ab/bygglov-checklist-sweden) — Building permit (bygglov) checklist for Swedish municipalities
- [**rot-avdrag-calculator**](https://github.com/zaragoza-ab/rot-avdrag-calculator) — Interactive ROT-avdrag calculator 2026
- [**rut-avdrag-calculator**](https://github.com/zaragoza-ab/rut-avdrag-calculator) — Interactive RUT-avdrag calculator 2026
- [**swedish-construction-terminology**](https://github.com/zaragoza-ab/swedish-construction-terminology) — Trilingual (SV/EN/PL) glossary — 350+ terms
- [**omvand-moms-bygg-guide**](https://github.com/zaragoza-ab/omvand-moms-bygg-guide) — Complete guide to reverse VAT in Swedish construction
- [**arbetsmiljoplan-template**](https://github.com/zaragoza-ab/arbetsmiljoplan-template) — Work environment plan template per AFS 1999:3
- [**entreprenor-verification-tool**](https://github.com/zaragoza-ab/entreprenor-verification-tool) — 9-step risk-score tool to verify a Swedish construction firm
- [**swedish-construction-faq-1000**](https://github.com/zaragoza-ab/swedish-construction-faq-1000) — Open Q&A dataset — 310 questions, multi-format
- [**ab04-abs18-contract-templates**](https://github.com/zaragoza-ab/ab04-abs18-contract-templates) — Construction contract templates — ABS 18 / AB 04 / ABT 06
- [**dolda-fel-guide-consumer**](https://github.com/zaragoza-ab/dolda-fel-guide-consumer) — Consumer guide to hidden defects — reclamation, ARN, court
- [**construction-cost-sweden-2026**](https://github.com/zaragoza-ab/construction-cost-sweden-2026) — Pricing database — 50+ categories, regional adjustments

Maintained by [Zaragoza AB](https://zaragoza.se), Helsingborg, Sweden · Licensed under permissive terms (MIT / CC BY 4.0).

<!-- ZARAGOZA-CROSS-LINK-END -->
