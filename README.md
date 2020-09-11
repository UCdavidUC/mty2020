# IoT on Azure (MTY 2020)

GitHub Docs: The concise guide to IoT Edge on Azure: https://github.com/UCdavidUC/mty2020

# Contents

* AI - How tu run AI models on the Edge and stream it to the cloud.
* CV - Deploy your Cognitive Service Computer Vision and get insights from what you see.
* Function - Create an IoT Edge integrated environment with Azure Functions running on the Edge.
* ML - Run your machine learning models on the edge and get predictions and classifications models streaming to the cloud.
* Stream Analytics - Gather only valuable inforamtion from your devices in real time, get your stream onto real time monitoring services in Azure with Power BI.

# Getting started

In this guide it is described how to prepare your Azure and IoT Edge environments for our different labs and scenarios. 

For this scenarios I will be using a Raspberry Pi 3 B. Support for Raspberry Pi 4 will be comming soon.

You can also use a Linux or Windows environment. Plan ahead on aqcuiring a device with one CPU architectures: ARM32v7, AMD64 or ARM64 (in Preview, some features may not be available).

Enjoy!

## Prepare your Microsoft Azure environment

### Create a Resource Group to group your resources

* Create your resource group based on the region you want to provision your resorces.
* Use a meaningful name so you can identify what the resoruce's group contents are about.

### Create an IoT Hub

* IoT Hub is you device gateway to the cloud.
* You can register your devices here and receive information from them such as: monitoring informacion, data gathered from the environment or the result of on Edge data processing.
* With Azure IoT Device Provisioning Service (IoT DPS) in Azure you can update all of your devices or specific single or grouped devices on zero touch on-deman way.
* Configure your IoT Hub on the available regions depending on the features you want to deploy. *
* IoT Hub may require some time to provision. Please be patient :D and have a coffee in the meantime.
* Once it is provision, you can go to the next step.

### Create an IoT Edge device in your IoT Hub

* Now it´s time to generate your Azure to the Edge endpoint by creating an IoT Edge device.
* In your IoT Hub tools on your left you can find a section called "Automatic device management", under this section click the "IoT Edge" button.
* In the top bar select "Add and IoT Edge device".
* Fill the information requested in the form and then click the "Save" button at the bottom.
* There you go! You've created an IoT Edge device onto your IoT Hub.

### Get your IoT Edge device information

* Once your IoT Edge device is created you can select it from the Azure IoT Edge blade.
* You will see a set of fields containing different keys and connection strings, this information will be used to connect our device to our IoT Hub and create a bidirectional connection between Azure and your device.
* Copy both your Primary Key and connection string into a safe place, we will need it when we configure our IoT Edge device.
* As you can see in the bottom of the IoT Edge management blade there are two different modules: 
    * $edgeAgent
    * $edgeHub
* These must be up and running when we finish the device setup in the following steps.

## Prepare your IoT Edge environment

* First of all, you can provision almost any device that can support to run containers as mobi-engine and docker and devices with different operating systems: Linux or Windows.
* Not all devices are suitable, depending on the CPU architecture they may be supported or not.
* Please checkout the following link to know if your device is supported or if it is suitable for IoT Edge: 
    * Supported OS: https://docs.microsoft.com/en-us/azure/iot-edge/support
    * IoT Edge Certified Devices: https://catalog.azureiotsolutions.com/alldevices?filters={%2218%22:[%221%22]}

## Prepare your device for IoT Edge

* Debian 10 systems, including Raspian Buster, use a version of OpenSSL that IoT Edge doesn't support. Use the following command to install an earlier version before installing IoT Edge:

```
sudo apt-get install libssl1.0.2
```

Access to the source demo and guidelines: https://docs.microsoft.com/en-us/azure/iot-edge/tutorial-deploy-custom-vision

### References

Note: IoT DPS service is only available at certain locations, please review the following link to check service availability in Azure:
https://azure.microsoft.com/en-us/global-infrastructure/services/?products=iot-hub
