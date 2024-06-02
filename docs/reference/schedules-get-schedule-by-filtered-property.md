---
layout: page
---
# Retrieve schedules for a specific property

Returns an array of driving [`schedules`](schedules) objects for specified query parameters.
Assumption: to return the correct schedule, you must know the property to query.
For example, you might want to filter responses by 'title' to return a driver's "School run" or "Vet visit" schedules.

## URL

```shell

{GET}{server_url}/schedules/
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
        "driverId": "1",
        "title": "School run",
        "passenger": "Molly",
        "pickupLocation": "789 Oak St, Anytown",
        "dropoffLocation": "321 Maple St, Anytown",
        "pickupTime": "2024-06-16T09:00:00Z",
        "dropoffTime": "2024-06-16T09:30:00Z",
        "status": "Scheduled",
        "id": "2"
    },
    {
        "driverId": "3",
        "title": "Swimfest",
        "passenger": "Molly",
        "pickupLocation": "123 Main St, Springfield",
        "dropoffLocation": "110 Nassau St, Springfield",
        "pickupTime": "2024-07-22T08:00:00Z",
        "dropoffTime": "2024-07-22T08:30:00Z",
        "status": "Scheduled",
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
