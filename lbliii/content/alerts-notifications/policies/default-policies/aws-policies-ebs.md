---
title: "AWS EBS Policies"
date: 2018-04-12
draft: true
categories:
tags: ["alerts", "notifications", "policies", "default policies", "ebs", "aws"]
author: Lawrence Lane
---
Before reading about the EBS default policy, it is important to understand the following Metricly computed metrics.

- **Average Latency**: Average Latency is straightforward as it represents the average amount of time that it takes for a disk operation to complete.
- **Queue Length Differential**: Queue Length Differential measures the difference between the actual disk queue length and the “ideal” disk queue length.The ideal queue length is based on Amazon’s rule of thumb that for every 200 IOPS you should have a queue length of 1. In theory, a well-optimized volume should have a queue length differential that tends to hover around 0. In practice, we have seen volumes with extremely low latency (< 0.0001) have queue length differentials that are higher than 0; presumably this is because the latency is much lower than Amazon is assuming for their rule of thumb. Even in these cases, the differential is a pretty steady number.

| Policy name                                              | Duration | Condition 1                                                                                    | (and) Condition 2                                     | Cat.     | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|----------------------------------------------------------|----------|------------------------------------------------------------------------------------------------|-------------------------------------------------------|----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Elevated Queue Length Differential with Elevated Latency | 30 min   | metricly.aws.ebs.queuelengthdifferentialhas an upper baseline deviation + static threshold > 1 | metricly.aws.ebs.averagelatency has an upper baseline | CRITICAL | The first condition of the policy looks for an upper deviation as the first indication that the disk may be getting more traffic than it can keep up with. It also checks for the differential to be greater than 1 in order to avoid false alarming in cases where the differential is very low.The second condition is added because an elevated queue differential by itself is not necessarily a bad thing. We only want to alarm if your differential is higher than normal AND your latency is higher than normal.                                                                                                                                    |
| Elevated iops Utilization with low Burst Balance         | 5 min    | netuitive.aws.ebs.iopsutilization  => 90                                                       | aws.ebs.burstbalance <= 10.                           |          | This policy looks at two metrics: IOPS Utilizaton and EBS Burst Balance. High IOPS Utilization (a Metricly computed metric) indicates the disk is highly utilized and a low EBS Burst Balance indicates the disk is so highly utilized that most of the burst available to the disk is depleted. Once the burst balance is fully depleted available disk IOPS will fall causing slowdowns in I/O and deteriorated performance of the application using the volume.\n\nCheck this volume and the application using it to see if the I/O profile has changed. Consider using Provisioned IOPS to increase the disk performance if this new profile is normal. |