---
layout: page
---
# Retrieve a specific driver

Returns an array of [`drivers`](drivers) objects for the specified `driverId`, if it exists.

For example, you want to retrieve *driverId=1* from the database.

Assumption: to return the correct driver, you must know the `driverId` to query.

## URL

```shell

{GET}{server_url}/drivers/{id}
```

## Query parameters

| Property | Description | Type | Required | Notes |
| -------------- | ------ | ------------ |------------ |------------ |
| `driverId` | The record ID of the driver to return.  | number | Required |  |

---

**NOTE:**
To retrieve a driver by cell phone number or other property, further filter your [drivers request](drivers-get-driver-by-property.md).

---

## Request headers

| Header name | Description | Required | Values |
| -------------- | ------ | ------------ |------------ |
| Basic Auth | A security checkpoint that requires transmission of a username and password with every request. | Required | Basic authentication is a simple authentication scheme that's built into the HTTP protocol. See the Quickstart > Security section.|

## Request body

None

## Return body

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

## Related information

* [Quickstart guide > Security](../get-started/quickstart.md)
