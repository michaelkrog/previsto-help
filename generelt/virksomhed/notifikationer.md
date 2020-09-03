---
description: Afsend notifikationer til dine kunder via SMS eller Email
---

# Notifikationer

Du kan få Previsto til at sende notifikationer til dine kunder som en varsling af den opgave du kommer og udfører eller som en information om at du _har_ været og udføre en opgave.

### Indstil notifikationer <a id="indstil-notifikationer"></a>

1. Klik på **Indstillinger** i menuen.
2. Vælg **Notifikationer**.
3. Angiv om notifikationer skal sendes ud via SMS og/eller Email. [1](https://previsto.com/da/support/virksomhed-notifikationer/#fn:priser)
4. Angiv evt. om Previsto automatisk skal sende notifikationer.
5. Angiv evt. om varslinger til kunden skal indeholde tidspunkter for servicevindue.

Ved at klikke på blyanten ud for de hændelser hvor der automatisk afsendes notifikationer, kan du redigere og/eller se et preview af de notifikationer der bliver sendt.

Du kan med det samme begynde at sende varslinger til de kunder der har enten et telefonnummer eller en email-adresse angivet. For de kunder hvor ingen af delene er angivet kan du ikke sende en notifikation.

### Påmindelse / Varsling

Påmindelser eller varslinger er notifikationer der sendes før arbejdet udføres. Det er en hjælp til at minde kunden om at din virksomhed har planlagt at udføre arbejde for dem samt en information om hvornår det vil ske. Du kan vælge at Previsto automatisk skal gøre det 3 dage før arbejdet skal udføres eller du kan vælge at gøre det manuelt på de enkelte kunder du ønsker at varsle.

På en kundes aftale kan du angive en **tekst før arbejdets udførelse**. Det er en besked du ønsker at give kunden i forbindelse med varslingen, f.eks. `Husk at lægge en nøgle.` eller `Lad bagdøren stå åben.` i forbindelsen med opgaver der f.eks. kræver at du kommer indenfor selvom ingen er hjemme. Det kan også være andre beskeder som passer til den givne situation.

Når kunden får tilsendt en varsling indeholder den følgende besked. \(Det er vores standard besked fra systemet, men du kan dog ændre beskederne til en egen specifik tekst\)

```text
Kære <her indsættes kundenavn>

Vi kommer den <her indsættes dato + evt. tidspunkt for servicevindue> og udfører følgende arbejde:
* <her indsættes arbejdets beskrivelse> - <her indsættes tekst forud for arbejde>
* <her indsættes evt. mere arbejdes beskrivelse> - <her indsættes tekst forud for arbejde>

Med venlig hilsen
<firmanavn>
<signaturtekst>
```

#### Eksempel

```text
Kære Jørgen Jensen

Vi kommer den 28/3-2020 kl. 8-12 og udfører følgende arbejde:
* Udvendig vinduespolering
* Indvendig vinduespolering - Husk at lade terassedøren stå åben

Med venlig hilsen
Rent rundt på gulvet Aps
Kontakt os på tlf: 22 33 44 55
```

Når en kunde er blevet varslet, vil det blive angivet i planen. Opgaven vil blive låst til den dato kunden er blevet informeret om og har fået et servicevindue tildelt som Previsto vil anvende i planlægningen. Du kan dog stadig manuelt flytte opgaven til en anden dag.

### Besked om udført arbejde <a id="besked-om-udf&#xF8;rt-arbejde"></a>

Hvis du har sat Previsto til at sende en notifikation når en opgave er udført, vil Previsto gøre det automatisk når du gennemfører en opgave i Previsto og kunden har enten telefonnummer eller email-adresse angivet.

Når kunden modtager en notifikation om udført arbejde vil den indeholde følgende besked \(Det er vores standard besked fra systemet, men du kan dog ændre beskederne til en egen specifik tekst\).

```text
Kære <her indsættes kundenavn>

Vi har den <her indsættes dato> udført følgende arbejde:
* <her indsættes arbejdets beskrivelse> - <her indsættes meddelelse efter udført arbejde>
* <her indsættes evt. mere arbejdes beskrivelse> - <her indsættes meddelelse efter udført arbejde>

Vi ser frem til at servicere dem igen.

Med venlig hilsen
<firmanavn>
<signaturtekst>
```

#### Eksempel

```text
Kære Jørgen Jensen

Vi har den 28/3-2020 kl. 8-12 udført følgende arbejde:
* Udvendig vinduespolering
* Indvendig vinduespolering

Vi ser frem til at servicere dem igen.

Med venlig hilsen
Rent rundt på gulvet Aps
Kontakt os på tlf: 22 33 44 55
```

### Bemærkning vedr. SMS’er <a id="bem&#xE6;rkning-vedr-smser"></a>

En SMS kan indeholde 160 tegn. Hvis en notifikation indeholder mere end 160 tegn, vil den derfor blive beregnet som mere end én SMS. Af samme grund er teksten i notifikationerne holdt meget kort, men afhængig af titlen på opgaverne, varslingstekst, kundens navn, firmanavn osv. kan den samlede længde overstige 160 karakterer og blive beregnet som mere end én SMS.

Email’s er ikke underlagt samme begrænsning og vil altid kun blive beregnet som én email uanset antal tegn.

