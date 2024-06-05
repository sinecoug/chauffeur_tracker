---
layout: page
---
# Retrieve drivers by property

Returns an array of [`drivers`](drivers) objects matching a specified property.

For example, to return a driver by cell phone number, query the property `cellPhone` to filter responses.

Assumption: to return the correct driver, you must know the property to query.

## URL

```shell

{GET}{server_url}/drivers/?{property}={value}
```

## Query parameters

Optionally, you can specify driver properties as`Key/Value` query parameters. For example: `driverIdentity/Neighbor`. Note that property titles are case sensitive.

| Property | Description | Type | Required | Notes |
| -------------- | ------ | ------------ |------------ |------------ |
| `driverName` | The driver's full name. | string | Required |  |
| `driverIdentity` | The driver's primary role in relationship to the family. | string | Optional |Examples: Mom, Dad, Neighbor.  |
| `cellPhone` | The driver's cell phone number. | string | Required |  |
| `email` | The driver's email address. | string | Required | A unique email is required. |

## Request headers

None

## Request body

None

## Sample request

The API call should look something like this. You can change the values of each property as you’d like.

```bash
{GET}{base_url}/drivers?driverIdentity=Neighbor
```

## Return body

The sample response returns a driver matching the specified `driverIdentity`.

```js
[
    {
        "driverName": "Melanie Griffiths",
        "driverIdentity": "Neighbor",
        "cellPhone": "(555)794-4321",
        "email": "m.griffiths@gmail.com",
        "id": "3"
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

* [Tutorial: Retrieve a driver's cell phone number](../tutorials/how-to-get-a-driver-by-property.md)
