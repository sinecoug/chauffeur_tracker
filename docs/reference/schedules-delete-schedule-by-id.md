---
layout: page
---
# Delete a schedule for a specific driver

Deletes a [`schedules`](schedules) object in the database.

For example, you want to delete schedule *Id=6* from the database.

Assumption: to delete the correct schedule, you must know the `Id` to query.

## URL

```shell

{server_url}/schedules/{id}
```

## Method

{DELETE}

## Query parameters

| Property | Description | Type | Required | Notes |
| -------------- | ------ | ------------ |------------ |------------ |
| `Id` | The record ID of the schedule to return.  | number | Required |  |

## Request headers

| Header name | Description | Required | Values |
| -------------- | ------ | ------------ |------------ |
| Basic Auth | A security checkpoint that requires transmission of a username and password with every request. | Required | Basic authentication is a simple authentication scheme that's built into the HTTP protocol. See the Quickstart > Security section.|

## Request body

None

## Return body

The sample response returns a schedule matching the specified `id`, and deletes the object in the database.

```js
[
   {
        "id": "6",
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

## Related information

* [Security](../get-started/quickstart.md#security)
