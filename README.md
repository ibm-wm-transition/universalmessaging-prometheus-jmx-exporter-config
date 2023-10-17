# Universal Messaging Prometheus JMX Exporter Configuration (Universal Messaging Version 10.15)

Copyright (c) 1999 - 2011 my-Channels Ltd
Copyright (c) 2012 - 2022 Software AG, Darmstadt, Germany and/or Software AG USA Inc., Reston, VA, USA, and/or its subsidiaries and/or its affiliates and/or their licensors.

SPDX-License-Identifier: Apache-2.0

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at (http://www.apache.org/licenses/LICENSE-2.0). Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.

# Introduction
This repository provides configurations for integrating Universal Messaging server with Prometheus JMX Exporter. For comprehensive guidance, please refer to the Universal Messaging documentation:

- [Using JMX to Monitor Universal Messaging](https://documentation.softwareag.com/universal_messaging/num10-15/webhelp/num-webhelp/#page/num-webhelp%2Fto-using_jmx.html%23)
- [Monitoring Universal Messaging Using Prometheus](https://documentation.softwareag.com/universal_messaging/num10-15/webhelp/num-webhelp/#page/num-webhelp%2Fto-ops_monitoring_with_prometheus.html%23)

# Details
## Full Prometheus monitoring capabalities (jmx_sag_um_exporter.yaml) 
- This configuration is recommended by Software AG for integrating the Prometheus JMX Exporter with Universal Messaging. It provides metrics suitable for statistical data collection in Prometheus. These metrics are also listed in [JMX Metrics in jmx_sag_um_exporter.yaml](https://documentation.softwareag.com/universal_messaging/num10-15/webhelp/num-webhelp/#page/num-webhelp%2Fre-jmx_exporter_metrics.html%23).
- To find all available JMX metrics for server monitoring, please refer to the section [Universal Messaging JMX Metrics](https://documentation.softwareag.com/universal_messaging/num10-15/webhelp/num-webhelp/#page/num-webhelp%2Fre-jmx_metrics.html%23).

## Health Monitoring Prometheus capabalities  
For health monitoring guidelines, please refer to [Notes on Health Monitoring with Prometheus](https://documentation.softwareag.com/universal_messaging/num10-15/webhelp/num-webhelp/#page/num-webhelp%2Fre-prometheus_metrics_usage_notes.html%23wwconnect_header).

# Notes
- For more information on the Prometheus JMX Exporter, please check [Prometheus JMX Exporter](https://github.com/prometheus/jmx_exporter).
- For more information on how to configure the Prometheus JMX Exporter for Universal Messaging server, please follow the [Universal Messaging documentation](https://documentation.softwareag.com/universal_messaging/num10-15/webhelp/num-webhelp/#page/num-webhelp%2Fta-ops_enable_jmx_exporter_agent.html%23).

**Note**: The provided `jmx_sag_um_exporter.yaml` is a configuration example that can be customized according to specific requirements. The same flexibility applies to the recommended health monitoring metric thresholds.

---

Please note that these tools are provided "as-is" without warranty or support and do not constitute part of the Software AG product suite. Users are free to use, fork, and modify them, subject to the license agreement. While Software AG welcomes contributions, we cannot guarantee to include every contribution in the master project.
