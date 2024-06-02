---
layout: page
---
# Retrieve schedules for a specific driver

Retrieves a specific driver's pick-up and drop-off schedule.
Returns an array of driving [`schedules`](schedules) objects for the specified driverId.
Assumption: to return the correct driver, you must know the driverId to query.

## URL

```shell

{GET}{server_url}/schedules/
```

## Query parameters

Assumption: you must know the id parameter of the driver you want to retrieve.

| Property | Description | Type | Required | Notes |
| -------------- | ------ | ------------ |------------ |------------ |
| `driverID` | The ID of the driver resource you want to retrieve. | number | Required |  |

---

**NOTE:**
To retrieve a driver's schedule by title or other property, further filter your [schedules request] properties.(schedules-get-schedule-by-filtered-property.md).

## Request headers

None

## Request body

None

## Return body

The following example shows the response.

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
        "driverId": "1",
        "title": "Vet visit",
        "passenger": "Minnie",
        "pickupLocation": "123 Main St, Springfield",
        "dropoffLocation": "12 Animal Drive, Springfield",
        "pickupTime": "2024-08-08T08:00:00Z",
        "dropoffTime": "2024-08-08T08:30:00Z",
        "status": "Scheduled"
    }
    ...
]
```

## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | Success | Requested data returned successfully |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |
