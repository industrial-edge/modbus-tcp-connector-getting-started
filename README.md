# Modbus TCP Connector

This example shows how to use the Industrial Edge app Modbus TCP Connector.

- [Modbus TCP Connector](#modbus-tcp-connector)
  - [Description](#description)
    - [Overview](#overview)
    - [General task](#general-task)
  - [Requirements](#requirements)
    - [Prerequisites](#prerequisites)
    - [Used components](#used-components)
    - [PLC project](#plc-project)
  - [Installation](#installation)
  - [Usage](#usage)
  - [Documentation](#documentation)
  - [Contribution](#contribution)
  - [Licence and Legal Information](#licence-and-legal-information)

## Description

### Overview

This tutorial shows how to use the Industrial Edge application Modbus TCP Connector to establish a connection between an Industrial Edge Device (IED) and a 3rd party PLC that supports Modbus TCP, a data communications protocol (client/server) that runs on Ethernet.

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

The Modbus TCP Connector is an application that runs on the individual IED. Connections can be configured using the Common Configurator for Industrial Edge. The connector transfers the value series of selected data points from a PLC to the Databus. From there the data can be used within other Edge apps, e.g. the Flow Creator.

### General task

**TODO: Go ahead here...**

In this example a connection between a Modbus server and clients is configured. The edge device acts as the client and the Modbus server can be any hardware that is able to instantiate standard Modbus communication. Please also check the documentation for the requirements.


Getting started Edge App Modbus TCP. 
In this example the Edge Device acts as Modbus client. 
For the ModBus Server any modbus TCP capable Device can be used (see Modbus TCP documentation system tested). 

![Overview](docs/graphics/Overview.png)

## Requirements

###  Prerequisites

- Access to an Industrial Edge Management System (IEM)
- Onboarded Industial Edge Device on IEM
- Installed System Configurators for Databus 
- Installed System Apps Databus
- Installed Apps Modbus TCP Configurator, Modbus TCP Connector, IE-Flow Creator
- Edge device is connected to Modbus TCP Server
- Google Chrome (Version ≥ 72) or Firefox (Version ≥ 62)

### Used components

- Industrial Edge Management (IEM) V1.2.0-34
- IE Databus Configurator V1.2.29
- IE Databus V1.2.16
- Modbus TCP Connector V1.1.2
- Modbus TCP Configurator V1.1.2
- Modbus TCP Server (e.g. LOGO!230)
- Industrial Edge Device V 1.2.0-56
- Web browser (Mozilla or Chrome)

### PLC project

## Installation

You can find the further information about the following steps in the [docs](docs/Installation.md)
- Download Modbus TCP Configurator & Connector on your Edge Device
- Activate ModBus TCP Server 
- Configure PLC Connection (Databus, Modbus TCP Configurator)
- Cofnigure Data Service and add ModBus Adapter 



## Documentation

You can find further documentation and help in the following links
  - [Industrial Edge Hub](https://iehub.eu1.edge.siemens.cloud/#/documentation)
  - [Industrial Edge Forum](https://www.siemens.com/industrial-edge-forum)
  - [Industrial Edge landing page](https://new.siemens.com/global/en/products/automation/topic-areas/industrial-edge/simatic-edge.html)
  
## Contribution

Thank you for your interest in contributing. Anybody is free to report bugs, unclear documentation, and other problems regarding this repository in the Issues section.
Additionally everybody is free to propose any changes to this repository using Pull Requests.

If you are interested in contributing via Pull Request, please check the [Contribution License Agreement](Siemens_CLA_1.1.pdf) and forward a signed copy to [industrialedge.industry@siemens.com](mailto:industrialedge.industry@siemens.com?subject=CLA%20Agreement%20Industrial-Edge).

## Licence and Legal Information

Please read the [Legal information](LICENSE.md).
