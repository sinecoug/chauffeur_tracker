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
    "driverName": "Faith Jaxon",
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
| `cellPhone` | The driver's cell phone number. | string | Required |  |
| `email` | The driver's email address. | string | Required | A unique email is required. |
| `id` | The driver's unique record ID. | number | Required |  |

## Operations

The `drivers` resource supports these operations.

### RETRIEVE (GET)

* [Retrieve all drivers](drivers-get-all-drivers.md)
* [Retrieve a specific driver](drivers-get-driver-by-id.md)
* [Retrieve a driver by property](drivers-get-driver-by-property.md)

### CREATE (POST)

* [Create a driver](drivers-create-driver.md)

### UPDATE (PUT/PATCH)

* [Update a driver](drivers-update-driver-by-id.md)
* [Update a driver by property](drivers-update-driver-by-property.md)

### DELETE

* [Delete a specific driver](drivers-delete-driver-by-id.md)
