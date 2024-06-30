---
layout: page
---

# `drivers` resource

Base endpoint:

```shell
{server_url}/drivers
```

Contains information about drivers who transport family members by car.

## Resource properties

Sample `drivers` resource

```js
{
    "driverName": "Laura Jaxon",
    "driverIdentity": "Mom"
    "cellPhone": "(555)555-1234"
    "email": "f.smith@gmail.com"
    "id": 1
}
```

| Property | Description | Type | Required | Notes |
| -------------- | ------ | ------------ |------------ |------------ |
| `driverName` | The driver's full name. | string | Required |  |
| `driverIdentity` | The driver's primary role in relationship to the family. | string | Optional |Examples: Mom, Dad, Neighbor.  |
| `cellPhone` | The driver's cell phone number. | string | Required |The standard US telephone number is a 10-digit number, such as (555) 555-1234, where the first three digits are the 'area code'.  |
| `email` | The driver's email address. | string | Required | A unique email is required. |
| `id` | The driver's unique record ID. | number | Required |  |

## Operations

The `drivers` resource supports these operations.

### RETRIEVE (GET)

* [Retrieve all drivers](../2-operations/drivers-get-all-drivers.md)
* [Retrieve a specific driver](../2-operati/drivers-get-driver-by-id.md)
* [Retrieve a driver by property](../2-operati/drivers-get-driver-by-property.md)

### CREATE (POST)

* [Create a driver object](../2-operations/drivers-create-driver.md)

### UPDATE (PUT/PATCH)

* [Update a specific driver](../2-operations/drivers-update-driver-by-id.md)
* [Update a driver by property](../2-operations/drivers-update-driver-by-property.md)

### DELETE

* [Delete a specific driver](../2-operations/drivers-delete-driver-by-id.md)
