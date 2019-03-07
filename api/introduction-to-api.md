---
description: Integrate with Previsto using our Rest Api.
---

# Introduction to Api

Welcome to the [Previsto](http://previsto.io/) API documentation. This is the API used by the official Previsto web interface as well as our Mobile App, so everything the web ui is able to do can also be accomplished via the API.

The Previsto API is organized around [REST](http://en.wikipedia.org/wiki/Representational_State_Transfer). Our API is designed to have predictable, resource-oriented URLs and to use HTTP response codes to indicate API errors. We use built-in HTTP features, like HTTP authentication and HTTP verbs, which can be understood by off-the-shelf HTTP clients, and we support cross-origin resource sharing to allow you to interact securely with our API from a client-side web application \(though you should remember that you should never expose your secret API key in any public website's client-side code\). JSON will be returned in all GET, PUT and POST responses from the API, including errors. Only exception is DELETE requests which returns an empty response upon success.

#### Feedback <a id="feedback"></a>

We would love your feedback at any time. Contact us at [support@previsto.com](mailto:support@previsto.com).

### Authentication <a id="authentication"></a>

> Example Request

```text
$ curl https://api.previsto.io/account \
   -u sk_12345:
```

You authenticate to the Previsto API by providing one of your API keys in the request. You can manage your API keys from your account. You can have multiple API keys active at one time. Your API keys carry many privileges, so be sure to keep them secret!

Authentication to the API occurs via a Token given in the HTTP headers. Provide your API key as the username of Basic Authentication.

All API requests must be made over HTTPS. Calls made over plain HTTP will fail. You must authenticate for all requests.

### HTTP Status Codes <a id="http-status-codes"></a>

Previsto uses conventional HTTP response codes to indicate success or failure of an API request. In general, codes in the 2xx range indicate success, codes in the 4xx range indicate an error that resulted from the provided information \(e.g. a required parameter was missing etc.\), and codes in the 5xx range indicate an error with Previsto's servers.

#### HTTP Status Code Summary <a id="http-status-code-summary"></a>

| HTTP Code | Meaning |
| :--- | :--- |
| 200 - OK | Everything worked as expected. |
| 400 - Bad Request | Often missing a required parameter. |
| 401 - Unauthorized | No valid API key provided. |
| 402 - Request Failed | Parameters were valid but request failed. |
| 403 - Forbidden | Action not allowed for provided API key. |
| 404 - Not Found | The requested item doesn't exist. |
| 429 - Too many requests | Request limit exceeded. |
| 500, 502, 503, 504 - Server Errors | Something went wrong on Previsto's end. |

### Errors <a id="errors"></a>

> Example Response

```text
{
    "type": "invalid_request",
    "message": "'name' must be specified.",
    "param": "name"
}
```

When an error occurs the response will always contain a JSON object as shown to the right. The following is the explanation of the Error object.

#### Attributes <a id="attributes"></a>

| Field | Optional | Explained |
| :--- | :--- | :--- |
| type | No | The type of error returned. Can be invalid\_request\_error or api\_error |
| message | Yes | A human-readable message giving more details about the error. |
| param | Yes | The parameter the error relates to if the error is parameter-specific. You can use this to display a message near the correct form field, for example. |

#### Types <a id="types"></a>

| Value | Explained |
| :--- | :--- |
| invalid\_request\_error | Invalid request errors arise when your request has invalid parameters. |
| api\_error | API errors cover any other type of problem \(e.g. a temporary problem with Previsto's servers\) and should turn up only very infrequently. |

### Request Limit <a id="request-limit"></a>

The Previsto API will rate limit requests on a per-API key basis. Each key will by default have **a limit of 120 requests per minute**. If you exceed your rate limit you will receive an API response with a 429 HTTP status code and a brief message indicating you have exceeded your rate limit.

To increase your rate limit, contact sales.

### Pagination <a id="pagination"></a>

All top-level Previsto API resources have support for bulk fetches — "list" API methods. For instance you can list contacts, list assignments, and list agreements. These list API methods share a common structure. Previsto utilizes cursor-based pagination, using the parameter page. Pass page to dictate where in the list you would like to begin \(see below\).

#### Arguments <a id="arguments"></a>

| Field | Optional | Explained |
| :--- | :--- | :--- |
| size | Yes | Size of page. Defines the number of objects to be returned. Size can range between 1 and 100 items. Default limit is 20. |
| page | Yes | A zero-based cursor for use in pagination. Page is a number that defines your place in the list. For instance, if you make a list request and receive 100 objects, your subsequent call can set page=1 in order to fetch the next page of the list. |

### Filtering <a id="filtering"></a>

All top-level Previsto API resources have support for filtering by its properties. All properties can be used as a query parameter and simple equality methods are available. The example to the right shows how to request assignments that has been invoiced.

```text
curl https://api.previsto.io/assignments?status=Invoiced \
   -u sk_12345:
```

### Sorting <a id="sorting"></a>

All top-level Previsto API resources have support for sorting by its properties. Sorting can be done ascending or descending. The example to the right shows how to request assignments sorted by its timestamp in descending order.

```text
curl https://api.previsto.io/assignments?sort=timestamp,desc \
   -u sk_12345:
```

### Metadata <a id="metadata"></a>

Most updatable Previsto objects support a user-specified metadata parameter.

You can use the metadata parameter to attach key-value data. This is useful for storing additional structured information about an object. As an example, you could store your user's full name, favorite color, and their corresponding unique identifier from your system on a Previsto customer object.

Note: You can have up to 20 keys, with key names up to 40 characters long and values up to 500 characters long.

