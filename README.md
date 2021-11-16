# Universal Messaging Prometheus JMX exporter configuration

Copyright (c) 1999 - 2011 my-Channels Ltd
Copyright (c) 2012 - 2020 Software AG, Darmstadt, Germany and/or its licensors

SPDX-License-Identifier: Apache-2.0

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at (http://www.apache.org/licenses/LICENSE-2.0). Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.

# Details
The repository contains best practices example of how Universal Messaging server can be integrated with Prometheus jmx agent.
Following sample configurations are provided:
## Full Prometheus monitoring capabalities (jmx_sag_um_exporter.yaml) 
This file defines the recommended by Software AG configuration for the Prometheus JMX Exporter agent when configured with the UM server, when Prometheus will be used as a monitoring tool to collect all possible UM metrics.
This configuration exports many verbose metrics which might be usefull if collecting statistical data in Prometheus is needed.

## Health Monitoring Prometheus capabalities (jmx_sag_um_exporter_health_monitoring.yaml) 
This file defines the recommended by Software AG configuration for the Prometheus JMX Exporter agent when configured with the UM server, when Prometheus is used to monitor UM's health.
This configuration is more lightweight and exports only the metrics important for monitoring UM's health.
Bellow is a short explanation how these metrics can be used for monitoring UM's server health:

### Server
**sag_um_server_cpu_usage_ratio**, if > 60% this means the UM server is hitting the CPU limits

**sag_um_server_memory_heap_usage_bytes**, if stays constantly > 80% of the max configured heap that might be an indication that heap limits are reached

**sag_um_server_memory_direct_usage_megabytes**, if stays constantly > 80% of the max configured direct memory

### Cluster
**sag_um_cluster_processqueue_total**, if > 100 and constantly increasing this might be an indication in delays in the inter-cluster synchronization, short peaks are concidered fine

**sag_um_cluster_clientqueue_total**, if > 100 and constantly increasing this might be an indication in delays in the inter-cluster synchronization, short peaks are concidered fine

**sag_um_cluster_commsqueue_total**, if > 100 and constantly increasing this might be an indication in delays in the inter-cluster synchronization, short peaks are concidered fine

**sag_um_cluster_currentstate_info**, if the server is in good cluster state- the value should be Master or Slave. If the value is something else or is changing often that is an indication of a cluster instability
Note: Value is always 1, the label "state" need to be monitored

### Threads
**sag_um_threadpool_queueedtasks_total**, for each thread pool should be lower then 100. Short peaks are allowed, but if the value stays high and\or increasing that is an indication that the particular thread pool is exhausted and server is not operating properly.

**sag_um_threadpool_stalledtasks_total**, for each thread pool should be always 0. If bigger then 0 that means that some thread is taking more then 60secs(default value). This is an indication of some resource exhaustion or some kind of a dead\live lock.

### Topics
**sag_um_topic_noofevents_total**, should be smaller then X, use case specific. X can be 10 000, 100 000, etc. If threshold is exceeded that means events are piling up in the system and this can lead to heap\disk\performance problems.

**sag_um_topic_memory_usage_bytes**, should be smaller then X, use case specific. X can be- 100MB, 1000MB, etc. 

**sag_um_topic_disk_usage_bytes**, should be smaller then X, use case specific. X can be- 500MB, 1GB, etc.

**sag_um_topic_durable_connection_pending_total**, if number is constantly high > X, this can be an indication that client is processing events slow. X can be use case specific- 100, 200, etc.

### Queue
**sag_um_queue_events_total**, should be smaller then X, use case specific. X can be 10 000, 100 000, etc. If threshold is exceeded that means events are piling up in the system and this can lead to heap\disk\performance problems.

**sag_um_queue_memory_usage_bytes**, should be smaller then X, use case specific. X can be- 100MB, 1000MB, etc. 

**sag_um_queue_disk_usage_megabytes**, should be smaller then X, use case specific. X can be- 500MB, 1GB, etc.

**sag_um_queue_connection_pending_total**, if number is constantly high > X, this can be an indication that client is processing events slow. X can be use case specific- 100, 200, etc.

# Notes
- For more information on the Prometheus JMX Exporter, please check [Prometheus JMX Exporter](https://github.com/prometheus/jmx_exporter).
- For more information on how to configure the Prometheus JMX Exporter for Universal Messaging server, please follow the [Universal Messaging documentation]( https://documentation.softwareag.com/universal_messaging/num10-7/10-7_UM_webhelp/index.html#page/um-webhelp%2Fta-ops_enable_jmx_exporter_agent.html%23)

**Note**: Universal Messaging Prometheus integration is supported from Universal Messaging version 10.7 onwards.

**Note**: The jmx_sag_um_exporter.yaml and jmx_sag_um_exporter_health_monitoring.yaml are only examples of how the Prometheus JMX Exporter can be configured, customer might edit the files according to their needs.

**Note**: Starting from version 10.11 the jmx_sag_um_exporter.yaml is shipped by default with the Universal Messaging server installation in following location: <UM install folder>\server\<UM server instance>\bin\jmx_sag_um_exporter.yaml. The jmx_sag_um_exporter.yaml configuration still can be used in version 10.7.

  ------------------------------

These tools are provided as-is and without warranty or support. They do not constitute part of the Software AG product suite. Users are free to use, fork and modify them, subject to the license agreement. While Software AG welcomes contributions, we cannot guarantee to include every contribution in the master project.
