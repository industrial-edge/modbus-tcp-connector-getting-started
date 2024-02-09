# Configuration

- [Configuration](#configuration)
  - [Overview](#overview)
  - [Install Modbus TCP Connector](#install-modbus-tcp-connector)
  - [Configure IE Databus](#configure-ie-databus)
  - [Configure Modbus TCP via IIH Configurator](#configure-modbus-tcp-via-iih-configurator)

## Overview

When working with connectors on Industrial Edge, the **IE Databus** app is required to exchange the data via MQTT. The configuration of the connectors is done via the **IIH Configurator** app. Therefore also the **Registry Service** app is necessary, to find installed connectors on an Industrial Edge Device.

Make sure the following apps are installed and running on the Industrial Edge Device (IED):
- IE Databus
- Common Configurator
- IIH Registry Service

## Install Modbus TCP Connector

The Modbus TCP Connector app must be available in your IEM catalog. Proceed the following steps to install the app on your IED:

- open the catalog in the IEM
- select the Modbus TCP Connector
- click 'Install'
- in the tab 'Configurations' click 'Next'
- in the tab 'Devices' choose your IED
- click 'Install Now'
- click 'Install' to allow the installation

![app](/docs/graphics/Modbus_App.png)

## Configure IE Databus

The system app Databus is essential to exchange data between a PLC and the IED. The Modbus TCP Connector sends the transfered data to the Databus on the IED. From there the data can be used for further processing.

You need to create a user and one or more topics in the Databus configuration, which cover the Modbus TCP data:

- ***ie/m/j/simatic/v1/mbtcp1/dp*** for Modbus TCP metadata
- ***ie/d/j/simatic/v1/mbtcp1/dp/#*** for Modbus TCP data

Therefore follow these steps:

- open the Industrial Edge Management (IEM)
- go to 'Data Connections' > IE Databus
- select the corresponding IED
- create the topic `ie/#` and a dedicated user with username and password ('edge'/'edge'), set permissions to 'Publish and Subscribe'
- deploy the configuration and wait for the job to be finished successfully

![databus](/docs/graphics/Databus.png)

## Configure Modbus TCP via Common Configurator

With the Common Configurator, you can configure several connectors and publish the data to the IE Databus. Therefore, you must enter the Databus credentials within the Common Configurator:

- open the IED web interface
- open the app IIH Configurator
- go to the tab 'Settings' and select the menu 'Databus credentials'
- enter the databus service name: 'ie-databus:1883'
- in tab 'Data Publisher settings' enter the databus user name and password ('edge'/'edge')
- in tab 'Data Subscriber settings' enter the databus user name and password ('edge'/'edge')
- Save the settings

![IIH_Settings](/docs/graphics/IIH_Settings.png)

As soon as the Modbus TCP Connector is installed and started on the same IED as the Common Configurator, the connector is visible within the configurator. In this example we want to configure a Modbus TCP connection to any Modbus TCP server.

To configure the Modbus TCP Connector, proceed as following:

- go to the tab 'Get data' and select tab 'Databus connectors'
- select the Modbus TCP Connector
- switch to tab 'Tags'
- choose 'Add data source'
- configure the PLC accordingly and save

**Zero based addressing**: is enabled by default; the configured address should start with an index of zero so that both PLC register addresses and configurator indexes will start from zero.

**Change word order**: is disabled by default; this modifies the word order for the representation of 32-bit values. The setting has only an effect on the data types Double and Float in the address operand of 4x.

**Change bit order**: is disabled by default; here the standart bit counting method 16 LSB - 1 MSB is used. Otherwise the bit counting method 0 LSB - 15 MSB is used.

**Use single write**: is enabled by default; the function codes
05H, 06H, 15H, and 16H are used for writing into the PLC. Otherwise only function codes 15H and 16H are used.

Please look up the operating manual of the app for detailed information.
![MTCP - config](https://github.com/industrial-edge/modbus-tcp-connector-getting-started/assets/158267726/5d3364dc-b317-4db8-b276-64bb7b3669b2)

- under column 'Actions' of the newly created PLC, choose 'Add tag'
- configure the tags accordingly and save

![configuration2](/docs/graphics/Configuration2.png)

- select the newly created PLC and click 'Deploy' to save the configuration and start the project
![deploy](https://github.com/industrial-edge/modbus-tcp-connector-getting-started/assets/158267726/819c6c7a-69d7-4408-828d-03bca8b5e6b6)

- back on the overview page 'Databus connectors', the status of the Modbus TCP Connector should be shown as **connected**
![Avaible connectors](https://github.com/industrial-edge/modbus-tcp-connector-getting-started/assets/158267726/018608f2-51ab-4ee0-a8f4-029bb000706f)

Now data can be transferred via the Modbus TCP connection. Please find more information in the [Usage](/docs/Usage.md) documentation.
