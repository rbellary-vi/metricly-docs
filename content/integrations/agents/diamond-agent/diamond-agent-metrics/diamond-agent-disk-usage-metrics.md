---
title: "Diamond Disk Usage Metrics"
#date: 2018-12-11
draft: false
tags: ["#diamond", "#integrations", "#agents", "#diskspace" ]
author: Lawrence Lane
---

## Computed
| Fully Qualified Name(FQN)             | Description                                                               | Units | Min | Max  | BASE | CORR | UTIL |
|---------------------------------------|---------------------------------------------------------------------------|-------|-----|------|------|------|------|
| netuitive.linux.iostat.totalreads  | Total reads across all disks. **Computation**: data.sum(‘iostat\\..*\\.reads)   |       | 0   | none | yes  | no   | no   |
| netuitive.linux.iostat.totalwrites | Total writes across all disks. **Computation**: data.sum(‘iostat\\..*\\.writes) |       | 0   | none | yes  | no   | no   |
