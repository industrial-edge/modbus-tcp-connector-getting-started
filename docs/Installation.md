# Configuration

- [Configuration](#configuration)
  - [Overview](#overview)
  - [Install Modbus TCP Connector](#install-modbus-tcp-connector)
  - [Configure Databus](#configure-databus)
  - [Configure Modbus TCP via Common Configurator](#configure-modbus-tcp-via-common-configurator)

## Overview

When working with connectors on Industrial Edge, the **Databus** app is required to exchange the data via MQTT. The configuration of the connectors is done via the **Common Configurator** app. Besides this, also the apps **IIH Registry Service** and **Common Import Converter** are necessary.

Make sure the following apps are installed and running on the Industrial Edge Device (IED):

- Databus
- Databus Gateway
- Common Configurator
- IIH Registry Service
- Common Import Converter

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

## Configure Databus

The system app Databus is essential to exchange data between a PLC and the IED. The Modbus TCP Connector sends the transfered data to the Databus on the IED. From there the data can be used for further processing.

You need to create a user and one or more topics in the Databus configuration, which cover the Modbus TCP data:

- ***ie/m/j/simatic/v1/mbtcp1/dp*** for Modbus TCP metadata
- ***ie/d/j/simatic/v1/mbtcp1/dp/#*** for Modbus TCP data

Therefore follow these steps:

- open the Industrial Edge Management (IEM)
- go to 'Data Connections' > Databus
- select the corresponding IED
- create the topic `ie/#` and a dedicated user with username and password ('edge'/'edge'), set permissions to 'Publish and Subscribe'
- deploy the configuration and wait for the job to be finished successfully

![databus](/docs/graphics/databus.png)

## Configure Modbus TCP via Common Configurator

With the Common Configurator, you can configure several connectors and publish the data to the Databus. Therefore, you must enter the Databus credentials within the Common Configurator:

- open the IED web interface
- open the app Common Configurator
- go to the tab 'Settings' and select the menu 'Databus credentials'
- enter the databus service name: 'ie-databus:1883'
- in tab 'Data Publisher settings' enter the databus user name and password ('edge'/'edge')
- in tab 'Data Subscriber settings' enter the databus user name and password ('edge'/'edge')
- save the settings

![IIH_Settings](/docs/graphics/databuscred.PNG)

As soon as the Modbus TCP Connector is installed and started on the same IED as the Common Configurator, the connector is visible within the configurator. In this example we want to configure a Modbus TCP connection to any Modbus TCP server.

In Common Configurator choose Get Data - Connector Configurator:

![configuration1](/docs/graphics/connectors.png)

To configure the Modbus TCP Connector, proceed as following:

- go to the tab 'Get data'
- select the Modbus TCP Connector
- switch to tab 'Tags'
- choose 'Add data source'
- configure the PLC accordingly and save

![configuration2](/docs/graphics/modbusset.png)
 
Good to know:

- "Zero based addressing": PLC register addresses begin at zero and configurator indices begin at one by default (enable, if PLC register addresses and configurator indices begin at zero)
- "Change word order": default counting method is 16 LSB - 1 MSB (enable, if bit counting method is 0 LSB - 15 MSB)
- "Use single write": function codes 15H and 16H are used by default (enable, if function codes 05H, 06H, 15H and 16H are used)

-> Please look up the operating manual of the app for detailed information.

Under column 'Actions' of the newly created PLC, choose 'Add tag':
  
![configuration2](/docs/graphics/tagimport.png)
  
Configure the tags accordingly and save:

![configuration2](/docs/graphics/Configuration3.png)

Select the newly created PLC and click 'Deploy' to save the configuration and start the project:

![Deploy](/docs/graphics/deploy.png)

Back on the overview page 'Databus connectors', the status of the Modbus TCP Connector should be shown as **connected**:

![configuration1](/docs/graphics/connectors.png)

Now data can be transferred via the Modbus TCP connection. Please find more information in the [Usage](/docs/Usage.md) documentation.
