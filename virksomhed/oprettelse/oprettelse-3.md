---
description: Angivelse af dine virksomhedsoplysninger
---

# Grundlæggende oplysninger

Under **Virksomhed** i menuen til venstre kan du indtaste de grundlæggende oplysninger om din virksomhed. Her finder du de samme faner som i følgende beskrivelse:

{% tabs %}
{% tab title="Generelt" %}
Under denne fane kan du angive stamdata for din virksomhed.

Vi anbefaler at angive dine virksomhedsoplysninger, herunder navn, adresse og CVR-nummer, da det vil være de oplysninger der vil blive anvendt på faktura m.m.
{% endtab %}

{% tab title="Indstillinger" %}
Under denne fane kan du angive hvordan Previsto skal fungere for lige netop din virksomhed.

#### Integration til regnskab <a id="integration-til-regnskab"></a>

Du kan angive om din virksomhed er knyttet til et regnskabssystem og i så fald hvilket. Ved at angive det kan du få Previsto til automatisk at fakturere de arbejde din virksomhed udfører. Læs mere om detaljerne i det på følgende side:

{% page-ref page="../../aftaler/automatisk-fakturering.md" %}

#### Låste dage <a id="l&#xE5;ste-dage"></a>

Previsto forsøger hele tiden at optimere dine ruter. Det betyder at der kan blive justeret løbende i de ruter der er planlagt. Men mange virksomheder har behov for at kunne låse planen fast for nært forestående arbejde. Derfor kan du med denne indstilling angive hvor mange dage ud i fremtiden du ønsker planen låst for din virksomhed.

Hvis du f.eks. angiver 7 dage, vil arbejde der er planlagt indenfor de næste 7 dage ikke blive flyttet til en anden dag automatisk - heller ikke hvis det ellers kunne optimere din rute. Du vil selvfølgelig stadig selv kunne flytte arbejdet manuelt, hvis du får behov for det.
{% endtab %}

{% tab title="Abonnement" %}
Under denne fane kan du se og ændre dine betalingsoplysninger ligesom du kan se og hente dine tidligere fakturaer.

Det er også her du kan opsige eller genoptage dit abonnement.
{% endtab %}

{% tab title="API" %}
Under denne fane har du et overblik over API-nøglerne til din virksomhed. Disse nøgler er specifikt knyttet til din virksomhed alene.

### Public ApiKey

Denne nøgle er, som navnet antyder, en offentlig nøgle. Det skal forstås på den måde at det er sikkert at give denne nøgle til hvem som helst. Den vil oftest blive brugt til at tilgå dine virksomheds data fra f.eks. en offentligt hjemmeside.

Denne offentlige nøgle har ikke mange rettigheder i Previsto. Den har udelukkende adgang til at gøre følgende i din virksomhed i Previsto:

* Oprette ny kunde
* Oprette ny aftale
* Oprette ny opgave

Den offentlige nøgle har _ikke_ adgang til at læse nogen som helst data fra din virksomhed.

### Secret ApiKey

Den nøgle er, som navnet antyder, en hemmelig nøgle. Den skal og må bevares hemmelig, da den har rettighed til alle data i din virksomhed. Den kan anvendes til at integrere med dine virksomheds data fra andre systemer.

Hvis du mener at uvedkommende har fået fat på denne nøgle bør du klikke på `Regenerér nøgler` for at få nye nøgler. De gamle nøgler vil effektivt være ubrugelige bagefter.
{% endtab %}

{% tab title="Notifikationer" %}
Denne fane giver dig mulighed for at bestemme hvordan notifikationer skal sendes til dine kunder.

Du kan angive om notifikationer skal leveres vi Email og/eller Sms. Du kan også angive om Previsto automatisk skal sende påmindelser ud til kunden før arbejdet bliver udført eller en notifikation når arbejdet er udført.
{% endtab %}
{% endtabs %}

