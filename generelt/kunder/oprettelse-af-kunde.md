---
description: Previsto kan håndtere uendeligt mange kunder.
---

# Oprettelse af kunde

Med Previsto kan du have et ubegrænset antal kunder i virksomheden.

I menuen vælger du “kunder” og derefter klikker du på det orange + i bunden af siden. Udfyld kundeinformation og klik på fluebenet done øverst.

Se hvordan du opretter en kunde i følgende video. Detaljer om oprettelse af kunde fortsætter på denne side efter videoen.

{% embed url="https://youtu.be/SQ8ID0cs4fo" %}

{% tabs %}
{% tab title="Generelt" %}
Under denne fane kan du indtaste kundens stamdata. Informationer som navn og adresse er påkrævet.

#### Email og telefonnummer <a href="#email" id="email"></a>

At angive telefon og email for kunden kan være en god idé. Det giver Previsto mulighed for at kontakte kunden, fx. ved udsendelse af faktura, notikationer m.m.

#### Hvad betyder ‘EAN’? <a href="#hvad-betyder-ean" id="hvad-betyder-ean"></a>

Et EAN-nummer er et 13-cifret nummer, der kendetegner en bestemt offentlig virksomhed.\
EAN står for ”European Article Numbering”. Det er altså det specifikke nummer, som skal stå på fakturaen når du sender den til fx en kommune.

#### Hvad betyder ‘kundenummer’? <a href="#hvad-betyder-kundenummer" id="hvad-betyder-kundenummer"></a>

Nummeret kan bruges som en identifikation af kunden hvis man manuelt ønsker at referere til samme kunde oprettet i et eksternt system, f.eks. et regnskabsprogram som Dinero ikke har integration til. Det giver et let overblik over hvilket kunder du manuelt skal fakturere i dit eksterne regnskabssystem.

{% content-ref url="broken-reference" %}
[Broken link](broken-reference)
{% endcontent-ref %}
{% endtab %}

{% tab title="Planlægning" %}
Fanen `Planlægning` indeholder detaljer der vedrører planlægning generelt for kunden.

#### Foretrukken medarbejder <a href="#foretrukken-medarbejder" id="foretrukken-medarbejder"></a>

Ved at vælge en fortrukken medarbejder kan du sørge for at kundens aftaler altid bliver planlagt til en bestemt medarbejder i din virksomhed. Du vil dog altid manuelt kunne tilrette det i planoversigten hvis opstår behov for det.

#### Servicevindue <a href="#servicevindue" id="servicevindue"></a>

Angiver hvornår på dagen kunde foretrækker at arbejde hos dem udføres. Servicevinduet skal være på minimum 3 timer, f.eks. fra 06:00-09:00.

Previsto tager servicevinduet med i betragtning når den planlægger ruterne så du så vidt muligt er hos kunden indenfor tidsvinduet. Der kan dog være situationer hvor det ikke kan lade sig gøre at lægge planen så servicevinduet rammes. I de tilfælde vil Previsto planlægge det så tæt på servicevinduet som muligt.

#### Kunden skal varslen om forestående arbejde <a href="#kunden-skal-varslen-om-forestaende-arbejde" id="kunden-skal-varslen-om-forestaende-arbejde"></a>

Indikerer overfor medarbejderen at kunden skal have besked fra gang til gang om hvornår arbejdet udføres. Det vil blive vist i planen om medarbejderen skal huske at sende et varslet til kunden.\

{% endtab %}

{% tab title="Bogføring" %}
Denne fane giver mulighed for at justere hvordan kunden bogføres hvis du har integration til et regnskabssystem.

{% content-ref url="broken-reference" %}
[Broken link](broken-reference)
{% endcontent-ref %}

#### Bogføring af arbejde <a href="#bogforing-af-arbejde" id="bogforing-af-arbejde"></a>

Dette angiver om kunden skal bogføres eller ej. Du kan vælge følgende:

* Din virksomheds standardindstilling: Kundens arbejde bogføres som det er valgt under din virksomheds indstillinger.
* Ingen bogføring: Kundes arbejde bliver ikke bogført.
* Føj til fakturakladde: Kundens arbejde oprettes som kladde i regnskabssystemet, men afsluttes ikke. Senere arbejde på samme kunde vil blive føjet til samme kladde.
* Føj til fakturakladde og fakturér: Kundens arbejde oprettes som kladde i regnskabssystemet og afsluttes med oprettelse af faktura.

#### Bogføringstidspunkt <a href="#bogforingstidspunkt" id="bogforingstidspunkt"></a>

Dette angiver hvornår faktura for kunden skal oprettes. Du kan vælge følgende:

* Din virksomheds standardindstilling: Kundens arbejde bogføres på det tidspunkt det er valgt under din virksomheds indstillinger.
* Før arbejde gennemføres: Kundens arbejde vil blive bogført natten inden det er planlagt at blive udført.
* Efter arbejde gennemføres: Kundens arbejde vil blive bogfør når det markeres som gennemført.

#### Fakturalevering <a href="#fakturalevering" id="fakturalevering"></a>

Dette angiver om fakturaen automatisk skal leveres til kunden. Du kan vælge følgende:

* Din virksomheds standardindstilling: Kundens faktura levere som det er valgt under din virksomheds indstillinger.
* Ingen levering: Ingen automatisk levering af fakturaen.
* Email: Previsto vil bede dit regnskabssystem om at sende fakturaen ud til kunden.

Kunden er nu oprettet og du er klar til at oprette aftaler på kunden.
{% endtab %}

{% tab title="Notifikationer" %}
Det er her muligt at overrule virksomhedens indstillinger for notifikationer for denne ene specifikke kunde.

{% content-ref url="../virksomhed/notifikationer.md" %}
[notifikationer.md](../virksomhed/notifikationer.md)
{% endcontent-ref %}
{% endtab %}
{% endtabs %}

