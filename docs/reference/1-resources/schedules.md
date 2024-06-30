---
layout: page
---

# `schedules` resource

Base endpoint:

```shell
{server_url}/schedule
```

Contains a driver's schedule, which includes their pick-up and drop-off commitments.

## Resource properties

Sample `schedules` resource

```js
{
    "driverId": "1",
    "title": "Baseball practice",
    "passenger": "Molly",
    "pickupLocation": "123 Main St, Springfield",
    "dropoffLocation": "456 Elm St, Springfield",
    "pickupTime": "2024-06-15T08:00:00Z",
    "dropoffTime": "2024-06-15T08:30:00Z",
     "status": "Scheduled",
    "id": 1
}
```

| Property | Description | Type | Required | Notes |
| -------------- | ------ | ------------ |------------ |------------ |
| `driverId` | The ID of the driver resource to which this schedule is assigned. | number | Required |  |
| `title` | The title or short description of the driving schedule. | number | Required | Example: Vet visit, School run. |
|`passenger` | Who the driver is to transport. | string | Required |  |
| `pickupLocation` | Where the driver is to pick up a passenger. | string | Required |  |
| `dropoffLocation` | Where the driver is to drop off a passenger. | string | Required |  |
| `pickupTime` | When the driver is to pick up a passenger. | string | Required | The [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format of the date and time: YYYY-MM-DDTHH:MM:SS |
| `dropoffTime` | When the driver is to drop off a passenger. | string | Required | The [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format of the date and time: YYYY-MM-DDTHH:MM:SS |
| `status` | The status of the driving schedule. | string | Required |Allowed status values are *Scheduled*, *Canceled*, *Rescheduled*. |
| `id` | The driving schedule's unique record ID. | number | Required |  |

## Operations

The `schedules` resource supports these operations.

### RETRIEVE (GET)

* [Retrieve all schedules](../2-operations/schedules-get-all-schedules.md)
* [Retrieve schedules for a specific driver](../2-operations/schedules-get-schedule-by-id.md)
* [Retrieve schedules by property](../2-operations/schedules-get-schedule-by-property.md)

### CREATE (POST)

* [Create a schedule](../2-operations/schedules-create-schedule.md)

### UPDATE (PUT/PATCH)

* [Update a schedule for a specific driver](../2-operations/schedules-update-schedule-by-id.md)
* [Update a schedule by property](../2-operations/schedules-update-schedule-by-property.md)

### DELETE

* [Delete a schedule for a specific driver](../2-operations/schedules-delete-schedule-by-id.md)
