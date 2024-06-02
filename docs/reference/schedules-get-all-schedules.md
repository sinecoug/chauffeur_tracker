---
layout: page
---
# Retrieve all schedules

Returns an array of driving [`schedules`](schedules) objects for all drivers who are registered with the service.

## URL

```shell

{GET}{server_url}/schedules/
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
        "driverId": "2",
        "title": "Baseball practice",
        "passenger": "Richie",
        "pickupLocation": "123 Main St, Springfield",
        "dropoffLocation": "456 Elm St, Springfield",
        "pickupTime": "2024-06-15T08:00:00Z",
        "dropoffTime": "2024-06-15T08:30:00Z",
        "status": "Scheduled",
        "id": "1"
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
    },
    {
        "driverId": "1",
        "title": "Vet visit",
        "passenger": "Minnie",
        "pickupLocation": "123 Main St, Springfield",
        "dropoffLocation": "12 Animal Drive, Springfield",
        "pickupTime": "2024-08-08T08:00:00Z",
        "dropoffTime": "2024-08-08T08:30:00Z",
        "status": "Scheduled",
        "id": "4"
    }
    ...
]
```

## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | Success | Requested data returned successfully |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |
