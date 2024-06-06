---
layout: page
---

# System requirements

These are the steps you must do before you can run the tutorials for the **Chauffeur Tracker service**.

Expect this preparation to take about 20 minutes to complete.

## Preparing for the tutorials

The following instructions describe how to prepare for running the tutorials on Windows.
For information about how to prepare MacOS for the tutorials, visit the [MacOS installation guide](macos-installation).

### Setting up your development environment

To complete the tutorials in this section, install the following tooling:

* A [GitHub account](https://github.com)
* A development system (PC, Mac, or Linux) running a current or
long-term support (LTS version of the operating system).
* The following software on your development system:
  * [Git](https://docs.github.com/en/get-started/quickstart/set-up-git) (for the command line)
  * [GitHub Desktop](https://desktop.github.com) (optional)
    * A fork of the [chauffeur-tracker-service repo](https://github.com/sinecoug/chauffeur-tracker-service)
    * A current/LTS version of [node.js](https://nodejs.org/en/)
    * A current version of [json-server](https://www.npmjs.com/package/json-server)
    * A current copy of the database file: /api/chauffeur-tracker-db-source.json. You can get this by syncing your fork.
    * **TIP**: If you're using a fork of the repo, create a working branch in which to do your tutorials. Create a new branch for each tutorial to prevent a mistake in one from affecting your work in another.
    * The [Postman desktop app](https://www.postman.com/downloads/). Because you run the **Chauffeur Tracker service** on your development system with an `http://localhost` hostname, the web-version of Postman can't perform the exercises.

## Test your development system

To test your development system, follow these steps:

1. Create and checkout a test branch of your fork of the To-Do-service repo. Your `GitHub repo workspace` is the directory that contains your fork of the `chauffeur-tracker` repo.

    ```shell
    cd <your GitHub repo workspace>
    ls
    # (see the chauffeur-tracker-service directory in the list)
    cd chauffeur-tracker
    git checkout -b tutorial-test
    cd api
    json-server -w chauffeur-tracker-db-source.json
    ```

    If your development system is installed correctly, you should see
    the service start and display the URL of the service: `http://localhost:3000`.

2. Make a test call to the service.

    ```bash

        curl -u user:pass http://localhost:3000/drivers
    ```

3. If the service is running correctly, you should see a list of users from the service, such as in this example.

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

1. You mistyped a command.
2. You aren't in the correct directory.
3. A required software component didn't install correctly.
4. A required software component isn't up to date.

If you see the list of users from the service, you're ready to do
the tutorials.

## Related information

* [Quickstart guide](../get-started/quickstart.md)
