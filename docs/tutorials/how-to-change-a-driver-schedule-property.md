---
layout: page
---

# Change the status (property) of a driver's schedule

Let's suppose that Johnny's dental appointment has been canceled. You want to update SallyAnn's driving schedule to reflect the changed status for this appointment.

In this tutorial, you will learn how to update a single property in a driver's schedule.

Expect this tutorial to take about 15 minutes to complete.

## Before you start

* Complete all the [prerequisites](../overview/prereqs.md) on the development system you'll use for the tutorial.
* Open the Postman app, which you'll use to test your API calls.

## About this task

There's two parts to this task.

1. Identify the schedule's ID — unless you already know the driving schedule's unique ID, you must first retrieve it from the list of available schedules. If you already know the schedule’s ID, skip this step.
2. Update the *status* property in returned/known schedule. You'll used a PATCH request to make the call.

## Identify a driving schedule's ID

To view all drivers, make a `GET` call to the [`drivers`](../reference/drivers) resource.

1. To create a new request in Postman, click **New** > **HTTP**. Give the request a title.
1. Specify these request values in the right-frame window:

    | UI Element | Values | Required | Notes |
    | -------------- | ------ | ------------ |------------ |
    | **METHOD** | GET | Required | Locate the drop-down menu next to the URL field. |
    | **URL** | `{server_url}/schedules` | Required | All schedules are returned unless you specify query parameters (see params) to return a specific schedule. |
    |**params** | `Key/Value` | Optional | You can specify schedule attributes as key/value query parameters. For example: *passenger/Johnny*. Note that key/value titles are case sensitive.  |
    |**Headers** | `Content-Type` | Optional | The format of the data to be posted. Default value is application/json. |
    |**Request body** | None |  |  |

1. Click **Send** to make the request.
1. Review the response body and verify the schedule id, which is automatically generated when the schedule object is created. The response should look something like this.

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
                "status": "Unscheduled"
    }
        ]   
    ```

## Update a property in the identified driver's schedule

Assuming that you know the schedule {id}, proceed to update the driving schedule property (status).
Make a `PATCH` call to the [`schedules`](../reference/schedules) resource.

1. To create a new request in Postman, click **New** > **HTTP**. Give the request a title.
1. Specify these values in the right-frame window:

    | UI Element | Values | Required | Notes |
    | -------------- | ------ | ------------ |------------ |
    | **METHOD** | PATCH | Required | Locate the drop-down menu next to the URL field. |
    | **URL** | `{server_url}/schedules/{id}` | Required |Specify the {id} of the selected schedule returned in your `GET` call.  |
    |**Headers** | `Content-Type` | Optional | The format of the data to be posted. Default value is application/json. |

1. In the request body, POST a JSON representation of Nana's [`schedules`](schedules) object like this. You can change the values of each property as you’d like.

    ```js
        [
            {
                "status": "Canceled"
            }
        ]
    ```

1. Click **Send** to make the request.

1. Review the response body and verify the driver's schedules, which should look something like this. A 200 OK status code indicates success.

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
                "status": "Canceled"
            }
        ]  
    ```

## Related information

* [Endpoint: Update a schedule by property](../reference/schedules-update-schedule-by-property.md)
