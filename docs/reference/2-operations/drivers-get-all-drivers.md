---
layout: page
---
# Retrieve all drivers

Returns an array of [`drivers`](../1-resources/drivers.md) objects who are registered with the service.

## URL

```shell

{server_url}/drivers/
```

## Method

{GET}

## Query parameters

None

## Request headers

| Header name | Description | Required | Values |
| -------------- | ------ | ------------ |------------ |
| Basic Auth | A security checkpoint that requires transmission of a username and password with every request. | Required | Basic authentication is a simple authentication scheme that's built into the HTTP protocol. See the Quickstart > Security section.|

## Request body

None

## Return body

```js
[
    {
        "driverName": "Faith Jaxon",
        "driverIdentity": "Mom",
        "cellPhone": "(555)555-1234",
        "email": "f.smith@gmail.com",
        "id": "1"
    },
    {
        "driverName": "Aiden Issac",
        "driverIdentity": "Dad",
        "cellPhone": "(555)555-7954",
        "email": "a.issac@gmail.com",
        "id": "2"
    },
    {
        "driverName": "Melanie Griffiths",
        "driverIdentity": "Neighbor",
        "cellPhone": "(555)794-4321",
        "email": "m.griffiths@gmail.com",
        "id": "3"
    }
    ...
]
```

## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | Success | Requested data returned successfully |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |

## Related information

* [Security](../../get-started/2-quickstart.md#security)
