---
layout: page
---
# Delete a schedule for a specific driver

Deletes a specific driver's pick-up and drop-off schedule.
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
        "id": "0f50",
        "driverID": "5",
        "title": "Birthday party celebration",
        "passenger": "Johnny & Molly, Frankie and Jill",
        "pickupLocation": "123 Main St, Springfield",
        "dropoffLocation": "Omniplex, 112 Baker St, Springfield",
        "pickupTime": "2024-07-09T19:30:00Z",
        "dropoffTime": "2024-07-09T23:00:00Z",
        "status": "Unscheduled"
    }
    ...
]
```

## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | Success | Requested data returned successfully |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |
