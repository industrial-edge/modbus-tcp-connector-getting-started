# Usage

- [Usage](#usage)
  - [Read metadata](#read-metadata)
  - [Write data](#write-data)
  - [Read data](#read-data)
  - [Use Data Service](#use-data-service)
  
Via the IE Flow Creator, we can write and read the Modbus TCP data.

The used flow can be downloaded [here](/src/flow.json) and imported into the IE Flow Creator, that is running on the same IED as the Modbus TCP Connector.

## Read metadata

To print out the Modbus TCP Connector metadata, follow these steps:

- create a mqtt in node
- set the server to 'ie-databus' with port 1883 and corresponding user name/password ('edge'/'edge')
- set the topic to `ie/m/j/simatic/v1/mbtcp1/dp`
- create a debug node and connect to the mqtt in node
- deploy the flow and watch the debug window

![metadata_flow](/docs/graphics/Metadata_Flow.png)

![metadata](/docs/graphics/Metadata.png)


## Write data

To write some data on the Modbus TCP tags, you must fetch the tag ID from metadata payload based on the tag name. Please follow these steps:

- for the ***var_int*** tag, create an inject node to write the value -32768 with this JSON payload: `{"vals":[{"id":"102","val":"-32768"}]}`
- for the ***var_int*** tag, create another inject node to write the value 32767 with this JSON payload: `{"vals":[{"id":"102","val":"32767"}]}`
- for the ***var_dint*** tag, create an inject node to write the value -2147483648 with this JSON payload: `{"vals":[{"id":"103","val":"-2147483648"}]}`
- for the ***var_dint*** tag, create another inject node to write the value 2147483647 with this JSON payload: `{"vals":[{"id":"103","val":"2147483647"}]}`
- create a mqtt out node
- set the server to 'ie-databus' with port 1883 and corresponding user name/password ('edge'/'edge')
- set the topic to `ie/d/j/simatic/v1/mbtcp1/dp/w/Modbus Server`
- connect the inject nodes to the mqtt out node
- deploy the flow
- click the single inject buttons, to write the values

![write_data_flow](/docs/graphics/Write_Data_Flow.png)

## Read data

To print out the transfered Modbus TCP Connector data, you must fetch the tag ID from metadata payload based on the tag name. Please follow these steps:

- create a mqtt in node
- set the server to 'ie-databus' with port 1883 and corresponding user name/password ('edge'/'edge')
- set the topic to `ie/d/j/simatic/v1/mbtcp1/dp/r/#`
- create a debug node and connecto to the mqtt in node
- deploy the flow
- as soon as the value for a configured tag changes, you can see it in the debug window

![read_data_flow](/docs/graphics/Read_Data_Flow.png)

If some data is written in flow creator it looks like the following:

![read_1](/docs/graphics/Read_1.png)


## Use IIH Essentials
The app IIH Essentials collects the data out of different connectors and stores it for a defined time period. This is a prerequisite for other apps like Performance Insight.

To activate the data transfer from the Modbus TCP Connector, proceed as following:

- open the IED web interface
- open the app Data Service
- go to tab 'Connectors' and select 'Modbus TCP Connector'
- select the edit button and enter the user name and the password for the Databus user ('edge'/'edge')
- activate the adapter and save

![DataServiceAdapter](/docs/graphics/DataService_Adapter.png)

- go to tab 'Assets & Connectivity' and add the variables, that were configured within the Modbus TCP Connector

- ## Use Store Data in Common Configurator
- (It´s necessary to have IIH Essentials installed)
- open Define Data in Common Configurator
- choose Modbus TCP Connector
- Add asset, add tags to the asset and deploy

![DataServiceAdapter](/docs/graphics/Storedata.png)

