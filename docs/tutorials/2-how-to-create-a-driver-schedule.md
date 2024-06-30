---
layout: page
---

# Create a driver's schedule

Let's suppose that you've enrolled SallyAnn (*Nana*) in the service, and you want to create a driving schedule for her. She's offered to drive her grandson, Johnny, to and from a dental appointment.

In this tutorial, you will learn how to create a pick-up and drop-off schedule for a driver in the service.

Expect this tutorial to take about 15 minutes to complete.

## Before you start

Before you start this tutorial:

* Complete all the [prerequisites](../overview/prereqs.md) on the development system you'll use for the tutorial.
* Open the Postman app, which you'll use to test your API calls.

## About this task

There's two parts to this task.

1. Identify the driver's ID — unless you already know the driver's unique ID, you must first retrieve it from the list of available drivers. If you already know the driver’s ID, skip this step.
2. Create a driving schedule to associate with the returned/known driver's ID.

## Identify a driver's ID

To view all drivers, make a `GET` call to the [`drivers`](../reference/drivers) resource.

1. To create a new request in Postman, click **New** > **HTTP**. Give the request a title.
1. Specify these request values in the right-frame window:

    | UI Element | Values | Required | Notes |
    | -------------- | ------ | ------------ |------------ |
    | **METHOD** | GET | Required | Locate the drop-down menu next to the URL field. |
    | **URL** | `{server_url}/drivers` | Required |All drivers are returned unless you specify query parameters (see params) to return a specific driver. |
    |**params** | `Key/Value` | Optional |  You can specify driver attributes as key/value query parameters. For example: *driverIdentity/Nana*. Note that key/value titles are case sensitive.  |
    |**Headers** | `Content-Type` | Optional | The format of the data to be posted. Default value is application/json. |
    |**Request body** | None |  |  |

1. Click **Send** to make the request.
1. Review the response body and verify the driver's id, which is automatically generated when the driver object is created. The response should look something like this.

    ```js
        [
            {
                "driverName": "SallyAnn Issac",
                "driverIdentity": "Nana",
                "cellPhone": "(555)555-9874",
                "email": "s.issac@gmail.com"
                "id": "00ad"
            }
        ]   
    ```

## Create a schedule for an identified driver

Assuming that you know Nana's driver's {id}, proceed to create a driving schedule for her.
Make a `POST` call to the [`schedules`](../reference/schedules) resource.

1. To create a new request in Postman, click **New** > **HTTP**. Give the request a title.
1. Specify these values in the right-frame window:

    | UI Element | Values | Required | Notes |
    | -------------- | ------ | ------------ |------------ |
    | **METHOD** | POST | Required | Locate the drop-down menu next to the URL field. |
    | **URL** | `{server_url}/schedules` | Required |  |
    |**Headers** | `Content-Type` | Optional | The format of the data to be posted. Default value is application/json. |

1. In the request body, POST a JSON representation of Nana's [`schedules`](../reference/schedules) object like this.
The *driverId* is the id you identified in your previous `GET` call to the [`drivers`](../reference/drivers) resource, if not already known. You can change the values of each property as you’d like.

    ```js
        [
            {
                "driverId": "00ad",
                "title": "Johnny's Dental visit",
                "passenger": "Johnny",
                "pickupLocation": "123 Main St, Springfield",
                "dropoffLocation": "The Quay, Docks, Springfield",
                "pickupTime": "2024-06-14T11:00:00Z",
                "dropoffTime": "2024-07-14T12:00:00Z",
                "status": "Scheduled"
            }
        ]
    ```

1. Click **Send** to make the request.

1. Review the response body and verify that the driver's schedule includes a newly generated *id*. A 200 OK status code indicates success.

    ```js
        [
            {
                "id": "e3a8",
                "driverID": "00ad",
                "title": "Johnny's Dental visit",
                "passenger": "Johnny",
                "pickupLocation": "123 Main St, Springfield",
                "dropoffLocation": "The Quay, Docks, Springfield",
                "pickupTime": "2024-06-16T11:00:00Z",
                "dropoffTime": "2024-07-16T12:00:00Z",
                "status": "Scheduled"
            }
        ]  
    ```

## Related information

* [Endpoint: Create a schedule](../reference/schedules-create-schedule.md)
