---
layout: page
---

# Set up your development environment

You must do the following steps before you can run
the tutorials for the **Chauffeur Tracker service**.

Expect this preparation to take about 20 minutes to complete.

## Install prerequisite tooling

The following instructions describe how to prepare for running the tutorials on Windows. You only have to do this one time per development system.

For information about how to prepare MacOS for the tutorials, visit the [MacOS installation guide](../macos-installation).

Install the following tools on your development system:

* A [GitHub account](https://github.com)
* A development system (PC, Mac, or Linux) running a current or
long-term support (LTS version of the operating system).
* The following software on your development system:
  * (Optional) [Git](https://docs.github.com/en/get-started/quickstart/set-up-git) (for the command line).
  * [GitHub Desktop](https://desktop.github.com).
  * A fork of the [chauffeur-tracker-service repo](https://github.com/sinecoug/chauffeur-tracker-service).
  * A current/LTS version of [node.js](https://nodejs.org/en/).
  * A current version of [json-server](https://www.npmjs.com/package/json-server).
  * A current copy of the database file. You can get this by syncing your fork.
  * **TIP**: If you're using a fork of the repo, create a working branch in which to do your tutorials. Create a new branch for each tutorial to prevent a mistake in one from affecting your work in another.
  * cURL comes installed by default on Mac operating systems. If you need to, install it from [here](https://curl.se/windows/).
  * The [Postman desktop app](https://www.postman.com/downloads/). Because you run the **Chaffeur Tracker service** on your development system with an `http://localhost` hostname, the web-version of Postman can't perform the exercises.

## Test your development system

To test your development system, follow these steps:

1. Check your json-server version.

    ```shell
    C:\>json-server --version
    ```

   The installed json-server version displays.

    ```shell
    1.0.0-alpha.23
    ```

1. Check your Node.js version.

    ```shell
   
    C:\>node --version
    v20.13.0

    ```

    The installed Node.js version displays.

    ```shell
    v20.13.0
    ```

1. Create and check out a test branch of your fork of the chauffeur-tracker-service repo. Your `GitHub repo workspace` is the directory that contains your fork of the `chauffeur-tracker` repo.

    ```shell
        cd <your GitHub repo workspace>
        # (see the chauffeur-tracker service directory in the list)
        cd chauffeur-tracker-service
        cd api
        cd start-server.bat

    ```

    If your development system is installed correctly, you should see
    the service start and display the URL of the service: `http://localhost:3000`.

    ```shell
         C:\chauffeur_tracker\api>json-server -w chauffeur-tracker-db-source.json
    
        --watch/-w can be omitted, JSON Server 1+ watches for file changes by default
         JSON Server started on PORT :3000
        Press CTRL-C to stop
        Watching  chauffeur-tracker-db-source.json...
    
        ♡( ◡‿◡ )
    
        Index:
        http://localhost:3000/
    
        Static files:
        Serving ./public directory if it exists
    
        Endpoints:
        http://localhost:3000/drivers
        http://localhost:3000/schedules

    ```

1. Make a test call to the service.

    ```bash

        curl -u user:pass http://localhost:3000/drivers
    ```

1. If the service is running correctly, you should see a list of drivers from the service, such as in this example.

    ```js
    [
        {
            "driverName": "Laura Jaxon",
            "driverIdentity": "Mom",
            "cellPhone": "(555)555-1234",
            "email": "l.jaxon@gmail.com",
            "id": "1"
        },
        {
            "driverName": "Aiden Issac",
            "driverIdentity": "Dad",
            "cellPhone": "(555)555-7954",
            "email": "a.issac@gmail.com",
            "id": "2"
        },
        ...
    ```

If you don't see the list of drivers, or receive an error in any step
of the procedure, investigate and correct the error before continuing.
Some common situations that cause errors include:

* You mistyped a command.
* You aren't in the correct directory.
* A required software component didn't install correctly.
* A required software component isn't up to date.

If you see the list of drivers from the service, you're ready to do
the tutorials. For more information, go [here](../index.md).
