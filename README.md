Plugin for monitoring the ActiveMQ 
==============================================

This plugin monitors the performance metrics of your Apache ActiveMQ instances and destinations used and their activity along with connections and subscriptions.

### Prerequisites

- Download and install the latest version of the [Site24x7 Linux agent] / [Site24x7 Windows agent] (https://www.site24x7.com/app/client#/admin/inventory/add-monitor) in the server where you plan to run the plugin. 

- Plugin Uses "jmxquery" python library. This module is used to execute the jmx query and get data. Execute the below command to install python jmxquery modeule in your server.  

		pip install jmxquery


### Plugin installation
---
##### Linux 

- Create a directory "activemq" under Site24x7 Linux Agent plugin directory - 
      Linux (Root)      ->   /opt/site24x7/monagent/plugins/activemq
      Linux (Non Root)  ->   /home/<user_name>/site24x7/monagent/plugins/activemq

##### Windows 

- Create a directory "activemq" under Site24x7 Windows Agent plugin directory - 
      Windows           ->   C:\Program Files (x86)\Site24x7\WinAgent\monitoring\Plugins\activemq

- Download all the files in "activemq" folder and place it under the "activemq" directory

	  wget https://raw.githubusercontent.com/mrkksparrow/Site24x7_ActiveMQ/main/activemq.py?token=AJUVBT456SOY4BCPY7OW4P3AKIDTU
	  wget https://raw.githubusercontent.com/mrkksparrow/Site24x7_ActiveMQ/main/acticemq.cfg?token=AJUVBTY6WNAMQ6F6FXOVVSTAKIDRY
	
- Configure the keys to be monitored, as mentioned in the configuration section below.

- Execute the below command with appropriate arguments to check for the valid json output.  

		python activemq.py –-host_name=localhost -–port=1099 -–broker_name=<your_broker_name> --destination_name=<your_destination_name>


The agent will automatically execute the plugin within five minutes and send performance data to the Site24x7 data center.

### Configurations
---
	[display_name]
	host_name = “<your_host_name>”
	port = “1099”
	broker_name = “<your_broker_name>”
	destination_name = “<your_destination_name>”

### Metrics Captured
---
Memory Percent Usage - “memory_percent_usage” metric calculates the percentage of memory used by the given Broker in your ActiveMQ Setup. [percent]

Storage Percent Usage - “storage_percent_usage” metric calculates the percentage of storage used by the given Broker in your ActiveMQ Setup. [percent]

Temp Percent Usage - “temp_percent_usage” metric calculates the percentage of temp used by the given Broker in your ActiveMQ Setup. [percent]

Average Enqueue Time - “avg_enqueue_time” metric calculate the average amount of time, the messages remained enqueued in the queue of the given Broker of your ActiveMQ Setup. [millisecond]

Minimum Enqueue Time - “min_enqueue_time” metric calculate the minimum amount of time, the messages remained enqueued in the queue of the given Broker of your ActiveMQ Setup. [millisecond]

Maximum Enqueue Time - “max_enqueue_time” metric calculate the maximum amount of time, the messages remained enqueued in the queue of the given Broker of your ActiveMQ Setup. [millisecond]

Dequeue Count - “dequeue_count” metric calculate the number of messages that remained dequeued in the queue of the given Broker of your ActiveMQ Setup. [message]

Enqueue Count - “enqueue_count” metric calculate the number of messages that remained enqueued in the queue of the given Broker of your ActiveMQ Setup. [message]

Consumer Count - “consumer_count” metric counts and records the number of consumers connected in the queue of the given Broker of your ActiveMQ Setup. [count]

Producer Count - “producer_count” metric counts and records the number of producers connected in the queue of the given Broker of your ActiveMQ Setup. [count]

Dispatch Count - “dispatch_count”  metric counts and records the number of messages that have been dispatched in the queue of the given Broker of your ActiveMQ Setup. [message]

Queue Size - “queue_size” metric calculate the number of messages that remained in the queue of the given Broker of your ActiveMQ Setup. [message]

Memory Percent - “memory_percent” metric calculate the percentage of memory currently used in the queue of the given Broker of your ActiveMQ Setup. [percent]

Expired Count - “expired_count” metric calculate the number of messages that have been expired in the queue of the given Broker of your ActiveMQ Setup. [message]

In Flight Count - “in_flight_count” metric calculate the number of messages that have been in flight in the queue of the given Broker of your ActiveMQ Setup. [message]		
