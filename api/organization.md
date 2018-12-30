# Organization

This is an object representing an organization in Previsto. You can retrieve it to see properties on the organization like its current e-mail address, physical address etc.

You are only allowed to access the organization your [account](http://tech.previsto.com/#account) refers to.

### The organization object <a id="the-organization-object"></a>

> Example Response

```text
{
    "id": "acct_123123123",
    "name": "Vinduespudser A/S",
    "url": "http://vinduespudser.nu",
    "address": "Pudservej 111",
    "postalCode": "1234",
    "city": "Pudserby",
    "countryCode": "DK",
    "phone": "+452209876543",
    "email": "vindue@pudser.dk",
    "registrationNo": "12345678",
    "terminated": false,
    "terminationTime": null,
    "createdDate": "2015-01-01T00:00:00Z",
    "trial": true,
    "subscriptionPrice": 0,
    "subscriptionPeriod": "Monthly",
    "subscriptionDiscount": 0.0,
    "subscriptionExpires": null,
    "subscriptionType": "Free",
    "languageCode": "da",
    "baseCurrency": "DKK",
    "locked": false,
    "subjectToVat": true,
    "timeZone": "Europe/Copenhagen"
}
```

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| id | string | No | - |
| name | string | Yes | Name of the business, fx. 'Vinduespudser A/S' |
| url | string | No | - |
| address | string | No | The street address, 'fx. Vesterbro 11' |
| postalCode | string | No | - |
| city | string | No | - |
| countryCode | string | No | 2-letter ISO 3166-1 code, fx. 'DK' |
| phone | string | No | Full international phonenumber, fx. '+4522123456' |
| email | string | No | - |
| registrationNo | string | No | The business's EU VAT number, CVR number in Denmark, TIN/EIN/SSN in US. |
| terminated | boolean | No | - |
| terminationTime | datetime | No | - |
| createdDate | datetime | No | - |
| trial | boolean | No | - |
| subscriptionPrice | number | No | Price for subscription in 1⁄100 of the monetary unit \(fx. cents or øre\) |
| subscriptionPeriod | string | No | 'Monthly', 'Quarterly', 'SemiAnnually' or 'Annually'. Default is 'Monthly'. |
| subscriptionDiscount | number | No | - |
| subscriptionExpires | datetime | No | - |
| subscriptionType | string | No | 'Free', 'Micro', 'Small', 'Medium' or 'Large'. |
| languageCode | string | No | 2-letter ISO 639-1 code, fx. 'da' |
| baseCurrency | string | Yes | 3-letter ISO 4217 code, fx. 'DKK' |
| locked | boolean | No | - |
| subjectToVat | boolean | No | - |
| timeZone | string | No | - |
| referenceId | string | No | An optional id for other systems to use for refering to this organization. |

### Create an organization <a id="create-an-organization"></a>

> Definition

```text
POST https://api.previsto.io/organizations
`
```

> Example Request

```text
curl https://api.previsto.io/organizations \
   -u sk_12345: \
   -d name="Vinduespudser A/S"
```

> Example Response

```text
{
    "id": "acct_123123123",
    "name": "Vinduespudser A/S",
    "url": null,
    "address": null,
    "postalCode": null,
    "city": null,
    "countryCode": "DK",
    "phone": null,
    "email": null,
    "registrationNo": null,
    "terminated": false,
    "terminationTime": null,
    "createdDate": "2015-01-01T00:00:00Z",
    "trial": true,
    "subscriptionPrice": 0,
    "subscriptionPeriod": "Monthly",
    "subscriptionDiscount": 0.0,
    "subscriptionExpires": null,
    "subscriptionType": "Free",
    "languageCode": "da",
    "baseCurrency": "DKK",
    "locked": false,
    "subjectToVat": true,
    "timeZone": "Europe/Copenhagen"
}
```

Creates a new organization.

A user can only create a new organization if it is not related to an organization yet. When a user creates a new organization it will automatically become related to the created organization.

#### Arguments <a id="arguments"></a>

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| name | string | Yes | Name of the business, fx. 'Vinduespudser A/S' |
| url | string | No | - |
| address | string | No | The street address, 'fx. Vesterbro 11' |
| postalCode | string | No | - |
| city | string | No | - |
| countryCode | string | No | 2-letter ISO 3166-1 code, fx. 'DK' |
| phone | string | No | Full international phonenumber, fx. '+4522123456' |
| email | string | No | - |
| registrationNo | string | No | The business's EU VAT number, CVR number in Denmark, TIN/EIN/SSN in US. |
| languageCode | string | No | 2-letter ISO 639-1 code, fx. 'da' |
| baseCurrency | string | No | 3-letter ISO 4217 code, fx. 'DKK' |
| subjectToVat | boolean | No | - |
| timeZone | string | No | - |

#### Returns <a id="returns"></a>

Returns an organization object if the call succeeded. If a invalid parameters are provided, the call will return an error.

### Retrieve an organization <a id="retrieve-an-organization"></a>

> Definition

```text
GET https://api.previsto.io/organization
```

> Example Request

```text
curl https://api.previsto.io/organization \
   -u sk_12345:
```

> Example Response

```text
{
    "id": "acct_123123123",
    "name": "Vinduespudser A/S",
    "url": "http://vinduespudser.nu",
    "address": "Pudservej 111",
    "postalCode": "1234",
    "city": "Pudserby",
    "countryCode": "DK",
    "phone": "+452212341234",
    "email": "vindue@pudser.dk",
    "registrationNo": "12345678",
    "terminated": false,
    "terminationTime": null,
    "createdDate": "2015-01-01T00:00:00Z",
    "trial": true,
    "subscriptionPrice": 0,
    "subscriptionPeriod": "Monthly",
    "subscriptionDiscount": 0.0,
    "subscriptionExpires": null,
    "subscriptionType": "Free",
    "languageCode": "da",
    "baseCurrency": "DKK",
    "locked": false,
    "subjectToVat": true,
    "timeZone": "Europe/Copenhagen"
}
```

Retrieves the details of the organization.

#### Arguments <a id="arguments"></a>

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| id | string | Yes | The identifier of the organization to be retrieved. |

#### Returns <a id="returns"></a>

Returns an organization object if a valid identifier was provided.

### Update an organization <a id="update-an-organization"></a>

> Definition

```text
POST https://api.previsto.io/organizations/{organization_ID}
```

> Example Request

```text
curl https://api.previsto.io/organizations/acct_123123123 \
   -u sk_12345: \
   -d phone=+452209876543
```

> Example Response

```text
{
    "id": "acct_123123123",
    "name": "Vinduespudser A/S",
    "url": "http://vinduespudser.nu",
    "address": "Pudservej 111",
    "postalCode": "1234",
    "city": "Pudserby",
    "countryCode": "DK",
    "phone": "+452209876543",
    "email": "vindue@pudser.dk",
    "registrationNo": "12345678",
    "terminated": false,
    "terminationTime": null,
    "createdDate": "2015-01-01T00:00:00Z",
    "trial": true,
    "subscriptionPrice": 0,
    "subscriptionPeriod": "Monthly",
    "subscriptionDiscount": 0.0,
    "subscriptionExpires": null,
    "subscriptionType": "Free",
    "languageCode": "da",
    "baseCurrency": "DKK",
    "locked": false,
    "subjectToVat": true,
    "timeZone": "Europe/Copenhagen"
}
```

Updates an organization by setting the values of the parameters passed. Any parameters not provided will be left unchanged.

#### Arguments <a id="arguments"></a>

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| name | string | Yes | Name of the business, fx. 'Vinduespudser A/S' |
| url | string | No | - |
| address | string | No | The street address, 'fx. Vesterbro 11' |
| postalCode | string | No | - |
| city | string | No | - |
| countryCode | string | No | 2-letter ISO 3166-1 code, fx. 'DK' |
| phone | string | No | Full international phonenumber, fx. '+4522123456' |
| email | string | No | - |
| registrationNo | string | No | The business's EU VAT number, CVR number in Denmark, TIN/EIN/SSN in US. |
| languageCode | string | No | 2-letter ISO 639-1 code, fx. 'da' |
| baseCurrency | string | No | 3-letter ISO 4217 code, fx. 'DKK' |
| subjectToVat | boolean | No | - |
| timeZone | string | No | - |

#### Returns <a id="returns"></a>

Returns the organization object if the update succeeded. Returns [an error](http://tech.previsto.com/#errors) if update parameters are invalid.

### Delete an organization <a id="delete-an-organization"></a>

> Definition

```text
DELETE https://api.previsto.io/organizations/{organization_ID}
```

> Example Request

```text
curl https://api.previsto.io/organizations/acct_123123123 \
   -u sk_12345: \
   -X DELETE
```

Permanently deletes an organization. It cannot be undone.

#### Arguments <a id="arguments"></a>

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| id | string | Yes | The identifier of the organization to be deletes. |

#### Returns <a id="returns"></a>

Returns an empty response upon success. If the organization ID does not exist, this call returns an error.

