---
title: "Docker"
#date: 2018-12-11
draft: false
tags: ["#docker", "#integrations", ]
author: Lawrence Lane
---
Docker is an open way of building, shipping, and running distributed applications anywhere using containers and images. CloudWisdom can be used to monitor the performance of your Docker host and containers.

Each Docker container you have running will be listed as  Docker Container in your [Inventory Explorer][1]. Each Docker host you have running will be listed as  SERVER in your Inventory Explorer. You’ll be able to identify which of your  SERVER elements are Docker hosts via the Docker Summary [dashboard][2] (if you have the Docker package installed).

CloudWisdom also offers a Docker container with the Linux agent configured to send Docker host and container metrics. The [Linux Agent Docker container][3] should be used only if the Linux agent cannot be installed on the host.

## Configuration
The [Linux Agent][4] must be installed before proceeding. If you need to disable the Linux integration or view the unique API key assigned to your account, navigate to the Integrations page under the user account drop-down menu and click the integration designated as Infrastructure under the Integration column.

1. Navigate to the Linux Agent configuration file, `/opt/netuitive-agent/conf/netuitive-agent.conf`.
2. Change the **enabled** setting to `True` in the `[[NetuitiveDockerCollector]]` section of the file.
3. Optionally, add a metric blacklist or whitelist to reduce the number of metrics you receive. See our [Regex Guide][5] for examples.  
4. **Save** the file, and **restart** the Linux agent.

This integration’s package will be automatically enabled and provisioned to your account as soon as CloudWisdom receives data from the integration. The PACKAGES button on the integration setup page will become active once data is received, so you’ll be able to disable and re-enable the package at will.

## Collector Options
| Option                 | Default | Description                                                                                |
|------------------------|---------|--------------------------------------------------------------------------------------------|
| enabled                | False   | Enable collecting Docker metrics.                                                          |
| minimal                | True    | Minimal mode collection. See [here][6] for metrics collected.                              |
| simple                 |         | Simple mode collection. See [here][7] for metrics collected.                               |
| byte_unit              |         | Default numeric output(s).                                                                 |
| measure_collector_time |         | Measure the collector’s run time in milliseconds.                                          |
| memory_path            |         | The path to the kernel’s CGroups memory file system.                                       |
| metrics_blacklist      |         | Regex list to match metrics to block. Mutually exclusive with metrics_whitelist option.    |
| metrics_whitelist      |         | Regex list to match metrics to transmit. Mutually exclusive with metrics_blacklist option. |



[1]: /capacity-monitoring/inventory
[2]: /dashboards/
[3]: /integrations/agents/linux-agent/LINUX-docker-install
[4]: /integrations/agents/linux-agent
[5]: /capacity-monitoring/policies/regex-guide
[6]: /integrations/docker/docker-collectors/#minimal-mode-default
[7]: /integrations/docker/docker-collectors/#simple-mode

