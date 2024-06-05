---
layout: page
---

# Tutorial: Retrieve a driver's cell phone number

Let's suppose that Mom, *Laura*, is late for a pick-up and her passenger, Molly, needs her cell phone number to check in with her.

In this tutorial, you will learn how to retrieve a driver in the service by a property query.

Expect this tutorial to take about 15 minutes to complete.

## Before you start

Before you start this tutorial:

1. Make sure you've completed these [prerequisites](../get-started/prereqs.md) on the development system you'll use for the tutorial.
2. Confirm that your local service is running. If it's not, start it with this command:

    ```shell
    cd <your-github-workspace>/chauffeur-tracker/api
    # Run the service and monitor its database file for updates
    json-server -w chauffeur-tracker-db-source.json
    ```

3. Open the Postman app. For this tutorial, you'll use Postman to test your API calls.

## About this task

For this tutorial, you'll use Postman to test your API calls.

## Retrieve a driver

To view a driver in the service, make a `GET` call to the [`drivers`](../reference/drivers) resource. Add a query parameter, `driverIdentity/Mom` to filter responses.

1. On your desktop, open the Postman app.
1. To create a new request, click **New** > **HTTP**. Give the request a title.
1. Specify these request values in the right-frame window:

    | UI Element | Values | Required | Notes |
    | -------------- | ------ | ------------ |------------ |
    | **METHOD** | GET | Required | Locate the drop-down menu next to the URL field. |
    | **URL** | `{base_url}/drivers` | Required |All drivers are returned unless you specify query parameters (see params) to return a specific driver. |
    |**params** | `Key/Value` | Optional | For the key/value pair, enter *driverIdentity/Mom*. Note that key/value titles are case sensitive.  |
    |**Headers** | `Content-Type` | Optional | The format of the data to be posted. Default value is application/json. |
    |**Request body** | None |  |  |

1. Click **Send** to make the request.
1. Review the response body, which should look something like this. Verify the requested driver's cell phone number.

    ```js
        [
            {
                "driverName": "Laura Jaxon",
                "driverIdentity": "Mom",
                "cellPhone": "(555)555-1234",
                "email": "f.smith@gmail.com",
                "id": "1"
            }
        ]
    ```

## Related information

* [Endpoint: Retrieve drivers by property](../reference/drivers-get-driver-by-property.md)
