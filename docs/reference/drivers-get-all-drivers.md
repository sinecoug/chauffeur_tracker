---
layout: page
---
# Retrieve all drivers

Returns an array of driving [`drivers`](drivers) objects who are registered with the service.

## URL

```shell

{GET}{server_url}/drivers/
```

## Params

None

## Request headers

None

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
