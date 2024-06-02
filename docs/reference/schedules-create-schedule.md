---
layout: page
---

# Create a schedule

Creates a driver's pick-up and drop-off [`schedules`](schedules).
The request body contains the new schedule details.
You must specify the required properties for the schedule.

## URL

```shell

{POST}{server_url}/schedules/
```

## Request headers

This request does not use any authorization. The endpoint is available to all users and applications.

| Header name | Description | Required | Values |
| -------------- | ------ | ------------ |------------ |
| Content-Type | The format of the data to be posted. | Optional | application/json. Default value.  |
| Accept | The format of the data to be returned. | Optional | application/json. Default value. |

## Request body

In the request body, specify a JSON representation of the [`schedule`](schedules) object. The following table lists the properties that are required when you create a schedule.

| Property | Description | Type | Required | Notes |
| -------------- | ------ | ------------ |------------ |------------ |
| `driverId` | The ID of the driver resource to which this schedule is assigned. | number | Required |  |
| `title` | The title or short description of the driving schedule. | number | Required | Example: Vet visit, School run. |
|`passenger` | Who the driver is to transport. | string | Required |  |
| `pickupLocation` | Where the driver is to pick up a passenger. | string | Required |  |
| `dropoffLocation` | Where the driver is to drop off a passenger. | string | Required |  |
| `pickupTime` | When the driver is to pick up a passenger. | date-time | Required | The [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format of the date and time. |
| `dropoffTime` | When the driver is to drop off a passenger. | date-time | Required | The [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format of the date and time. |
| `status` | The status of the driving schedule. | string | Required | Allowed status values are *Scheduled*, *Canceled*, *Rescheduled*. |
| `id` | The driving schedule's unique record ID. | number | Required | The schedule id is auto-generated. See the return body. |

## Sample request

The POST body should look something like this. You can change the values of each property as you’d like.

```js
[
     {
        "driverID": "5",
        "title": "Cinema night",
        "passenger": "Johnny & Molly",
        "pickupLocation": "123 Main St, Springfield",
        "dropoffLocation": "Omniplex, 112 Baker St, Springfield",
        "pickupTime": "2024-07-09T19:30:00Z",
        "dropoffTime": "2024-07-09T23:00:00Z",
        "status": "Scheduled"
    }
]
```

## Return body

The following example shows the response. Note that the names should be the same as you used in your **Request body** and the response should include the new schedule id. The schedule id is automatically generated when the schedule is created.

```js
[
    {
        "id": "6",
        "driverID": "5",
        "title": "Cinema night",
        "passenger": "Johnny & Molly",
        "pickupLocation": "123 Main St, Springfield",
        "dropoffLocation": "Omniplex, 112 Baker St, Springfield",
        "pickupTime": "2024-07-09T19:30:00Z",
        "dropoffTime": "2024-07-09T23:00:00Z",
        "status": "Scheduled"
    }
]
```

## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 201 | Created | Driving schedule created successfully. |
| 500 | Internal server Error | Invalid JSON. |
| ECONNREFUSED | N/A | Service is offline. Start the service and try again. |

## Related information

* [Tutorial: Create a driver's schedule](../tutorials/how-to-create-a-driver-schedule.md)
