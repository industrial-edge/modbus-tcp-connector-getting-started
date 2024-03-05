# Modbus TCP Connector

This example shows how to use the Industrial Edge app Modbus TCP Connector.

- [Modbus TCP Connector](#modbus-tcp-connector)
  - [Description](#description)
    - [Overview](#overview)
    - [General task](#general-task)
  - [Requirements](#requirements)
    - [Prerequisites](#prerequisites)
    - [Used components](#used-components)
  - [Configuration](#configuration)
  - [Usage](#usage)
  - [Documentation](#documentation)
  - [Contribution](#contribution)
  - [Licence and Legal Information](#licence-and-legal-information)

## Description

### Overview

This tutorial shows how to use the Industrial Edge application Modbus TCP Connector to establish a connection between an Industrial Edge Device (IED) and a PLC that supports Modbus TCP, a data communications protocol (client/server) that runs on Ethernet.

These PLC variants are supported:

- Schneider Quantum TCP/IP 140 CPU 113 03　
- Schneider TSX Premium TSXP573634　
- Schneider TSX Momentum 171CCC98020 (TCP/IP)　
- Schneider Micro TSX 3710001　
- Schneider M 340
- Schneider TM218LDAE24DRHN
- Schneider TM238LDD24DT
- Schneider TM258LD42DT　
- Siemens SIWAREX WP231　
- Siemens SIWAREX WP241

The Modbus TCP Connector is an application that runs on the individual IED. Connections can be configured using the Common Configurato for Industrial Edge. The connector transfers the value series of selected data points from a PLC to the Databus. From there the data can be used within other Edge apps, e.g. the Flow Creator.

### General task

Here we configure a connection between a Modbus server and client. The IED acts as the Modbus client and the Modbus server can be any hardware that is able to instantiate standard Modbus communication. The data is published on the IE Databus. By using the application IE Flow Creator, we fetch the metadata of the Modbus TCP Connector, write some data on the configured tags and read out data.

![Overview](docs/graphics/Overview.png)

## Requirements

###  Prerequisites

- Access to an Industrial Edge Management (IEM) with onboarded Industrial Edge Device (IED)
- IEM: Installed system configurator for Databus
- IED: Installed apps IE Databus, IE Flow Creator, Common Configurator, IIH Registry Service, Modbus TCP Connector, IIH Essentials, Databus gateway
- IED is connected to Modbus TCP Server
- Google Chrome (Version ≥ 72)

### Used components

- Industrial Edge Management (IEM) V1.5.1-4 / V2.0.1-1
  - Databus Configurator V2.3.2-2
  - Industrial Edge Virtual Device (OS) ievd-1.16.1-1-a
  - Databus V2.3.2-5
  - Flow Creator V1.16.0-2
  - Common Configurator V1.14.0
  - IIH Registry Service V1.9.0.0
  - Modbus TCP Connector V3.0.1
  - IIH Essentials V1.9.0
  - Databus Gateway V1.9.0
- Modbus TCP Server - ModRSsim2 Modbus TCP Server Simulator

## Configuration

You can find further information about the following steps in the [Configuration](/docs/Installation.md) documentation:

- [Overview](/docs/Installation.md#overview)
- [Install Modbus TCP Connector](/docs/Installation.md#install-modbus-tcp-connector)
- [Configure Databus](/docs/Installation.md#configure-ie-databus)
- [Configure Modbus TCP via Common Configurator](/docs/Installation.md#configure-modbus-tcp-via-common-configurator)

## Usage

As soon as the Modbus TCP Connector is configured, data can be transfered.

You can find further information about how to handle the data via the IE Flow Creator in the [Usage](/docs/Usage.md) documentation:

* [Read metadata](/docs/Usage.md#read-metadata)
* [Write data](/docs/Usage.md#write-data)
* [Read data](/docs/Usage.md#read-data)
* [Use IIH Essentials](/docs/Usage.md#use-IIH-Essentials)
* [Use Common Configurato](/docs/Usage.md#Use-Store-Data-in-Common-Configurator)
## Documentation

You can find further documentation and help in the following links

* [Industrial Edge Hub](https://iehub.eu1.edge.siemens.cloud/#/documentation)
* [Industrial Edge Forum](https://www.siemens.com/industrial-edge-forum)
* [Industrial Edge landing page](https://new.siemens.com/global/en/products/automation/topic-areas/industrial-edge/simatic-edge.html)
* [Industrial Edge GitHub page](https://github.com/industrial-edge)

## Contribution

Thank you for your interest in contributing. Anybody is free to report bugs, unclear documentation, and other problems regarding this repository in the Issues section.
Additionally everybody is free to propose any changes to this repository using Pull Requests.

If you haven't previously signed the [Siemens Contributor License Agreement](https://cla-assistant.io/industrial-edge/) (CLA), the system will automatically prompt you to do so when you submit your Pull Request. This can be conveniently done through the CLA Assistant's online platform. Once the CLA is signed, your Pull Request will automatically be cleared and made ready for merging if all other test stages succeed.

## Licence and Legal Information

Please read the [Legal information](LICENSE.md).
