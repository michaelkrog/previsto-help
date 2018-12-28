# Contact

A Contact specifies a Customer's information. The Contact can be a private person or a Company.

### The contact object <a id="the-contact-object"></a>

> Example Response

```text
{
    "id": "con_123123123",
    "name": "Anna Jensen",
    "address": "Kundevej 2",
    "appartment": null,
    "postalCode": "4321",
    "city": "Kundeby",
    "countryCode": "DK",
    "location" : [ 10.5286863, 56.8039035 ],
    "number": null,
    "remoteId": null,
    "remoteOrderId": null,
    "phone": "+452209876543",
    "email": "anna@jensen.dk",
    "registrationNo": null,
    "ean": null,
    "accountingMode": null,
    "accountingTime": null,
    "invoiceDelivery": null,
    "notifyBeforeWork": false,
    "archived": false,
    "agentIds": [],
    "meta": {
        "hairColor": "Brown"
    }
}
```

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| id | string | No | - |
| name | string | Yes | The name of the contact. Can be either a company name or a person's name. |
| address | string | No | The street address, 'fx. Vesterbro 11' |
| appartment | string | No | Apartment, fx. '1. th.' |
| postalCode | string | No | - |
| city | string | No | - |
| countryCode | string | No | 2-letter ISO 3166-1 code, fx. 'DK' |
| location | number\[\] | Yes | Array of length 2 holding longitude and latitude in specified order. \(Fx. \[11.543540954589844, 56.703469017862034\]\) |
| number | string | No | Arbitrary number \(or string\) that contacts can be referred to by. |
| remoteId | string | No | Id of the connected contact in financial system or null. |
| remoteOrderId | string | No | Id of current open order for this contact in financial system or null. |
| phone | string | No | Full international phonenumber, fx. '+4522123456' |
| email | string | No | - |
| registrationNo | string | No | The contact's EU VAT number, CVR number in Denmark, TIN/EIN/SSN in US. |
| ean | string | No | The contact's EAN \(European Article Number\). |
| accountingMode | string | No | `None`, `AddToDraft` or `AddToInvoice`. |
| accountingTime | string | No | `BeforeWork` or `AfterWork`. |
| invoiceDelivery | string | No | `None` or `Email`. |
| payingContactId | string | No | Id of another contact that pays assignments for this contact or null. |
| note | string | No | - |
| notifyBeforeWork | boolean | No | Flag that defines if contact should be notified of work or not. |
| archived | boolean | No | - |
| agentIds | string\[\] | No | Ids of the agents that takes care of this contact. Currently always account Ids. Empty list means that it is not specified. |
| meta | object | No | Dictionary of meta value. |

### Create a contact <a id="create-a-contact"></a>

> Definition

```text
POST https://api.previsto.io/contacts
`
```

> Example Request

```text
curl https://api.previsto.io/contacts \
   -u sk_12345: \
   -d name="Anna Jensen" \
   -d meta[hairColor]=Brown
```

> Example Response

```text
{
    "id": "con_123123123",
    "name": "Anna Jensen",
    "address": "Kundevej 2",
    "appartment": null,
    "postalCode": "4321",
    "city": "Kundeby",
    "countryCode": "DK",
    "location" : [ 10.5286863, 56.8039035 ],
    "number": null,
    "remoteId": null,
    "remoteOrderId": null,
    "phone": "+452209876543",
    "email": "anna@jensen.dk",
    "registrationNo": null,
    "ean": null,
    "accountingMode": null,
    "accountingTime": null,
    "invoiceDelivery": null,
    "notifyBeforeWork": false,
    "archived": false,
    "agentIds": [],
    "meta": {
        "hairColor": "Brown"
    }
}
```

Creates a new contact.

#### Arguments <a id="arguments"></a>

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| name | string | Yes | The name of the contact. Can be either a company name or a person's name. |
| address | string | No | The street address, 'fx. Vesterbro 11' |
| appartment | string | No | The apartment, 'fx. 1. th' |
| postalCode | string | No | - |
| city | string | No | - |
| countryCode | string | No | 2-letter ISO 3166-1 code, fx. 'DK' |
| location | number\[\] | Yes | Array of length 2 holding longitude and latitude in specified order. \(Fx. \[11.543540954589844, 56.703469017862034\]\) |
| number | integer | No | Arbitrary number \(or string\) that contacts can be referred to by. |
| phone | string | No | Full international phonenumber, fx. '+4522123456' |
| email | string | No | - |
| registrationNo | string | No | The contact's EU VAT number, CVR number in Denmark, TIN/EIN/SSN in US. |
| ean | string | No | The contact's EAN \(European Article Number\). |
| accountingMode | string | No | `None`, `AddToDraft` or `AddToInvoice`. |
| accountingTime | string | No | `BeforeWork` or `AfterWork`. |
| invoiceDelivery | string | No | `None` or `Email`. |
| payingContactId | string | No | Id of another contact that pays assignments for this contact or null. |
| note | string | No | - |
| notifyBeforeWork | boolean | No | Flag that defines if contact should be notified of work or not. |
| archived | boolean | No | - |
| meta | object | No | Dictionary of meta value. |

#### Returns <a id="returns"></a>

Returns an contact object if the call succeeded.

### Retrieve a contact <a id="retrieve-a-contact"></a>

> Definition

```text
GET https://api.previsto.io/contacts/{CONTACT_ID}
```

> Example Request

```text
curl https://api.previsto.io/contacts/con_123123123 \
   -u sk_12345:
```

> Example Response

```text
{
    "id": "con_123123123",
    "name": "Anna Jensen",
    "address": "Kundevej 2",
    "appartment": null,
    "postalCode": "4321",
    "city": "Kundeby",
    "countryCode": "DK",
    "location" : [ 10.5286863, 56.8039035 ],
    "number": null,
    "remoteId": null,
    "remoteOrderId": null,
    "phone": "+452209876543",
    "email": "anna@jensen.dk",
    "registrationNo": null,
    "ean": null,
    "accountingMode": null,
    "accountingTime": null,
    "invoiceDelivery": null,
    "notifyBeforeWork": false,
    "archived": false,
    "agentIds": [],
    "meta": {
        "hairColor": "Brown"
    }
}
```

Retrieves the details of an existing contact. You need only supply the unique contact identifier that was returned with the contact object upon a successfull creation.

#### Arguments <a id="arguments"></a>

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| id | string | Yes | The identifier of the contact to be retrieved. |

#### Returns <a id="returns"></a>

Returns a contact object if a valid identifier was provided.

### Update a contact <a id="update-a-contact"></a>

> Definition

```text
POST https://api.previsto.io/contacts/{CONTACT_ID}
```

> Example Request

```text
curl https://api.previsto.io/contacts/cot_123123123 \
   -u sk_12345: \
   -d phone=+4522123456
```

> Example Response

```text
{
    "id": "con_123123123",
    "name": "Anna Jensen",
    "address": "Kundevej 2",
    "appartment": null,
    "postalCode": "4321",
    "city": "Kundeby",
    "countryCode": "DK",
    "location" : [ 10.5286863, 56.8039035 ],
    "number": null,
    "remoteId": null,
    "remoteOrderId": null,
    "phone": "+452209876543",
    "email": "anna@jensen.dk",
    "registrationNo": null,
    "ean": null,
    "accountingMode": null,
    "accountingTime": null,
    "invoiceDelivery": null,
    "notifyBeforeWork": false,
    "archived": false,
    "agentIds": [],
    "meta": {
        "hairColor": "Brown"
    }
}
```

Updates the specified contact by setting the values of the parameters passed. Any parameters not provided will be left unchanged. For example, if you pass the address parameter, that becomes the contact's new address.

This request accepts mostly the same arguments as the contact creation call.

#### Arguments <a id="arguments"></a>

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| name | string | Yes | The name of the contact. Can be either a company name or a person's name. |
| address | string | No | The street address, 'fx. Vesterbro 11' |
| appartment | string | No | The apartment, 'fx. 1. th' |
| postalCode | string | No | - |
| city | string | No | - |
| countryCode | string | No | 2-letter ISO 3166-1 code, fx. 'DK' |
| location | number\[\] | Yes | Array of length 2 holding longitude and latitude in specified order. \(Fx. \[11.543540954589844, 56.703469017862034\]\) |
| number | integer | No | Arbitrary number \(or string\) that contacts can be referred to by. |
| phone | string | No | Full international phonenumber, fx. '+4522123456' |
| email | string | No | - |
| registrationNo | string | No | The contact's EU VAT number, CVR number in Denmark, TIN/EIN/SSN in US. |
| ean | string | No | The contact's EAN \(European Article Number\). |
| accountingMode | string | No | `None`, `AddToDraft` or `AddToInvoice`. |
| accountingTime | string | No | `BeforeWork` or `AfterWork`. |
| invoiceDelivery | string | No | `None` or `Email`. |
| payingContactId | string | No | Id of another contact that pays assignments for this contact or null. |
| note | string | No | - |
| notifyBeforeWork | boolean | No | Flag that defines if contact should be notified of work or not. |
| meta | object | No | Dictionary of meta value. |

#### Returns <a id="returns"></a>

Returns the contact object if the update succeeded. Returns [an error](http://tech.previsto.com/#errors) if update parameters are invalid.

### Delete a contact <a id="delete-a-contact"></a>

> Definition

```text
DELETE https://api.previsto.io/contacts/{CONTACT_ID}
```

> Example Request

```text
curl https://api.previsto.io/contacts/con_123123123 \
   -u sk_12345: \
   -X DELETE
```

Permanently deletes a contact. It cannot be undone.

#### Arguments <a id="arguments"></a>

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| id | string | Yes | The identifier of the contact to be deleted. |

#### Returns <a id="returns"></a>

Returns an empty response upon success. If the contact ID does not exist, this call returns an error.

### List all contacts <a id="list-all-contacts"></a>

> Definition

```text
GET https://api.previsto.io/contacts
```

> Example Request

```text
curl https://api.previsto.io/contacts \
   -u sk_12345:
```

> Example Response

```text
[
    {
        "id": "con_123123123",
        "name": "Anna Jensen",
        "address": "Kundevej 2",
        "appartment": null,
        "postalCode": "4321",
        "city": "Kundeby",
        "countryCode": "DK",
        "location" : [ 10.5286863, 56.8039035 ],
        "number": null,
        "remoteId": null,
        "remoteOrderId": null,
        "phone": "+452209876543",
        "email": "anna@jensen.dk",
        "registrationNo": null,
        "ean": null,
        "accountingMode": null,
        "accountingTime": null,
        "invoiceDelivery": null,
        "notifyBeforeWork": false,
        "archived": false,
        "agentIds": [],
        "meta": {
            "hairColor": "Brown"
        }
    },
    {  },
    {  },
    "... And then as many results as available or requested"

]
```

Returns a list of your contacts.

#### Arguments <a id="arguments"></a>

| Field | Optional | Explained |
| :--- | :--- | :--- |
| size | Yes | A limit on the number of objects to be returned. Size can range between 1 and 100 items. Default size is 20. |
| page | Yes | A zero-based cursor for use in pagination. Page is a number that defines your place in the list. For instance, if you make a list request and receive 100 objects, your subsequent call can set page=1 in order to fetch the next page of the list. |
| search | Yes | A free text search field. Cannot be used in combination with nearby. |
| nearby | Yes | Sorts the result by the distance to a given coordinate, fx. '?nearby=-7.437336444854736,62.11042750510291'. Cannot be used in combination with search. |

#### Returns <a id="returns"></a>

An array of up to limit contacts, starting after offset. Each entry in the array is a separate contact object. If no more contacts are available, the resulting array will be empty. This request should never return an error.

