---
layout: page
---

# `schedule` resource

Base endpoint:

```shell
{server_url}/schedule
```

Contains a family member's driving schedule, which includes their pick-up and drop-off commitments.

## Resource properties

Sample `schedule` resource

```js
{
    "familyMemberName": "Faith Jaxon",
    "pickupLocation": "123 Main St, Springfield",
    "dropoffLocation": "456 Elm St, Springfield",
    "pickupTime": "2024-06-15T08:00:00Z",
    "dropoffTime": "2024-06-15T08:30:00Z",
     "status": "Scheduled",
    "scheduleid": 1
}
```

| Property | Description | Type | Required | Notes |
| -------------- | ------ | ------------ |------------ |------------ |
| `familyMemberName` | The driver's full name. | string | Required |  |
| `pickupLocation` | Where the driver is to collect a passenger. | string | Required |  |
| `dropoffLocation` | Where the driver is to drop off a passenger. | string | Required |  |
| `pickupTime` | When the driver is to collect a passenger. | date-time | Required | The [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format of the date and time. |
| `dropoffTime` | When the driver is to drop off a passenger. | date-time | Required | The [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format of the date and time. |
| `status` | The status of the driving schedule. | string | Required |  |
| `scheduleid` | The unique ID of the driving schedule. | number | Required |  |

## Operations

The `schedule` resource supports these operations.

### RETRIEVE (GET)

### CREATE (POST)

### UPDATE (PUT/PATCH)

### DELETE
