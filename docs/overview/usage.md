---
layout: page
---

# API deep dive

The following key concepts reveal how the Chauffeur Tracker service works under the hood.

## The Chauffeur Tracker service

Driving schedules will surface in the Chauffeur Tracker service when they are created in the database and assigned to drivers (by driver {id}). If you’ve used the Chauffeur Tracker service previously, you’re already enrolled in the service and may have schedules to work with.

If not, you might need to set up your development system and get going from scratch. Don’t worry – you only have to do this one time per development system! Follow these [prerequisite steps](../get-started/1-prereqs.md) to install the tools and test your development system.

## When to use the Chauffeur Tracker service

The Chauffeur Tracker service REST API offers a wide range of integration possibilities, from enhancing a family's driving rota to creating customer-facing apps.

The service comprises two resources: [`drivers`](../reference/1-resources/drivers.md) and [`schedules`](../reference/1-resources/schedules.md). The [`drivers`](../reference/1-resources/drivers.md) resource (containing the subscribed drivers to the service) works in synergy with the [`schedules`](../reference/1-resources/schedules.md) resource (containing the schedules) to align drivers with their driving schedules.

Using this cloud-based service, customers (drivers) can register themselves to create and manage their own driving schedules.
When they're registered, customers can update and delete schedules to suit their needs. Adding schedules on customers' behalf is easy - if an organization is collaborating with drivers, for example, they might be delegated on-demand driving requests and assigned schedules from different sources.

## How to use the Chauffeur Tracker service

To build your API call, you must have the following components:

* **A host.**  The {server_url} depends on users' installation of the service in their development environment. For v1 of Chauffeur Tracker Service API, the **server_url** variable is typically set to `http://localhost`. For more information, see [Base URL](../get-started/2-quickstart.md#base-url).
* **Authentication.**  For v1 of the Chauffeur Tracker service, all API requests use HTTP Basic Auth - a security checkpoint that requires transmission of a username and password (Base64 encoded) with every request. For more information, see [API security](../get-started/2-quickstart.md#api-security).
* **A request.**  The Chauffeur Tracker service REST API enables CRUD operations via HTTP requests on database resources (`GET`, `POST`, `PUT`, `PATCH`, and `DELETE` methods). Request and response bodies are encoded as JSON.

### Supported endpoints

| HTTP Method | Endpoint |
| :--------------: | :--------------: |
| GET | [Retrieve all drivers](../reference/2-operations/drivers-get-all-drivers.md) |
| GET | [Retrieve a specific driver by ID](../reference/2-operations/drivers-get-driver-by-id.md) |
| GET | [Retrieve a driver by property](../reference/2-operations/drivers-get-driver-by-property.md) |
| POST | [Create a driver object](../reference/2-operations/drivers-create-driver.md) |
| PUT | [Update a driver by ID](../reference/2-operations/drivers-update-driver-by-id.md) |
| PATCH | [Update a driver by property](../reference/2-operations/drivers-update-driver-by-property.md) |
| DELETE | [Delete a driver by ID](../reference/2-operations/drivers-delete-driver-by-id.md) |
| GET | [Retrieve all driving schedules](../reference/2-operations/schedules-get-all-schedules.md) |
| GET | [Retrieve a specific schedule by ID](../reference/2-operations/schedules-get-schedule-by-id.md) |
| GET | [Retrieve a schedule by property](../reference/2-operations/schedules-get-schedule-by-property.md) |
| POST | [Create a schedule](../reference/2-operations/schedules-create-schedule.md) |
| PUT | [Update a schedule by ID](../reference/2-operations/schedules-update-schedule-by-id.md) |
| PATCH | [Update a schedule by property](../reference/2-operations/schedules-update-schedule-by-property.md) |
| DELETE | [Delete a schedule by ID](../reference/2-operations/schedules-delete-schedule-by-id.md) |

## Related information

* [Quickstart guide](../get-started/2-quickstart.md)
