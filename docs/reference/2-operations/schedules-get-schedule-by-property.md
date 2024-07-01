---
layout: page
---
# Retrieve schedules by property

Returns an array of driving [`schedules`](../1-resources/schedules.md) objects for specified query parameters.

For example, to return drivers who are scheduled to drive *Molly*, query the property `passenger` to filter responses.

Assumption: to return the correct schedule, you must know the property to query.

## URL

```shell

{server_url}/schedules/?{property}={value}
```

## Method

{GET}

## Query parameters

Optionally, you can specify schedule properties as`Key/Value` query parameters. For example: `title/School run`. Note that property titles are case sensitive.

| Property | Description | Type | Required | Notes |
| -------------- | ------ | ------------ |------------ |------------ |
| `title` | The title or short description of the driving schedule. | number | Optional | Example: Vet visit, School run. |
|`passenger` | Who the driver is to transport. | string | Optional |  |
| `pickupLocation` | Where the driver is to pick up a passenger. | string | Optional |  |
| `dropoffLocation` | Where the driver is to drop off a passenger. | string | Optional |  |
| `status` | The status of the driving schedule. | string | Optional |Allowed status values are *Scheduled*, *Canceled*, *Rescheduled*. |

## Request headers

| Header name | Description | Required | Values |
| -------------- | ------ | ------------ |------------ |
| Basic Auth | A security checkpoint that requires transmission of a username and password with every request. | Required | Basic authentication is a simple authentication scheme that's built into the HTTP protocol. See the Quickstart > Security section.|

## Request body

None

## Sample request

The API call should look something like this. You can change the values of each property as you’d like.

```bash
{base_url}/schedules?passenger=Molly
```

## Return body

The sample response returns drivers' schedules matching the specified `passenger`.

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
        "driverId": "3",
        "title": "Swimfest",
        "passenger": "Molly",
        "pickupLocation": "123 Main St, Springfield",
        "dropoffLocation": "110 Nassau St, Springfield",
        "pickupTime": "2024-07-22T08:00:00Z",
        "dropoffTime": "2024-07-22T08:30:00Z",
        "status": "Scheduled",
        "id": "3"
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

* [Security](../../get-started/2-quickstart.md#security)
