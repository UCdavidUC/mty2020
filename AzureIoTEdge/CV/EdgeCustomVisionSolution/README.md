# Computer Vision on the Edge with Azure

## Prerequisites

* Updated Python installation (Python3)
* Python libraries installation requirements:
```
pip3 install --upgrade iotedgehubdev
pip3 install azure-iot-device
pip3 install azure-iothub-device-client
```
Depending on the pip implementation, you can use either pip or pip3.

For Linux and MacOS you will require to run the following script:

Linux:
```
sudo apt-get install libboost-python-dev
```

MacOS:
```
brew install libboost-python-dev
```

It is highly recommended that you install the Azure CLI, follow the instructions based on your computer OS [Install Azure CLI](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest).

## Create an IoT Edge solution

* Update the camera module Dockerfile to include ```pip3``` instead of ```pip``` if you are using a Python version >= 3.0 environment.

* Before publishing your container images to your container registry ensure that you are logged into the ACR docker container, use the following command:

```
az acr login --name <acrName>
```

This command requires that you have installe the Azure CLI.

## Prepare your device

In this lab I use a Raspberry Pi model B+ with a Raspbian Stretch (9) image.

You will need to enable the camera in your device, if you have a Raspberry Pi camera follow the instructions on [Getting started with Raspberry Pi 3 Camera](https://projects.raspberrypi.org/en/projects/getting-started-with-picamera/3).

## Azure environment configuration

* Build a Computer Vision model image with Custom Vision.
* Develop an IoT Edge module that queries the Custom Vision web server on your device.
* Send the results of the image analysis to IoT Hub.

## Test your camera endpoint

### How to build

```
docker build -t <your image name> .
```

### How to run locally:

```
docker run -p 127.0.0.1:80:80 -d <your image name>
```

Then use your favorite tool to connect to the end points.

POST http://127.0.0.1/image with multipart/form-data using the imageData key.
	
    curl -X POST http://127.0.0.1/image -F imageData=@some_file_name.jpg

POST http://127.0.0.1/image with application/octet-stream
	
    curl -X POST http://127.0.0.1/image -H "Content-Type: application/octet-stream" --data-binary @some_file_name.jpg

POST http://127.0.0.1/url with a json body of { "Url": "<test url here>" }

    curl -X POST http://127.0.0.1/url -d "{ \"Url\": \"<test url here>\" }"


## References: 

* GitHub Microsoft refence lab: [Custom Vision IoT Edge with Raspberry Pi](https://github.com/Azure-Samples/Custom-vision-service-iot-edge-raspberry-pi)
* Azure IoT EdgeHub Dev Tool installation guide [installation guide](https://github.com/Azure/iotedgehubdev#installing)