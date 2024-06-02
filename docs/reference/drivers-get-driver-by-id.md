---
layout: page
---
# Retrieve a specific driver

Retrieves a specific driver's pick-up and drop-off schedule.
Returns an array of driving [`schedules`](schedules) objects for the specified driverId.
Assumption: to return the correct driver, you must know the driverId to query.

## URL

```shell

{GET}{server_url}/drivers/
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
    "driverName": "Faith Jaxon",
    "driverIdentity": "Mom",
    "cellPhone": "(555)555-1234",
    "email": "f.smith@gmail.com",
    "id": "1"
   }
    ...
]
```

## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | Success | Requested data returned successfully |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |
