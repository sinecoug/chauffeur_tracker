---
layout: page
---
# Retrieve schedules for a specific driver

Returns an array of [`schedules`](schedules) objects for a specified `driverId`, if it exists.

For example, you want to retrieve the driving schedule of *driverId=1* from the database.

Assumption: to return the correct driver's pick-up and drop-off schedule, you must know the `driverId` to query.

## URL

```shell

{GET}{server_url}/schedules/{driverId}
```

## Query parameters

| Property | Description | Type | Required | Notes |
| -------------- | ------ | ------------ |------------ |------------ |
| `driverId` | The record ID of the driver to return.  | number | Required |  |

---

**NOTE:**
To retrieve a driver's schedule by title or other property, further filter your [schedules request](schedules-get-schedule-by-property.md).

---

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

## Related information

* [Tutorial: Retrieve a driver's schedule](../tutorials/how-to-get-a-drivers-schedule.md)
