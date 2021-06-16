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

Open the app Modbus TCP Configurator.On the left corner you can add the Data Source. 

![add_data_source](graphics/add_data_source.png)

Add multiple Tags

![add_tag](graphics/add_tag.png) 

Adjust user credentials 

![add_credentials](graphics/add_credentials.png)

Deploy and start the project

![workflow_project](graphics/workflow_project.png)

Open IE-Flow Creator 

![IE_Flow_Creator](graphics/IE_Flow_Creator.png)

Observe the incoming data via IE-Flow Creator "MQTT-In Node"

![flow_creator](graphics/flow_creator.png) 
