---
description: Afsend notifikationer til dine kunder via SMS eller Email
---

# Notifikationer

Du kan få Previsto til at sende notifikationer til dine kunder som en varsling af den opgave du kommer og udfører eller som en information om at du _har_ været og udføre en opgave.

### Indstil notifikationer <a id="indstil-notifikationer"></a>

1. Klik på “Virksomhed” i menuen.
2. Vælg fanen ‘Notifikationer’.
3. Angiv om notifikationer skal sendes ud via SMS og/eller Email. [1](https://previsto.com/da/support/virksomhed-notifikationer/#fn:priser)
4. Angiv evt. om Previsto automatisk skal sende notifikationer.
5. Angiv evt. om varslinger til kunden skal indeholde tidspunkter for servicevindue.

Når du har indstillet notifikationer kan du sende test-beskeder for at se om dine notifikationer ser ud som du ønsker de skal.

Du kan med det samme begynde at sende varslinger til de kunder der har enten et telefonnummer eller en email-adresse angivet. For de kunder hvor ingen af delene er angivet kan du ikke sende en notifikation.

### Påmindelse / Varsling

Påmindelser eller varslinger er notifikationer der sendes før arbejdet udføres. Det er en hjælp til at minde kunden om at din virksomhed har planlagt at udføre arbejde for dem samt en information om hvornår det vil ske. Du kan vælge at Previsto automatisk skal gøre det 3 dage før arbejdet skal udføres eller du kan vælge at gøre det manuelt på de enkelte kunder du ønsker at varsle.

På en kundes aftale kan du angive en varslingstekst. Det er en besked du ønsker at give kunden i forbindelse med varslingen, f.eks. `Husk at lægge en nøgle.` eller `Lad bagdøren stå åben.` i forbindelsen med opgaver der kræver at du kommer indenfor selvom ingen er hjemme. Det kan også være andre beskeder som passer til den givne situation.

Når kunden får tilsendt en varsling indeholder den følgende besked:

```text
Kære <her indsættes kundenavn>

Vi kommer den <dato + evt. tidspunkt for servicevindue> og udfører følgende arbejde:
* <arbejdets beskrivelse> - <tekst forud for arbejde>
* <evt. mere arbejdes beskrivelse> - <tekst forud for arbejde>

Med venlig hilsen
<firmanavn>
<signaturtekst>
```

Når en kunde er blevet varslet, vil det blive angivet i planen. Opgaven vil blive låst til den dato kunden er blevet informeret om og har fået et servicevindue tildelt som Previsto vil anvende i planlægningen. Du kan dog stadig manuelt flytte opgaven til en anden dag.

### Besked om udført arbejde <a id="besked-om-udf&#xF8;rt-arbejde"></a>

Hvis du har sat Previsto til at sende en notifikation når en opgave er udført, vil Previsto gøre det automatisk når du gennemfører en opgave i Previsto og kunden har enten telefonnummer eller email-adresse angivet.

Når kunden modtager en notifikation om udført arbejde vil den indeholde følgende besked:

```text
Kære <her indsættes kundenavn>

Vi har den <her indsættes dato> udført følgende arbejde:
* <arbejdets beskrivelse> - <meddelelse efter udført arbejde>
* <evt. mere arbejdes beskrivelse> - <meddelelse efter udført arbejde>

Vi ser frem til at servicere dem igen.

Med venlig hilsen
<firmanavn>
<signaturtekst>
```

### Bemærkning vedr. SMS’er <a id="bem&#xE6;rkning-vedr-smser"></a>

En SMS kan indeholde 160 tegn. Hvis en notifikation indeholder mere end 160 tegn, vil den derfor blive beregnet som mere end én SMS. Af samme grund er teksten i notifikationerne holdt meget kort, men afhængig af titlen på opgaverne, varslingstekst, kundens navn, firmanavn osv. kan den samlede længde overstige 160 karakterer og blive beregnet som mere end én SMS.

Email’s er ikke underlagt samme begrænsning og vil altid kun blive beregnet som én email uanset antal tegn.

