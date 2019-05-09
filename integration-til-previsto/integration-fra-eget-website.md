---
description: >-
  Denne side beskriver hvordan du kan integrere dit eget website med Previsto så
  nye kunder oprettes direkte i Previsto.
---

# Oprettelse af kunder direkte fra eget website

{% hint style="info" %}
Denne sektion er af teknisk art og kræver at man selv har en basal viden om webudvikling \(HTML/Javascript\). Derudover er det gavnlig hvis man kan begå sig på en kommandolinje.
{% endhint %}

## Forberedelse

Før du påbegynder integration til Previsto direkte fra dit eget website, skal du have en `public apikey` til din virksomhed. Du finder den under menupunktet `Udvikler` i Previsto når du er logget ind i din virksomhed.

![Du kan finde din Public ApiKey n&#xE5;r du er logget ind i Previsto](../.gitbook/assets/skaermbillede-2019-05-09-kl.-12.43.51.png)

{% hint style="danger" %}
Det er vigtigt at du kun bruger **Public ApiKey** når du integrerer fra dit website. Denne nøgle har ekstremt begrænset rettigheder og er egnet til at blive anvendt på offentlige steder - som f.eks. på dit website.
{% endhint %}

Når du har din offentlige nøgle kan du teste den fra en kommandolinje ved at tilgå [Previsto's API](../api/introduction-to-api.md). \(Bemærk: På grund af nøglens meget begrænsede rettigheder vil følgende give en fejl om at der ikke kan opnås adgang\)

```text
$ curl -u pk_65pRgtXNbEiqSWREWFaad3r3RT1TBel: https://api.previsto.io/contacts
{
  "message" : "Access is denied",
  "type" : "InvalidRequestError"
}
```

Ovenstående er et korrekt svar fra serveren. Hvis du på den anden side ikke angiver en valid ApiKey, så vil du modtage følgende svar istedet.

```text
$ curl -u pk_this-key-is-invalid: https://api.previsto.io/contacts 
{
    "type": "InvalidRequestError" ,
    "message": "Bad credentials"
}
```

Når du har sikret dig at du har fået det rette svar fra serveren, er du klar til at gå igang med at lave selve implementation på dit website. [🙌🏻](https://emojipedia.org/person-raising-both-hands-in-celebration-type-1-2/)

## Oprettelse af kunde

_Bliver snart beskrevet_

### Oprettelse af tilbud eller aftale

_Bliver snart beskrevet_

