---
layout: page
---
# Delete a specific driver

Deletes a [`drivers`](drivers) object in the database.

For example, you want to delete *driverId=4* from the database.

Assumption: to delete the correct driver, you must know the `driverId` to query.

## URL

```shell

{DELETE}{server_url}/drivers/{id}
```

## Query parameters

| Property | Description | Type | Required | Notes |
| -------------- | ------ | ------------ |------------ |------------ |
| `driverID` | The record ID of the driver to delete.  | number | Required |  |

## Request headers

| Header name | Description | Required | Values |
| -------------- | ------ | ------------ |------------ |
| Basic Auth | A security checkpoint that requires transmission of a username and password with every request. | Required | Basic authentication is a simple authentication scheme that's built into the HTTP protocol. See the Quickstart > Security section.|

## Request body

None

## Return body

The sample response returns a driver matching the specified `id`, and deletes the object in the database.

```js
[
    {
        "driverName": "SallyAnn Issac",
        "driverIdentity": "Nana",
        "cellPhone": "(555)555-9874",
        "email": "s.issac@gmail.com",
        "id": "fd05"
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

* [Quickstart guide > Security](../get-started/quickstart.md)
