---
layout: page
---

# Create a driver object

Creates a [`drivers`](drivers) object in the database.
The request body contains the new driver's details.
You must specify the required properties for the driver.

## URL

```shell

{POST}{server_url}/drivers/
```

## Request headers

| Header name | Description | Required | Values |
| -------------- | ------ | ------------ |------------ |
| Basic Auth | A security checkpoint that requires transmission of a username and password with every request. | Required | Basic authentication is a simple authentication scheme that's built into the HTTP protocol. See the Quickstart > Security section.|
| Content-Type | The format of the data to be posted. | Optional | application/json. Default value.  |
| Accept | The format of the data to be returned. | Optional | application/json. Default value. |

## Request body

In the request body, specify a JSON representation of the [`drivers`](drivers) object. The following table lists the properties that are required when you create a driver object.

| Property | Description | Type | Required | Notes |
| -------------- | ------ | ------------ |------------ |------------ |
| `driverName` | The driver's full name. | string | Required |  |
| `driverIdentity` | The driver's primary role in relationship to the family. | string | Optional |Examples: Mom, Dad, Neighbor.  |
| `cellPhone` | The driver's cell phone number. | string | Required |The standard US telephone number is a 10-digit number, such as (555) 555-1234, where the first three digits are the 'area code'.  |
| `email` | The driver's email address. | string | Required | A unique email is required. |
| `id` | The driver's unique record ID. | number | Required | The schedule id is auto-generated. See the return body. |

## Sample request

The POST body should look something like this. You can change the values of each property as you’d like.

```js
[
    {
        "driverName": "SallyAnn Issac",
        "driverIdentity": "Nana",
        "cellPhone": "(555)555-9874",
        "email": "s.issac@gmail.com"
    }
``
]
```

## Return body

The following example shows the response. Note that the names should be the same as you used in your **Request body** and the response should include the new driver's id. The driver's id is automatically generated when the driver object is created.

```js
[
    {
        "id": "fd05",
        "driverName": "SallyAnn Issac",
        "driverIdentity": "Nana",
        "cellPhone": "(555)555-9874",
        "email": "s.issac@gmail.com"
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

* [Tutorial: Enroll a new driver](../tutorials/how-to-enroll-a-driver.md)
* [Quickstart guide > Security](../get-started/quickstart.md)
