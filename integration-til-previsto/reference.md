# Reference

{% hint style="warning" %}
 This page is being built!
{% endhint %}

This is the API reference for Previsto.js. Use Previsto.js’ APIs to create contacts, create agreements, geocode addresses using customizable [Previsto Elements](previsto.js-og-elements.md), and have customers requests for getting a quote from you planned fully automatic.

### Including Previsto.js

However you’re using Previsto.js, you always begin by including the library and setting your API key. To get started, include this script on your pages—it should always be loaded directly from **https://js.previsto.com**:

```text
<script src="https://js.previsto.com/v1/"></script>
```

### Previsto\(publicApiKey\[, options\]\)

Use `Previsto(publicApiKey[, options])` to create an instance of the Previsto object. Your Previsto public API key is required when calling this function, as it identifies your website to Previsto.

```text
v​ar previsto = new Previsto(‘pk_fkdkeofkfkfkekdkdke’);
```

We‘ve placed a random API key in the code. Replace it with your [actual publishable API](api-keys.md) keys to test this code through your Previsto account.

### T​he Previsto Object 

* [previsto.createContact\(\)](https://app.gitbook.com/@previsto/s/help/~/drafts/-LemIT6N4OkLu6IxNDL6/primary/integration-til-previsto/reference#previsto-createcontact)
* [p​revisto.createAgreement\(\)](https://app.gitbook.com/@previsto/s/help/~/drafts/-LemIT6N4OkLu6IxNDL6/primary/integration-til-previsto/reference#previsto-createagreement)
* [p​revisto.searchAddress\(\)](https://app.gitbook.com/@previsto/s/help/~/drafts/-LemIT6N4OkLu6IxNDL6/primary/integration-til-previsto/reference#previsto-searchaddress)
* [p​revisto.requestTwoFaToken\(\)](https://app.gitbook.com/@previsto/s/help/~/drafts/-LemIT6N4OkLu6IxNDL6/primary/integration-til-previsto/reference#previsto-requesttwofatoken)

### previsto.createContact\(\)

### previsto.createAgreement\(\)

### previsto.searchAddress\(\)

### previsto.requestTwoFaToken\(\)

​




