---
description: Variabler der kan bruges i tekster i Previsto
---

# Variabler

Det er muligt at gøre brug af nogle særlige variabler i Previsto for at inkludere data fra systemet i diverse tekster.

### Opgavebeskrivelse - og varelinjer

Når du i Previsto opretter en aftale eller en opgave, skal du angive en beskrivelse af opgaven. Denne beskrivelse bliver også anvendt på varelinjer i fakturaer. I nogle tilfælde er der behov for at få nogle data med fra systemet når fakturaen dannes og det er derfor muligt at anvende _variabler_ i beskrivelsen.

Variablerne angives i teksten på følgende måde: `${<variabel>}`. F.eks. kan en beskrivelse med dato for udførelse af en opgave angives på følgende måde: `Udvendig pudsning den ${date}` hvor `date`. er variablen.

#### Tilgængelige variabler

| Variabel | Beskrivelse | Eksempel |
| :--- | :--- | :--- |
| date | Dato for opgavens udførelse | Udvendig pudsning den ${date} |
| organization.name | Navnet på virksomheden | Pudsning foretaget af ${organization.name} |
| organization.phone | Telefonnummer på virksomheden | Pudsning udført. Kontakt ${organization.phone} |
| organization.email | Email på virksomheden | Pudsning udført. Kontakt ${organization.email} |

