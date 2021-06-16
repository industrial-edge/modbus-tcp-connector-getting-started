# Configuration

- [Configuration](#configuration)
    - [Configure Databus](#configure-databus)
  - [Configure Modbus TCP Configurator](#modbus-tcp-configurator)
    - [Configure IE-Flow Creator](#ie-flow-creator)
   


### Configure Databus

In your IEM open the Databus and launch the configurator.

Add a user with this topic:
`"ie/#"`

![ie_databus_user](graphics/IE_Databus_User.PNG)

![ie_databus](graphics/IE_Databus.PNG)

Deploy the configuration.

## Configure Modbus TCP Configurator

In your IED Web UI open the app Modbus TCP Configurator.

Click "Add Data Source" at the top of the left side.

![Modbus_TCP_Configurator]](graphics/add_data_source.PNG)

Add your Tags(graphics/add_tag.PNG) 

Click on the right corner Settings and add your Databus credentials(graphics/add_credentials.PNG)

Afterwards you can deploy and start the project(graphics/workflow_project.PNG)

![IE_Flow_Creator](graphics/IE_Flow_Creator.png)

Select the "MQTT-In Node" and check if you're able to browse the metadata(graphics/flow_creator.PNG)
