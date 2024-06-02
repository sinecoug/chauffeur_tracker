---
layout: page
---

# Update a schedule for a specific driver

Updates a driver's pick-up and drop-off [`schedules`](schedules).
The request body contains the updated driving schedule details.
You must specify the required properties for the user.

## URL

```shell

{PUT}{server_url}/schedules/
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
| `driverID` | The ID of the driver resource to which this schedule is assigned. | number | Required |  |
| `passenger` | Who the driver is to transport. | string | Required |  |
| `pickupLocation` | Where the driver is to collect a passenger. | string | Required |  |
| `dropoffLocation` | Where the driver is to drop off a passenger. | string | Required |  |
| `pickupTime` | When the driver is to collect a passenger. | date-time | Required | The [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format of the date and time. |
| `dropoffTime` | When the driver is to drop off a passenger. | date-time | Required | The [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format of the date and time. |
| `status` | The status of the driving schedule. | string | Required |  |
| `id` | The driving schedule's unique record ID.  | number | Required |  |

## Sample request

The PUT body should look something like this. You can change the values of each property as you’d like.

```js
[
      {
        "id": "0f50",
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

## Return body

The following example shows the response. Note that the names should be the same as you used in your **Request body** and the response should include the new schedule id. The schedule id is automatically generated when the schedule is created.

```js
[
    {
        "id": "0f50",
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

* [Handling errors](handling-errors.md)