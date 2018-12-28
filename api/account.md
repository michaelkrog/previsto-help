# Account

This is an object representing your Previsto account. You can retrieve it to see properties on the account like its current e-mail address etc. You are allowed to change parameters for your own account only.

The account object also holds information about the user's authorizations in the property 'roles'. There are 2 kinds of roles: \(1\) system-wide roles and \(2\) organization-specific roles. System-wide roles are prefixed with `ROLE_` and organization-specific roles are prefixed with `ORGROLE_`followed by the id of the specific organization.

### The account object <a id="the-account-object"></a>

> Example Response

```text
{
    "id": "acct_7B10MYfEnPp6r",
    "login": "john",
    "name": "John Dow",
    "email": "john@doe.com",
    "emailValidated": true,
    "address": "Kundevej 2",
    "appartment": null,
    "postalCode": "4321",
    "city": "Kundeby",
    "countryCode": "DK",
    "location": [11.543540954589844, 56.703469017862034],
    "languageCode": "da",
    "roles": [
        "ROLE_USER",
        "ORGROLE_org-ZW46jOjfA0rpDZ_USER"
    ],
    "meta": {
        "hairColor": "Brown"
    }
}
```

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| login | string | Yes | - |
| password | string | Yes | Cannot not be read. Can only be set via this property when account is created. |
| name | string | Yes | Full name of user |
| email | string | Yes | Must have email syntax, fx. 'john@doe.com' |
| emailValidated | boolean | No | - |
| languageCode | string | Yes | 2-letter ISO 639-1 code, fx. 'da' |
| address | string | No | Street and house number |
| appartment | string | No | Apartment, fx. '1. th.' |
| postalCode | string | No | - |
| city | string | No | - |
| countryCode | string | No | 2-letter ISO 3166-1 code, fx. 'DK' |
| location | number\[\] | Yes | Array of 2 numbers holding longitude and latitude in specified order according to geojson syntax. \(Fx. \[11.543540954589844, 56.703469017862034\]\) |
| roles | array | No | Array of user's system and organization roles. |
| meta | object | No | Dictionary of meta values. |

### Retrieve current account <a id="retrieve-current-account"></a>

> Definition

```text
GET https://api.previsto.io/accounts/current
```

> Example Request

```text
curl https://api.previsto.io/accounts/current \
   -u sk_12345:
```

> Example Response

```text
{
    "id": "acct_7B10MYfEnPp6r",
    "login": "john",
    "name": "John Dow",
    "email": "john@doe.com",
    "emailValidated": true,
    "address": "Kundevej 2",
    "postalCode": "4321",
    "city": "Kundeby",
    "countryCode": "DK",
    "location": [11.543540954589844, 56.703469017862034],
    "languageCode": "da",
    "roles": [
        "ROLE_USER",
        "ORGROLE_org-ZW46jOjfA0rpDZ_USER"
    ],
    "meta": {
        "hairColor": "Brown"
    }
}
```

Retrieves the details of the account.

#### Arguments <a id="arguments"></a>

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| id | string | Yes | The identifier of the account to be retrieved. |

#### Returns <a id="returns"></a>

Returns an account object if a valid identifier was provided.

### Update current account <a id="update-current-account"></a>

> Definition

```text
POST https://api.previsto.io/accounts/current
```

> Example Request

```text
curl https://api.previsto.io/accounts/current \
   -u sk_12345: \
   -d email=jane@doe.com
```

> Example Response

```text
{
    "id": "acct_7B10MYfEnPp6r",
    "login": "john",
    "name": "John Dow",
    "email": "jane@doe.com",
    "emailValidated": true,
    "address": "Kundevej 2",
    "postalCode": "4321",
    "city": "Kundeby",
    "countryCode": "DK",
    "location": [11.543540954589844, 56.703469017862034],
    "languageCode": "da",
    "roles": [
        "ROLE_USER",
        "ORGROLE_org-ZW46jOjfA0rpDZ_USER"
    ],
    "meta": {
        "hairColor": "Brown"
    }
}
```

Updates an account by setting the values of the parameters passed. Any parameters not provided will be left unchanged.

#### Arguments <a id="arguments"></a>

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| name | string | Yes | Full name of user |
| email | string | No | - |
| languageCode | string | No | 2-letter ISO 639-1 code, fx. 'da' |
| meta | object | No | Dictionary of meta values. |

#### Returns <a id="returns"></a>

Returns the account object if the update succeeded. Returns [an error](http://tech.previsto.com/#errors) if update parameters are invalid.

### Delete an account <a id="delete-an-account"></a>

> Definition

```text
DELETE https://api.previsto.io/accounts/{ACCOUNT_ID}
```

> Example Request

```text
curl https://api.previsto.io/accounts/acct_7B10MYfEnPp6r \
   -u sk_12345: \
   -X DELETE
```

Permanently deletes an account. It cannot be undone.

#### Arguments <a id="arguments"></a>

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| id | string | Yes | The identifier of the account to be deletes. |

#### Returns <a id="returns"></a>

Returns an empty response upon success. If the account ID does not exist, this call returns an error.

