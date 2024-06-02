---
layout: page
---
# Retrieve drivers by property

Returns an array of driving [`drivers`](drivers) objects for specified query parameters.
Assumption: to return the correct schedule, you must know the property to query.
For example, you might want to filter responses by 'title' to return a driver's "School run" or "Vet visit" schedules.

## URL

```shell

{GET}{server_url}/drivers/
```

## Query parameters

| Property | Description | Type | Required | Notes |
| -------------- | ------ | ------------ |------------ |------------ |
| `title` | The title or short description of the driving schedule. | number | Optional | Example: Vet visit, School run. |
|`passenger` | Who the driver is to transport. | string | Optional |  |
| `pickupLocation` | Where the driver is to pick up a passenger. | string | Optional |  |
| `dropoffLocation` | Where the driver is to drop off a passenger. | string | Optional |  |
| `status` | The status of the driving schedule. | string | Optional |  |

## Request headers

None

## Request body

None

## Return body

The following example shows a response that filters driving schedules with a named passenger.

```js
[
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
