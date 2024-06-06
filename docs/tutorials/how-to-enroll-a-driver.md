---
layout: page
---

# Tutorial: Enroll a new driver

Let's suppose that SallyAnn (*Nana*) wants to add herself to the family's driving rota to ease their load.

In this tutorial, you will learn how to enroll a new driver in the service.

Expect this tutorial to take about 15 minutes to complete.

## Before you start

Before you start this tutorial:

* Complete all the [prerequisites](../overview/prereqs.md) on the development system you'll use for the tutorial.
* Open the Postman app, which you'll use to test your API calls.

## Enroll a new driver

To enroll a new driver, make a `POST` call to the [`drivers`](../reference/drivers) resource.

1. To create a new request in Postman, click **New** > **HTTP**. Give the request a title.
1. Specify these request values in the right-frame window:

    | UI Element | Values | Required | Notes |
    | -------------- | ------ | ------------ |------------ |
    | **METHOD** | POST | Required | Locate the drop-down menu next to the URL field. |
    | **URL** | `{server_url}/drivers` | Required | |
    |**Headers** | `Content-Type` | Optional | The format of the data to be posted. Default value is application/json. |

1. In the request body, POST a JSON representation of SallyAnn's [`drivers`](../reference/drivers) object like this. You can change the values of each property as you’d like.

    ```js
        [
            {
                "driverName": "SallyAnn Issac",
                "driverIdentity": "Nana",
                "cellPhone": "(555)555-9874",
                "email": "s.issac# Tutor@gmail.com"
            }
        ]
    ```

1. Click **Send** to make the request.
1. Review the response body. The driver's id is automatically generated when the driver object is created.

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

## Related information

* [Endpoint: Create a driver object](../reference/drivers-create-driver.md)
