---
layout: page
---

# Retrieve a driver's schedule

Let's suppose that Mom, *Laura*, wants a list of her *scheduled* driving commitments.

In this tutorial, you will learn how to retrieve schedules with a requested status for a specific driver in the service.

Expect this tutorial to take about 15 minutes to complete.

## Before you start

* Complete all the [prerequisites](../get-started/1-prereqs.md) on the development system you'll use for the tutorial.
* Open the Postman app, which you'll use to test your API calls.

## About this task

There's two parts to this task.

1. Identify the driver's ID — unless you already know the driver's unique ID, you must first retrieve it from the list of available drivers. If you already know the driver’s ID, skip this step.
2. Retrieve the *scheduled* driving commitments associated with the returned/known driver's ID.

## Identify a driver's ID

To view all drivers, make a `GET` call to the [`drivers`](../reference/1-resources/drivers.md) resource.

1. To create a new request in Postman, click **New** > **HTTP**. Give the request a title.
1. Specify these request values in the right-frame window:

    | UI Element | Values | Required | Notes |
    | -------------- | ------ | ------------ |------------ |
    | **METHOD** | GET | Required | Locate the drop-down menu next to the URL field. |
    | **URL** | `{server_url}/drivers` | Required |All drivers are returned unless you specify query parameters (see params) to return a specific driver. |
    |**params** | `Key/Value` | Optional |  You can specify driver attributes as key/value query parameters. For example: *driverIdentity/Mom*. Note that key/value titles are case sensitive.  |
    |**Headers** | `Content-Type` | Optional | The format of the data to be posted. Default value is application/json. |
    |**Request body** | None |  |  |

1. Click **Send** to make the request.
1. Review the response body and verify the driver's id, which should look something like this.

    ```js
        [
            {
                "driverName": "Laura Jaxon",
                "driverIdentity": "Mom",
                "cellPhone": "(555)555-1234",
                "email": "l.jaxon@gmail.com",
                "id": "1"
            }
        ]
    ```

## Retrieve the driver's **scheduled** driving commitments

Assuming that you know the driver's {id}, proceed to retrieve their scheduled driving commitments.
Make a `GET` call to the [`schedules`](../reference/schedules) resource.

1. To create a new request in Postman, click **New** > **HTTP**. Give the request a title.
1. Specify these values in the right-frame window:

    | UI Element | Values | Required | Notes |
    | -------------- | ------ | ------------ |------------ |
    | **METHOD** | GET | Required | Locate the drop-down menu next to the URL field. |
    | **URL** | `{server_url}/schedules` | Required | All schedules are returned unless you specify query parameters (see params) to return a specific schedule. |
    |**Params** | `Key/Value` | Required |  Specify these key/value query parameters: <br /> * *driverId/{id}* of the selected driver returned in your `GET` call, and  <br /> * *status/Scheduled* <br /> Note that key/value titles are case sensitive. |
    |**Headers** | `Content-Type` | Optional | The format of the data to be posted. Default value is application/json. |
    |**Request body** | None |   |  |

1. Click **Send** to make the request.
1. Review the response body and verify the driver's schedules, which should look something like this. A 200 OK status code indicates success.

    ```js
        [
            {
                "driverId": "1",
                "title": "School run",
                "passenger": "Molly",
                "pickupLocation": "789 Oak St, Anytown",
                "dropoffLocation": "321 Maple St, Anytown",
                "pickupTime": "2024-06-16T09:00:00Z",
                "dropoffTime": "2024-06-16T09:30:00Z",
                "status": "Scheduled",
                "id": "2"
            },
            {
                "driverId": "1",
                "title": "Vet visit",
                "passenger": "Minnie",
                "pickupLocation": "123 Main St, Springfield",
                "dropoffLocation": "12 Animal Drive, Springfield",
                "pickupTime": "2024-08-08T08:00:00Z",
                "dropoffTime": "2024-08-08T08:30:00Z",
                "status": "Scheduled",
                "id": "4"
            }
        ]
    ```

## Related information

* [Endpoint: Retrieve schedules for a specific driver](../reference/2-operations/schedules-get-schedule-by-id.md)
