---
layout: page
---

# Update a driver by property

Updates and replaces property instances in the [`drivers`](drivers) object.

For example, you want to update a single property associated with *driverId=4* in the database.

Assumption: to update the correct driver, you must know the `driverId` to query.

The request body contains the updated driver's details.

## URL

```shell

{server_url}/drivers/{id}
```

## Method

{PATCH}

## Query parameters

| Property | Description | Type | Required | Notes |
| -------------- | ------ | ------------ |------------ |------------ |
| `driverId` | The record ID of the driver to return.  | number | Required |  |

## Request headers

| Header name | Description | Required | Values |
| -------------- | ------ | ------------ |------------ |
| Basic Auth | A security checkpoint that requires transmission of a username and password with every request. | Required | Basic authentication is a simple authentication scheme that's built into the HTTP protocol. See the Quickstart > Security section.|
| Content-Type | The format of the data to be posted. | Optional | application/json. Default value.  |
| Accept | The format of the data to be returned. | Optional | application/json. Default value. |

## Request body

In the request body, specify a JSON representation of the [`drivers`](drivers) object.

---

**IMPORTANT:**
With a {PATCH} call, the request body replaces specified properties of the [`drivers`](drivers) object.

To update/replace all the properties in the [`drivers`](drivers) object, use a {PUT} call in your [drivers request](drivers-update-driver-by-id.md).

---

The following table lists the properties that you can update.

| Property | Description | Type | Required | Notes |
| -------------- | ------ | ------------ |------------ |------------ |
| `driverName` | The driver's full name. | string | Required |  |
| `driverIdentity` | The driver's primary role in relationship to the family. | string | Optional |Examples: Mom, Dad, Neighbor.  |
| `cellPhone` | The driver's cell phone number. | string | Required |The standard US telephone number is a 10-digit number, such as (555) 555-1234, where the first three digits are the 'area code'.  |
| `email` | The driver's email address. | string | Required | A unique email is required. |
| `id` | The driver's unique record ID. | number | Required | The driver's id is auto-generated. See the return body. |

## Sample request

The PATCH body should look something like this. You can change the values of each property as you’d like.

```js
[
    {
        "driverIdentity": "Nana",
        "cellPhone": "(555)555-9874"
    }
]
```

## Return body

The following example shows the response. Note that the names should be the same as you used in your **Request body** and the response should include the driver's id. The driver's id is automatically generated when the schedule is created.

```js
[
    {
        "driverName": "SallyAnn Issac",
        "driverIdentity": "Nana",
        "cellPhone": "(555)555-9874",
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

* [Tutorial: Change the status (property) of a driver's schedule](../../tutorials/tutorials/4-how-to-change-a-driver-schedule-property.md)
* [Security](../../get-started/quickstart.md#security)
