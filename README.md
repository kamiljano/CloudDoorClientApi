# About

CloudDoor is a minimalistic serverless CnC application based on Azure Functions and Azure IoT Hub.
The application allows to register new IoT devices.

The following reporitory contains only the backend configuration and code.
[The code of an example bot can be found here.](https://github.com/kamiljano/CloudDoorClient)

# TODO

* Store the device creation date (might require parsing the IoT Hub event)
* Add automatic client version updates

# Endpoints

## Register

    PUT /api/bots

    No Body

    Example output:

    {
        "connectionString": "HostName=**********;SharedAccessKey=**************",
        "deviceId": "****************"
    }

# Install Dependencies

All dependencies can be installed with the simple command

```
npm install -g azure-functions-core-tools
npm install
```

# Debug locally

Once all resources are deployed, you can fetch the remote settings with `func azure functionapp fetch-app-settings CloudDoorDev`.
This will pre-configure the `local.settings.json` with all the necessary data to hook your local instance to the remotely hosted IoT Hub and
all other resources that are necessary for a smooth local run.

Once you have your `local.settings.json` in place, run the local server with `func start`