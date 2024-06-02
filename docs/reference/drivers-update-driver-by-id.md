---
layout: page
---

# Update a specific driver

Updates a [`drivers`](drivers) object in the database.

For example, you want to update properties of *driverId=4* in the database.

Assumption: to update the correct driver, you must know the `driverId` to query.

The request body contains the updated driver's details.

## URL

```shell

{PUT}{server_url}/drivers/{id}
```

## Query parameters

| Property | Description | Type | Required | Notes |
| -------------- | ------ | ------------ |------------ |------------ |
| `driverId` | The record ID of the driver to return.  | number | Required |  |

---

**NOTE:**
{PUT} calls replace the [`drivers`](drivers) object. To update/replace single property instances in the [`drivers`](drivers) object, use a {PATCH} call in your [drivers request](drivers-update-driver-by-property.md).

---

## Request headers

This request does not use any authorization. The endpoint is available to all users and applications.

| Header name | Description | Required | Values |
| -------------- | ------ | ------------ |------------ |
| Content-Type | The format of the data to be posted. | Optional | application/json. Default value.  |
| Accept | The format of the data to be returned. | Optional | application/json. Default value. |

## Request body

In the request body, specify a JSON representation of the [`drivers`](drivers) object. The following table lists the properties that are required when you create a driver object.

| Property | Description | Type | Required | Notes |
| -------------- | ------ | ------------ |------------ |------------ |
| `driverName` | The driver's full name. | string | Required |  |
| `driverIdentity` | The driver's primary role in relationship to the family. | string | Optional |Examples: Mom, Dad, Neighbor.  |
| `cellPhone` | The driver's cell phone number. | string | Required |  |
| `email` | The driver's email address. | string | Required | A unique email is required. |
| `id` | The driver's unique record ID. | number | Required | The driver's id is auto-generated. See the return body. |

## Sample request

The PUT body should look something like this. You can change the values of each property as you’d like.

```js
[
    {
        "driverName": "SallyAnn Issac",
        "driverIdentity": "Gran",
        "cellPhone": "(555)555-9674",
        "email": "s.issac@gmail.com"
    }
]
```

## Return body

The following example shows the response. Note that the names should be the same as you used in your **Request body** and the response should include the updated driver's id. The driver's id is automatically generated when the schedule is created.

```js
[
    {
        "driverName": "SallyAnn Issac",
        "driverIdentity": "Gran",
        "cellPhone": "(555)555-9674",
        "email": "s.issac@gmail.com",
        "id": "4"
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
