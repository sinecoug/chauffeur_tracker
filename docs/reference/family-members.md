---
layout: page
---

# `family-members` resource

Base endpoint:

```shell
{server_url}/family-members
```

Contains information about family members who transport others by car.

## Resource properties

Sample `family-members` resource

```js
{
    "familyMemberName": "Faith Jaxon",
    "email": "f.smith@gmail.com"
}
```

| Property | Description | Type | Required | Notes |
| -------------- | ------ | ------------ |------------ |------------ |
| `familyMemberName` | The driver's full name. | string | Required |  |
| `email` | The driver's email address. | string | Required |  |

## Operations

The `family-members` resource supports these operations.

### RETRIEVE (GET)

### CREATE (POST)

### UPDATE (PUT/PATCH)

### DELETE
