# Configuration

- [Configuration](#configuration)
  - [Configure Databus](#configure-databus)
  - [Configure Modbus TCP Configurator](#modbus-tcp-configurator)
  - [Configure IE-Flow Creator](#ie-flow-creator)
   


## Configure Databus

 Open the Databus and launch the configurator.

Add a user with the following topic:
`"ie/#"`

![ie_databus_user](graphics/IE_Databus_User.PNG)

Deploy the configuration.

![ie_databus](graphics/IE_Databus.PNG)

## Configure Modbus TCP Configurator

Open the app Modbus TCP Configurator.

On the left corner you can add your Data Source.

![Modbus_TCP_Configurator]](graphics/add_data_source.png)

Add multiple Tags(graphics/add_tag.png) 

Adjust user credentials (graphics/add_credentials.png)

Deploy and start the project(graphics/workflow_project.png)

![IE_Flow_Creator](graphics/flow_creator.png)

Observe the incoming data via IE-Flow Creator "MQTT-In Node"(graphics/IE_Flow_Creator.png)
