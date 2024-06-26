---
layout: page
---

# Quickstart guide

Are you looking for a way to plan and track your family's transport needs?

## At a glance

This Quickstart provides all the information you need to begin using Chauffeur Tracker to track your family's driving schedules.

You’ll learn about hosting a secure web service and how to make your first call to the API.

## API Security

At its heart, API security requires that the caller provides:

- an authenticated identity (the *authentication*), and
- evidence that the caller has permission to access the resources (the *authorization*).

The Chauffeur Tracker service is an imaginary, *simulated* service. While it doesn't follow all the access and restriction rules, the service does implement HTTP Basic Auth, which is a classic lock-and-key security model that's simple and widely used. Basic Auth requires a username and password combination that's Base64 encoded and sent in the HTTP Authorization header of a request.

In HTTP Basic Auth, the server-side application expects an Authorization header that contains a:

    - username 
    - password

If it doesn't receive it, it returns an HTTP 401 "Unauthorized" error. For more information, see [Error handling information](../reference/4-error-handling/error-handling.md).

## Base URL

The Chauffeur Tracker API is served over HTTPS. All URLs referenced in the documentation have the following base: https://{server_url}.

The {server_url} variable depends on users' installation of the service in their development environment. For v1 of Chauffeur Tracker service, the {server_url} variable is typically set to <http://localhost>.

Here's how to set your base URL variable in Postman.

1. In the request pane in the Postman interface, click on the **Params** tab.
1. Click on **Add Param** button.
1. Choose **URL** from the dropdown menu.
1. Enter a name for your variable,for example, ```baseURL```.
1. Enter the base URL for your API, for example, ```http://localhost:3000```.
1. Click **Save**.  

Note that whenever you create a new request, you can use the ```baseURL``` variable as part of your URL.

## Make your first API call – *List all driving schedules*

For your first call to the API, assume that you’re already enrolled in the Chauffeur Tracker service and you want to list all driving schedules.

- You've aleady set up your local [system requirements](../get-started/1-prereqs.md) to use the API.
- You’ll use cURL to make the API call, and for Basic Auth, include the -u parameter to bypass the username and password and return the response without errors.

Let’s test making this simple request to the [`schedules`](../reference/1-resources/schedules.md) resource.  

Open another command-line window and submit the following request to retrieve a list of drivers' schedules.

**Sample request:**

    ``` shell
    curl -u user:pass http://localhost:3000/schedules
    ```

---
**Remember:**
To make a request to ```http://localhost:3000/schedules```, you can simply use ```{baseURL}/drivers``` as your request URL.

---

**Sample response:**

    ```js

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
            "driverId": "2",
            "title": "Baseball practice",
            "passenger": "Richie",
            "pickupLocation": "123 Main St, Springfield",
            "dropoffLocation": "456 Elm St, Springfield",
            "pickupTime": "2024-06-15T08:00:00Z",
            "dropoffTime": "2024-06-15T08:30:00Z",
            "status": "Scheduled",
            "id": "1"
        },
        {
            "driverId": "3",
            "title": "Swimfest",
            "passenger": "Molly",
            "pickupLocation": "123 Main St, Springfield",
            "dropoffLocation": "110 Nassau St, Springfield",
            "pickupTime": "2024-07-22T08:00:00Z",
            "dropoffTime": "2024-07-22T08:30:00Z",
            "status": "Scheduled",
            "id": "3"
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
        },
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

    ```

## Next steps

Now that you’ve everything set up correctly, you’re good to go and can take full advantage of the Chauffeur Tracker service API! Go ahead and start posting new driving schedules or enrolling new drivers. You’ll see how easy the API is to use.

If you need more guidance, the Tutorials section of the API documentation walks through any task you’ll want to do. The finer details of the supported resources, endpoints and properties are in the API Reference section. For more information, go [here](../index.md).
