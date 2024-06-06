---
layout: page
---

# Quickstart guide

Are you looking for a way to plan and track your family's transport needs?

Easily manage all your pick-up and drop-off schedules in the Chauffeur Tracker!

## At a glance

This Quickstart provides all the information you need to begin using Chauffeur Tracker to track your driving schedules.

You’ll learn when and how to use the web service and get set up to make your first call to the API.

## Setting up the Chauffeur Tracker service

Driving schedules will surface in the Chauffeur Tracker service when they are created in the database and assigned to drivers (by driver {id}). If you’ve used the Chauffeur Tracker service previously, you’re already enrolled in the service and may have schedules to work with.

If not, you might need to set up your development system and get going from scratch. Don’t worry – you only have to do this one time per development system! Follow these [prerequisite steps](../overview/prereqs.md) to install the tools and test your development system.

## When to use the Chauffeur Tracker service

The Chauffeur Tracker service REST API offers a wide range of integration possibilities, from enhancing a family's driving workflow to creating customer-facing apps.

The service comprises two resources: [`drivers`](drivers) and [`schedules`](schedules). The [`drivers`](drivers) resource (containing the subscribed drivers to the service) works in synergy with the [`schedules`](schedules) resource (containing the schedules) to align drivers with their driving schedules.

Using this cloud-based service, customers (family members) can register themselves to create and manage their own driving schedules.
When they're registered, customers can update and delete schedules to suit their needs. Adding schedules on customers' behalf is easy - if, for exmample, an organization is collaborating with drivers on different teams and projects, they might be delegated on-demand driving requests and assigned schedules from different sources.

## How to use the Chauffeur Tracker service

To build your API call, you must have the following components:

* **A host.**  The {base_url} depends on users' installation of the service in their development environment. For v1 of Chauffeur Tracker Service API, the **base_url** variable is typically set to `http://localhost:3000`.
* **Authorization.**  For v1 of the Chauffeur Tracker service, requests do not use any authorization. All endpoints are available to all users and applications.
* **A request.**  The Chauffeur Tracker service REST API enables CRUD operations via HTTP requests on database resources (`GET`, `POST`, `PUT`, `PATCH`, and `DELETE` methods). Request and response bodies are encoded as JSON.

### Supported endpoints

| HTTP Method | Endpoint |
| :--------------: | :--------------: |
| GET | [Retrieve all drivers](../reference/drivers-get-all-drivers.md) |
| GET | [Retrieve a specific driver by ID](../reference/drivers-get-driver-by-id) |
| GET | [Retrieve a driver by property](../reference/drivers-get-driver-by-property) |
| POST | [Create a driver object](../reference/drivers-create-driver.md) |
| PUT | [Update a driver by ID](../reference/drivers-update-driver-by-id.md) |
| PATCH | [Update a driver by property](../reference/drivers-update-driver-by-property.md) |
| DELETE | [Delete a driver by ID](../reference/drivers-delete-driver-by-id.md) |
| GET | [Retrieve all driving schedules](../reference/schedules-get-all-schedules.md) |
| GET | [Retrieve a specific driver by ID](../reference/schedules-get-schedule-by-id) |
| GET | [Retrieve a driver by property](../reference/schedules-get-schedule-by-property) |
| POST | [Create a driver object](../reference/schedules-create-schedule.md) |
| PUT | [Update a driver by ID](../reference/schedules-update-schedule-by-id.md) |
| PATCH | [Update a driver by property](../reference/schedules-update-schedule-by-property.md) |
| DELETE | [Delete a driver by ID](../reference/schedules-delete-schedule-by-id.md) |

## Make your first API call – *List all tasks*

Assume that you’re already enrolled in the Chauffeur Tracker service and you want to list all driving schedules as a first call to the API.

Let’s test making this simple request to the [`schedules`](schedules) resource.  You’ll use cURL to make the API call.

```bash

curl http://localhost:3000/schedules
```

If the call was successful, the response you receive will be a list of schedules from the Chauffeur Tracker service such as you see in this example:

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

**NOTE:**
cURL comes installed by default on Mac operating systems. If you need to, install it from [here](https://curl.se/windows/).

---

## Next steps

Now that you’ve everything set up correctly, you’re good to go and can take full advantage of the Chauffeur Tracker service API! Go ahead and start posting new driving schedules or enrolling new drivers. You’ll see how easy the API is to use.

If you need more guidance, the Tutorials section of the API documentation walks through any task you’ll want to do. The finer details of the supported resources, endpoints and properties are in the API Reference section. For more information, go [here](../index.md).
