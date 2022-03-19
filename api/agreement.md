# Agreement

An Agreement is when the [Organization](http://tech.previsto.com/#organization) and a [Contact](http://tech.previsto.com/#contact) has agreed upon a specific assignment to be completed for a specific sum of money. The Agreement can be for a single assignment or for a recurring assignment.

The agreements will automatically be reflected in [Assignment](http://tech.previsto.com/#assignment). For example if an Agreement has been a recurring interval each monday then the system will automatically generate assignments for that agreement each monday. The assignments can be changed as needed, but if the Agreement is updated, new assignments will be generated from that date and forward – overwriting any changes to the assignments.

#### Fixed planning <a href="#fixed-planning" id="fixed-planning"></a>

If `planningDateType` for an agreement is set to `Fixed` then `planningDate` defines a specific date for the next assignment. This is often used when a customer has been promised that the work will be fulfilled at a specific date or when existing customers are being created in Previsto for the first time.

If `recurrenceRule` is defined for an agreement with fixed planning, then `planningDateType` will automatically change to `Optimal` when work has ben marked as handled for this agreement. (See [Assignment](http://tech.previsto.com/#assignment))

#### Optimal planning <a href="#optimal-planning" id="optimal-planning"></a>

If `planningDateType` for an agreement is set to `Optimal` then `planningDate` is ignored. Based on historical data Previsto will create assignments according to the interval defined in `recurrenceRule`.

If no historical data for the agreement exists yet then Previsto will look for a day within the next month that has work planned close to the contact of the agreement.

#### Supplementary agreements <a href="#supplementary-agreements" id="supplementary-agreements"></a>

By default the `type` of agreement will be `Primary`, but it can also be specified as `Supplementary`. `Supplementary` agreements will only generate assignments together with `Primary`assignments at the same Contact. Previsto will find the assignment at the Contact closest to the optimal date and plan it together with it.

This makes it possible to define work that should never be planned by itself, but only when other primary work is planned also. For example a Window Cleaner might clean windows of a house both inside and outside. If the inside windows are done with another interval than the outside windows then 2 agreements should be created to define those intervals. But the window cleaner would want the cleaning of the inside windows to always be planned together with cleaning of the outside windows. He can make sure of that by defining the cleaning of the outside windows as `Primary` and cleaning of the inside windows as `Supplementary`.

### The agreement object <a href="#the-agreement-object" id="the-agreement-object"></a>

> Example Response

```
{
    "id": "agt_123123123",
    "description": "Window Cleaning",
    "note": "Remember to close the gate.",
    "amount": 23900,
    "contactId": "cont_1231231321",
    "recurrenceRule": "FREQ=WEEKLY;INTERVAL=4;WKST=MO",
    "type": "Primary",
    "workType": "WindowCleaning",
    "duration": 15,
    "planningDateType": "Fixed",
    "planningDate": "2017-12-04",
    "archived": false,
    "meta": {
        "Note": "Good Deal"
    }
}
```

| Field            | Type    | Required | Description                                                                                                                                            |
| ---------------- | ------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| id               | string  | No       | -                                                                                                                                                      |
| description      | string  | Yes      | Short public description of the agreement. Will be used invoices etc.                                                                                  |
| note             | string  | Yes      | Private description of the agreement. Message only to be shown to employees.                                                                           |
| amount           | number  | No       | The amount agreed upon in 1⁄100 of the monetary unit (fx. cents or øre)                                                                                |
| contactId        | string  | Yes      | The contact that has entered into agreement with.                                                                                                      |
| recurrenceRule   | string  | No       | The iCal(RFC 2445) RRule specifying optional reccurence.                                                                                               |
| type             | string  | No       | The type of agreement. 'Primary'(default) or 'Supplementary'.                                                                                          |
| workType         | string  | No       | The type of work. Currently only 'WindowCleaning'.                                                                                                     |
| duration         | number  | Yes      | The expected duration in minutes of the work. Minimum 3 minutes.                                                                                       |
| planningDateType | string  | No       | The type of planning for this agreement. 'Fixed' to specifiy a specific date for next planning or 'Optimal' to have the system find most optimal date. |
| planningDate     | date    | No       | If planningDateType is 'Fixed' then this property defines the date, otherwise ignored.                                                                 |
| archived         | boolean | No       | -                                                                                                                                                      |
| meta             | object  | No       | Dictionary of meta value.                                                                                                                              |

### Create an agreement <a href="#create-an-agreement" id="create-an-agreement"></a>

> Definition

```
POST https://api.previsto.io/agreements
`
```

> Example Request

```
curl https://api.previsto.io/agreements \
   -u sk_12345: \
   -d description="Window Cleaning" \
   -d contactId=cot_1231233123 \
   -d meta[note]="Good Deal"
```

> Example Response

```
{
    "id": "agt_123123123",
    "description": "Window Cleaning",
    "note": "Remember to close the gate.",
    "amount": 23900,
    "contactId": "cont_1231231321",
    "recurrenceRule": "FREQ=WEEKLY;INTERVAL=4;WKST=MO",
    "type": "Primary",
    "workType": "WindowCleaning",
    "duration": 15,
    "planningDateType": "Fixed",
    "planningDate": "2017-12-04",
    "archived": false,
    "meta": {
        "Note": "Good Deal"
    }
}
```

Creates a new agreement.

#### Arguments <a href="#arguments" id="arguments"></a>

| Field          | Type   | Required | Description                                                |
| -------------- | ------ | -------- | ---------------------------------------------------------- |
| description    | string | No       | Short description of the agreement.                        |
| amount         | number | No       | The amount agreed upon.                                    |
| currency       | string | Yes      | 3-letter ISO 4217 code, fx. 'DKK'                          |
| contactId      | string | Yes      | The contact that has entered into agreement with.          |
| recurrenceRule | string | No       | The iCal(RFC 2445) RRule specifying optional reccurence.   |
| startDate      | date   | Yes      | The start of the agreement.                                |
| endDate        | date   | No       | The end of the agreement.                                  |
| previousDate   | date   | no       | The previous date work was done, if any.                   |
| nextDate       | date   | No       | The next date to accomplish work, if planned.              |
| accountId      | string | No       | Id of the employee that is the caretaker of the agreement. |
| meta           | object | No       | Dictionary of meta value.                                  |

#### Returns <a href="#returns" id="returns"></a>

Returns an agreement object if the call succeeded. If a invalid parameters are provided, the call will return an error.

### Retrieve an agreement <a href="#retrieve-an-agreement" id="retrieve-an-agreement"></a>

> Definition

```
GET https://api.previsto.io/agreements/{AGREEMENT_ID}
```

> Example Request

```
curl https://api.previsto.io/agreements/agt_123123123 \
   -u sk_12345:
```

> Example Response

```
{
    "id": "agt_123123123",
    "description": "Window Cleaning",
    "note": null,
    "amount": 23900,
    "contactId": "cont_1231231321",
    "recurrenceRule": "FREQ=WEEKLY;INTERVAL=4;WKST=MO",
    "type": "Primary",
    "workType": "WindowCleaning",
    "duration": 15,
    "planningDateType": "Fixed",
    "planningDate": "2017-12-04",
    "archived": false,
    "meta": {
        "Note": "Good Deal"
    }
}
```

Retrieves the details of an existing agreement. You need only supply the unique agreement identifier that was returned with the agreement object upon a successfull creation.

#### Arguments <a href="#arguments" id="arguments"></a>

| Field | Type   | Required | Description                                      |
| ----- | ------ | -------- | ------------------------------------------------ |
| id    | string | Yes      | The identifier of the agreement to be retrieved. |

#### Returns <a href="#returns" id="returns"></a>

Returns an agreement object if a valid identifier was provided.

### Update an agreement <a href="#update-an-agreement" id="update-an-agreement"></a>

> Definition

```
POST https://api.previsto.io/agreements/{AGREEMENT_ID}
```

> Example Request

```
curl https://api.previsto.io/agreements/agt_123123123 \
   -u sk_12345: \
   -d description="Window Cleaning Outside"
```

> Example Response

```
{
    "id": "agt_123123123",
    "description": "Window Cleaning Outside",
    "note": null,
    "amount": 23900,
    "contactId": "cont_1231231321",
    "recurrenceRule": "FREQ=WEEKLY;INTERVAL=4;WKST=MO",
    "type": "Primary",
    "workType": "WindowCleaning",
    "duration": 15,
    "planningDateType": "Fixed",
    "planningDate": "2017-12-04",
    "archived": false,
    "meta": {
        "Note": "Good Deal"
    }
}
```

Updates the specified agreement by setting the values of the parameters passed. Any parameters not provided will be left unchanged. For example, if you pass the amount parameter, that becomes the agreements's new amount.

This request accepts mostly the same arguments as the agreement creation call.

#### Arguments <a href="#arguments" id="arguments"></a>

| Field          | Type   | Required | Description                                                |
| -------------- | ------ | -------- | ---------------------------------------------------------- |
| description    | string | No       | Short description of the agreement.                        |
| amount         | number | No       | The amount agreed upon.                                    |
| currency       | string | Yes      | 3-letter ISO 4217 code, fx. 'DKK'                          |
| contactId      | string | Yes      | The contact that has entered into agreement with.          |
| recurrenceRule | string | No       | The iCal(RFC 2445) RRule specifying optional reccurence.   |
| startDate      | date   | No       | The start of the agreement.                                |
| endDate        | date   | No       | The end of the agreement.                                  |
| accountId      | string | No       | Id of the employee that is the caretaker of the agreement. |
| meta           | object | No       | Dictionary of meta value.                                  |
| type           | string | No       | Type of agreement. 'Primary' or 'Supplementary'.           |

#### Returns <a href="#returns" id="returns"></a>

Returns the agreement object if the update succeeded. Returns [an error](http://tech.previsto.com/#errors) if update parameters are invalid.

### Delete an agreement <a href="#delete-an-agreement" id="delete-an-agreement"></a>

> Definition

```
DELETE https://api.previsto.io/agreements/{AGREEMENT_ID}
```

> Example Request

```
curl https://api.previsto.io/agreements/agt_123123123 \
   -u sk_12345: \
   -X DELETE
```

Permanently deletes an agreement. It cannot be undone.

#### Arguments <a href="#arguments" id="arguments"></a>

| Field | Type   | Required | Description                                    |
| ----- | ------ | -------- | ---------------------------------------------- |
| id    | string | Yes      | The identifier of the agreement to be deleted. |

#### Returns <a href="#returns" id="returns"></a>

Returns an empty response upon success. If the agreement ID does not exist, this call returns an error.

### List all agreements <a href="#list-all-agreements" id="list-all-agreements"></a>

> Definition

```
GET https://api.previsto.io/agreements
```

> Example Request

```
curl https://api.previsto.io/agreements \
   -u sk_12345:
```

> Example Response

```
[
    {
        "id": "agt_123123123",
        "description": "Window Cleaning Outside",
        "amount": 23900,
        "currency": "DKK",
        "contactId": "cot_1231231321",
        "recurrenceRule": "FREQ=WEEKLY;INTERVAL=4;WKST=MO",
        "startDate": "2015-01-01",
        "endDate": null,
        "previousDate": null,
        "nextDate": null,
        "archived": false,
        "accountId": null,
        "meta": {
            "note": "Good Deal"
        }
    },
    {  },
    {  },
    "... And then as many results as available or requested"

]
```

Returns a list of your agreements.

#### Arguments <a href="#arguments" id="arguments"></a>

| Field | Optional | Explained                                                                                                                                                                                                                                           |
| ----- | -------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| size  | Yes      | A limit on the number of objects to be returned. Size can range between 1 and 100 items. Default size is 20.                                                                                                                                        |
| page  | Yes      | A zero-based cursor for use in pagination. Page is a number that defines your place in the list. For instance, if you make a list request and receive 100 objects, your subsequent call can set page=1 in order to fetch the next page of the list. |

#### Returns <a href="#returns" id="returns"></a>

An array of up to limit agreements, starting after offset. Each entry in the array is a separate agreement object. If no more agreements are available, the resulting array will be empty. This request should never return an error.
