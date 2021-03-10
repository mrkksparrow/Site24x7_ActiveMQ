Plugin for monitoring the ActiveMQ 
==============================================

This plugin monitors the performance metrics of your Apache ActiveMQ instances and destinations used and their activity along with connections and subscriptions.

### Prerequisites

- Download and install the latest version of the [Site24x7 Linux agent] / [Site24x7 Windows agent] (https://www.site24x7.com/app/client#/admin/inventory/add-monitor) in the server where you plan to run the plugin. 

- Plugin Uses "jmxquery" python library. This module is used to execute the jmx query and get data


### Plugin installation
---
##### Linux 

- Create a directory "activemq" under Site24x7 Linux Agent plugin directory - 
      Linux (Root)      ->   /opt/site24x7/monagent/plugins/activemq
      Linux (Non Root)  ->   /home/<user_name>/site24x7/monagent/plugins/activemq
      Windows           ->   C:\Program Files (x86)\Site24x7\WinAgent\monitoring\Plugins\activemq

- Download all the files in "activemq" folder and place it under the "activemq" directory

	  wget https://raw.githubusercontent.com/mrkksparrow/Site24x7/main/activemq.py?token=AJUVBT5U4WZGCS22LN7E4OLAKICBS
	  wget https://raw.githubusercontent.com/mrkksparrow/Site24x7/main/acticemq.cfg?token=AJUVBT3CS4AWEKPCVBKF2PLAKIB7Q
	
- Configure the keys to be monitored, as mentioned in the configuration section below.

- Execute the below command with appropriate arguments to check for the valid json output.  

		python process_availability.py --process="java" --plugin_version="1" --heartbeat="True"


The agent will automatically execute the plugin within five minutes and send performance data to the Site24x7 data center.

### Configurations
---
	process = Process to be monitored.
	plugin_version = 1
	heartbeat = True

### Metrics Captured
---
	process_name - Name of the process being monitored. 
	process_running - Total number of process running 			
