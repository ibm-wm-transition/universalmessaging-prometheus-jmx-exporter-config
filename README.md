# Universal Messaging Prometheus JMX exporter configuration

Copyright (c) 1999 - 2011 my-Channels Ltd
Copyright (c) 2012 - 2020 Software AG, Darmstadt, Germany and/or its licensors

SPDX-License-Identifier: Apache-2.0

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at (http://www.apache.org/licenses/LICENSE-2.0). Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.

# Details
The repository contains best practices example of how Universal Messaging server can be integrated with Prometheus jmx agent.

The jmx_sag_um_exporter.yaml file defines the recommended by Software AG configuration for the Prometheus JMX Exporter agent when configured with the UM server.
- For more information on the Prometheus JMX Exporter, please check [Prometheus JMX Exporter](https://github.com/prometheus/jmx_exporter).
- For more information on how to configure the Prometheus JMX Exporter for Universal Messaging server, please follow the [Universal Messaging documentation]( https://documentation.softwareag.com/universal_messaging/num10-7/10-7_UM_webhelp/index.html#page/um-webhelp%2Fta-ops_enable_jmx_exporter_agent.html%23)

Note: Universal Messaging Prometheus integration is supported from Universal Messaging version 10.7 onwards.

Note: The jmx_sag_um_exporter.yaml is only an example of how the Prometheus JMX Exporter can be configured, customer might edit it according to their needs.

Note: Starting from version 10.11 the jmx_sag_um_exporter.yaml is shipped with the Universal Messaging server installation in following location: <UM install folder>\server\<UM server instance>\bin\jmx_sag_um_exporter.yaml. The jmx_sag_um_exporter.yaml configuration still can be used in version 10.7.
