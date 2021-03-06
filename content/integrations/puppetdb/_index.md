---
title: "PuppetDB"
#date: 2018-12-12
draft: false
tags: ["#puppetDB", "#integrations" ]
author: Lawrence Lane
---

## Prerequisites
- [Linux Agent][1]

## Configure

### 1. Update the Configuration File

1. Open **PuppetDBCollector.conf** in the collectors folder, `/opt/netuitive-agent/conf/collectors`.
2. Change the **enabled** setting to `True`,]
3. **Save** the file and **restart** the agent.

```
enabled = True
host = localhost
port = 8080
```
4\. View your data.

{{% notice info %}}
CloudWisdom starts displaying data **in approximately 5 minutes**.You can adjust the default settings as necessary depending on your environment.
{{% /notice %}}

## Collector Options

| Setting                | Default   | Description                                                                   | Type     |
|------------------------|-----------|-------------------------------------------------------------------------------|----------|
| byte_unit              | byte      | Default numeric output(s)                                                     | str      |
| enabled                | FALSE     | Enable collecting these metrics                                               | bool     |
| host                   | localhost | Hostname to collect from                                                      | str      |
| measure_collector_time | FALSE     | Collect the collector run time in ms                                          | bool     |
| metrics_blacklist      | None      | Regex to match metrics to block. Mutually exclusive with metrics_whitelist    | NoneType |
| metrics_whitelist      | None      | Regex to match metrics to transmit. Mutually exclusive with metrics_blacklist | NoneType |
| port                   | 8080      | Port number to collect from                                                   | int      |


[1]: /integrations/agents/linux-agent
[2]: /dashboards/
[3]: /capacity-monitoring/policies
