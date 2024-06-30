---
layout: page
---

# Update a schedule by property

Updates and replaces property instances in the [`schedules`](schedules) object.

For example, you want to update properties of schedule *id=6* in the database.
Assumption: to update the correct schedule, you must know the schedule `Id` to query.

The request body contains the updated schedule details.

## URL

```shell

{server_url}/schedules/{id}
```

## Method

{PATCH}

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

In the request body, specify a JSON representation of the [`schedules`](schedules) object.

---

**IMPORTANT:**
With a {PATCH} call, the request body replaces specified properties of the [`schedules`](schedules) object.

To update/replace all the properties in the [`schedules`](schedules) object, use a {PUT} call in your [schedules request](schedules-update-schedule-by-id.md).

---

The following table lists the properties that you can update.

| Property | Description | Type | Required | Notes |
| -------------- | ------ | ------------ |------------ |------------ |
| `driverID` | The ID of the driver resource to which this schedule is assigned. | number | Required |  |
| `passenger` | Who the driver is to transport. | string | Required |  |
| `pickupLocation` | Where the driver is to collect a passenger. | string | Required |  |
| `dropoffLocation` | Where the driver is to drop off a passenger. | string | Required |  |
| `pickupTime` | When the driver is to collect a passenger. | string | Required |The [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format of the date and time: YYYY-MM-DDTHH:MM:SS |
| `dropoffTime` | When the driver is to drop off a passenger. | string | Required | The [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format of the date and time: YYYY-MM-DDTHH:MM:SS |
| `status` | The status of the driving schedule. | string | Required |Allowed status values are *Scheduled*, *Canceled*, *Rescheduled*. |
| `id` | The driving schedule's unique record ID.  | number | Required |  |

## Sample request

The PATCH body should look something like this. You can change the values of each property as you’d like.

```js
[
    {
        "title": "Birthday party celebration"
        "status": "Unscheduled"
    }
]
```

## Return body

The following example shows the response. Note that the names should be the same as you used in your **Request body** and the response should include the schedule id. The schedule id is automatically generated when the schedule is created.

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
]
```

## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | Updated | Driving schedule updated successfully. |
| 500 | Internal server Error | Invalid JSON. |
| ECONNREFUSED | N/A | Service is offline. Start the service and try again. |

## Related information

* [Tutorial: Change the status (property) of a driver's schedule](../../tutorials/how-to-change-a-driver-schedule-property.md)
* [Security](../../get-started/quickstart.md#security)
