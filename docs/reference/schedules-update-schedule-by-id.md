---
layout: page
---

# Update a schedule for a specific driver

Updates a driver's [`schedules`](schedules) object in the database.

For example, you want to update properties associated with schedule *id=6* in the database.

Assumption: to update the correct schedule, you must know the schedule `Id` to query.

The request body contains the updated schedule details.

## URL

```shell

{PUT}{server_url}/schedules/{id}
```

## Query parameters

| Property | Description | Type | Required | Notes |
| -------------- | ------ | ------------ |------------ |------------ |
| `Id` | The record ID of the schedule to return.  | number | Required |  |

## Request headers

| Header name | Description | Required | Values |
| -------------- | ------ | ------------ |------------ |
| Basic Auth | A security checkpoint that requires transmission of a username and password with every request. | Required | Basic authentication is a simple authentication scheme that's built into the HTTP protocol. See the Quickstart > Security section.|
| Content-Type | The format of the data to be posted. | Optional | application/json. Default value.  |
| Accept | The format of the data to be returned. | Optional | application/json. Default value. |

## Request body

In the request body, specify a JSON representation of the [`schedule`](schedules) object. The following table lists the properties that are required when you create a schedule.

---

**IMPORTANT:**
With a {PUT} call, the request body replaces the current properties of the [`schedules`](schedules) object.

To update/replace single property instances in the [`schedules`](schedules) object, use a {PATCH} call in your [schedules request](schedules-update-schedule-by-property.md).

---

| Property | Description | Type | Required | Notes |
| -------------- | ------ | ------------ |------------ |------------ |
| `driverID` | The ID of the driver resource to which this schedule is assigned. | number | Required |  |
| `passenger` | Who the driver is to transport. | string | Required |  |
| `pickupLocation` | Where the driver is to collect a passenger. | string | Required |  |
| `dropoffLocation` | Where the driver is to drop off a passenger. | string | Required |  |
| `pickupTime` | When the driver is to collect a passenger. | date-time | Required | The [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format of the date and time. |
| `dropoffTime` | When the driver is to drop off a passenger. | date-time | Required | The [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format of the date and time. |
| `status` | The status of the driving schedule. | string | Required |Allowed status values are *Scheduled*, *Canceled*, *Rescheduled*. |
| `id` | The driving schedule's unique record ID.  | number | Required |  |

## Sample request

The PUT body should look something like this. You can change the values of each property as you’d like.

```js
[
      {
        "id": "6",
        "driverID": "5",
        "title": "'Birthday party",
        "passenger": "Johnny & Molly, Frankie & Jill",
        "pickupLocation": "123 Main St, Springfield",
        "dropoffLocation": "Omniplex, 112 Baker St, Springfield",
        "pickupTime": "2024-07-09T19:30:00Z",
        "dropoffTime": "2024-07-09T23:00:00Z",
        "status": "Unscheduled"
    }
]
```

## Return body

The following example shows the response. Note that the names should be the same as you used in your **Request body** and the response should include the schedule id. The schedule id is automatically generated when the schedule is created.

```js
[
    {
        "id": "6",
        "driverID": "5",
        "title": "Birthday party",
        "passenger": "Johnny & Molly, Frankie and Jill",
        "pickupLocation": "123 Main St, Springfield",
        "dropoffLocation": "Omniplex, 112 Baker St, Springfield",
        "pickupTime": "2024-07-09T19:30:00Z",
        "dropoffTime": "2024-07-09T23:00:00Z",
        "status": "Unscheduled"
    }
]
```

## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | Updated | Driving schedule updated successfully. |
| 500 | Internal server Error | Invalid JSON. |
| ECONNREFUSED | N/A | Service is offline. Start the service and try again. |

## Related information

* [Quickstart guide > Security](../get-started/quickstart.md)
