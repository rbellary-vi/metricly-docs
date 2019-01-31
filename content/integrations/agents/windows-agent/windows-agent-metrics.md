---
title: "Metrics"
#date: 2018-12-11
draft: false
tags: ["#windows", "#integrations", "#metrics"]
author: Lawrence Lane
---
## Collected

| Friendly Name                 | Fully Qualified Name (FQN)                   | Description                                                                                                                                                                                                                                                                                          | Statistic | Units           | Min | Max  | Sparse Data Strategy (SDS) | BASE | CORR | UTIL |
|-------------------------------|----------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|-----------------|-----|------|----------------------------|------|------|------|
| Avg. Disk Queue Length        | logical_disk.*.avg_queue_length              | Average queue length for the logical disk.                                                                                                                                                                                                                                                           | average   | count           | 0   | none | none                       | yes  | no   | no   |
| Free Megabytes                | logical_disk.*.megabytes_free                | Space free on the logical disk expressed in megabytes.                                                                                                                                                                                                                                               | average   | megabytes       | 0   | none | none                       | yes  | no   | no   |
| % Free Space                  | logical_disk.*.percent_free                  | Space free on the logical disk expressed as a percentage.                                                                                                                                                                                                                                            | average   | percent         | 0   | 100  | none                       | yes  | no   | no   |
| Available Bytes               | memory.available_bytes                       | Available memory in bytes.                                                                                                                                                                                                                                                                           | average   | bytes           | 0   | none | none                       | yes  | no   | no   |
| Cache Faults/sec              | memory.cache_faults_per_sec                  | The rate at which faults occur when a page sought in the file system cache is not found and must be retrieved from elsewhere in memory or from disk.                                                                                                                                                 | average   | faults/second   | 0   | none | none                       | yes  | no   | no   |
| Committed Bytes               | memory.committed_bytes                       | The amount of committed virtual memory in bytes. Committed memory is the physical memory which has space reserved on the disk paging file(s).                                                                                                                                                        | average   | bytes           | 0   | none | none                       | yes  | no   | no   |
| Page Faults/sec               | memory.page_faults_per_sec                   | Average number of pages faulted per second.                                                                                                                                                                                                                                                          | average   | faults/second   | 0   | none | none                       | yes  | yes  | no   |
| % Usage                       | memory.page_file_percent_used                | Percentage of the paging file(s) in use.                                                                                                                                                                                                                                                             | average   | percent         | 0   | 100  | none                       | yes  | no   | no   |
| Pages Input/sec               | memory.pages_input_per_sec                   | The rate at which pages are read from disk to resolve hard page faults.                                                                                                                                                                                                                              | average   | pages/second    | 0   | none | none                       | yes  | no   | no   |
| Pages Output/sec              | memory.pages_output_per_sec                  | The rate at which pages are written to disk to free up space in physical memory                                                                                                                                                                                                                      | average   | pages/second    | 0   | none | none                       | yes  | no   | no   |
| Pages/sec                     | memory.pages_per_sec                         | The rate at which pages are read from or written to disk to resolve hard page faults.                                                                                                                                                                                                                | average   | pages/second    | 0   | none | none                       | yes  | yes  | no   |
| % Committed Bytes in Use      | memory.percent_committed_in_use              | Percentage of committed bytes in use.                                                                                                                                                                                                                                                                | average   | percent         | 0   | 100  | none                       | yes  | no   | no   |
| Bytes Received/sec            | network_interface.*.bytes_received_per_sec   | Network bytes received per second.                                                                                                                                                                                                                                                                   | average   | bytes/second    | 0   | none | none                       | yes  | no   | no   |
| Bytes Sent/sec                | network_interface.*.bytes_sent_per_sec       | Network bytes sent per second.                                                                                                                                                                                                                                                                       | average   | bytes/second    | 0   | none | none                       | yes  | no   | no   |
| Bytes Total/sec               | network_interface.*.bytes_total_per_sec      | Total network bytes sent and received per second.                                                                                                                                                                                                                                                    | average   | bytes/second    | 0   | none | none                       | yes  | no   | no   |
| Current Bandwidth             | network_interface.*.current_bandwidth        | Bandwidth the network is currently capable of, expressed in bits per second.                                                                                                                                                                                                                         | average   | bits/second     | 0   | none | none                       | yes  | no   | no   |
| Output Queue Length           | network_interface.*.output_queue_length      | Length of the output packet queue, in packets.                                                                                                                                                                                                                                                       | average   | packets         | 0   | none | none                       | yes  | no   | no   |
| Packets Outbound Errors       | network_interface.*.packets_outbound_errors  | Outbound packet errors.                                                                                                                                                                                                                                                                              | sum       | errors          | 0   | none | none                       | yes  | no   | no   |
| Packets Received Errors       | network_interface.*.packets_received_errors  | Inbound packet errors.                                                                                                                                                                                                                                                                               | sum       | errors          | 0   | none | none                       | yes  | no   | no   |
| Packets Received/Sec          | network_interface.*.packets_received_per_sec | Network packets received per second.                                                                                                                                                                                                                                                                 | average   | packets/second  | 0   | none | none                       | yes  | no   | no   |
| Packets Sent/Sec              | network_interface.*.packets_sent_per_sec     | Network packets sent per second.                                                                                                                                                                                                                                                                     | average   | packets/second  | 0   | none | none                       | yes  | no   | no   |
| Avg. Disk Queue Length        | physical_disk.*.avg_queue_length             | Average number of both read and write requests that were queued for the physical disk.                                                                                                                                                                                                               | average   | count           | 0   | none | none                       | yes  | yes  | no   |
| Avg. Disk Read Queue Length   | physical_disk.*.avg_read_queue_length        | Average number of read requests that were queued for the physical disk.                                                                                                                                                                                                                              | average   | count           | 0   | none | none                       | yes  | no   | no   |
| Avg. Disk sec/Read            | physical_disk.*.avg_sec_per_read             | Average disk read time in seconds.                                                                                                                                                                                                                                                                   | average   | seconds         | 0   | none | none                       | yes  | no   | no   |
| Avg. Disk sec/Write           | physical_disk.*.avg_sec_per_write            | Average disk write time in seconds.                                                                                                                                                                                                                                                                  | average   | seconds         | 0   | none | none                       | yes  | no   | no   |
| Avg. Disk Write Queue Length  | physical_disk.*.avg_write_queue_length       | Average number of write requests that were queued for the physical disk.                                                                                                                                                                                                                             | average   | count           | 0   | none | none                       | yes  | no   | no   |
| % Idle Time                   | physical_disk.*.percent_idle_time            | Percentage of time the physical disk was idle.                                                                                                                                                                                                                                                       | average   | percent         | 0   | 100  | none                       | yes  | no   | no   |
| % Idle time                   | processor.*.percent_idle_time                | Percentage of time a specific CPU was idle.                                                                                                                                                                                                                                                          | average   | percent         | 0   | 100  | none                       | yes  | yes  | no   |
| % Interrupt Time              | processor.*.percent_interrupt_time           | Percentage of time a specific CPU was processing interrupts.                                                                                                                                                                                                                                         | average   | percent         | 0   | 100  | none                       | yes  | no   | no   |
| % Privleged Time              | processor.*.percent_privileged_time          | Percentage of time a specific CPU was processing system threads.                                                                                                                                                                                                                                     | average   | percent         | 0   | 100  | none                       | yes  | no   | no   |
| % Processor Time              | processor.*.percent_processor_time           | Percentage of time a specific CPU was busy.                                                                                                                                                                                                                                                          | average   | percent         | 0   | 100  | none                       | yes  | no   | no   |
| % User Time                   | processor.*.percent_user_time                | Percentage of time a specific CPU was processing user threads.                                                                                                                                                                                                                                       | average   | percent         | 0   | 100  | none                       | yes  | no   | no   |
| Total % Idle Time             | processor._Total.percent_idle_time           | The percentage of idle time across all CPUs.                                                                                                                                                                                                                                                         | average   | percent         | 0   | 100  | none                       | yes  | no   | no   |
| Total % Interrupt Time        | processor._Total.percent_intterupt_time      | The percentage of time spent processing interrupts across all CPUs.                                                                                                                                                                                                                                  | average   | percent         | 0   | 100  | none                       | yes  | no   | no   |
| Total % Privileged Time       | processor._Total.percent_privileged_time     | The percentage of time spent on system processes across all CPUs. This includes time spend processing interrupts, so percent_interrupt_time is a component of percent_privileged_time.                                                                                                               | average   | percent         | 0   | 100  | none                       | yes  | no   | no   |
| Total % Processor time        | processor._Total.percent_processor_time      | This represents the total CPU utilization across all processors.                                                                                                                                                                                                                                     | average   | percent         | 0   | 100  | none                       | yes  | yes  | yes  |
| Total % User Time             | processor._Total.percent_user_time           | The percentage of time spent on user processes across all CPUs.                                                                                                                                                                                                                                      | average   | percent         | 0   | 100  | none                       | yes  | no   | no   |
| Context Switches/sec          | system.context_switches_per_sec              | The combined rate at which all processors on the computer are switched from one thread to another.                                                                                                                                                                                                   | average   | switches/second | 0   | none | none                       | yes  | yes  | no   |
| Processes                     | system.processes                             | The number of processes currently running.                                                                                                                                                                                                                                                           | average   | count           | 0   | none | none                       | yes  | yes  | no   |
| Processor Queue Length        | system.processor_queue_length                | The number of threads in the processor queue.                                                                                                                                                                                                                                                        | average   | count           | 0   | none | none                       | yes  | no   | no   |
| System calls/sec              | system.system_calls_per_sec                  | The combined rate of calls to operating system service routines by all processes running on the computer.                                                                                                                                                                                            | average   | calls/second    | 0   | none | none                       | yes  | no   | no   |
| Get Requests/sec              | Web_get_requests_per_sec                     | The number of GET requests made per second.                                                                                                                                                                                                                                                          |           |                 |     |      |                            | yes  | no   | no   |
| Post Requests/sec             | Web_post_requests_per_sec                    | The number of POST requests made per second.                                                                                                                                                                                                                                                         |           |                 |     |      |                            | yes  | no   | no   |
| Current Connections           | Web_current_connections                      | The number of connections currently established with the web service.                                                                                                                                                                                                                                |           |                 |     |      |                            | yes  | no   | no   |
| Connection Attempts/sec       | Web_connect_attempts_per_sec                 | The number of connection attempts per second.                                                                                                                                                                                                                                                        |           |                 |     |      |                            | yes  | no   | no   |
| Exceptions Thrown/sec         | CLR_count_exceptions_thrown                  | The number of exceptions thrown per second. This includes both .NET exceptions and unmanaged exceptions that are converted into .NET exceptions.                                                                                                                                                     |           |                 |     |      |                            | yes  |      |      |
| % Time in Garbage Collection  | CLR_percent_time_in_GC                       | The percentage of elapsed time spent performing garbage collection since the last garbage collection cycle.                                                                                                                                                                                          |           |                 |     |      |                            | yes  |      |      |
| Application Restarts          | ASP_application_restarts                     | The number of times an application has been restarted during the server’s lifetime.                                                                                                                                                                                                                  |           |                 |     |      |                            | yes  |      |      |
| Requests Current              | ASP_requests_current                         | The current number of requests, including those that are queued, currently executing, or waiting to be written to the client. Under the ASP.NET process model, when this counter exceeds requestQueueLimit defined in the processModel configuration section, ASP.NET will begin rejecting requests. |           |                 |     |      |                            | yes  |      |      |
| Request Wait Time             | ASP_request_wait_time                        | The time (in ms) that the most recent request waited in the processing queue.                                                                                                                                                                                                                        |           |                 |     |      |                            | yes  |      |      |
| Requests Queued               | ASP_requests_queued                          | The number of requests waiting for service from the queue.                                                                                                                                                                                                                                           |           |                 |     |      |                            | yes  |      |      |
| Request Execution Time        | ASP_request_execution_time                   | The time it took (in ms) to execute the most recent request.                                                                                                                                                                                                                                         |           |                 |     |      |                            | yes  |      |      |
| Percent Processor Time        | sql_server.percent_processor_time            | The percentage of time the processor is busy.                                                                                                                                                                                                                                                        |           |                 |     |      |                            |      |      |      |
| User Connections              | sql_server.user_connections                  | The number of users currently connected to the SQL Server.                                                                                                                                                                                                                                           |           |                 |     |      |                            |      |      |      |
| Blocked Processes             | sql_server.processes_blocked                 | The number of processes that are blocked.                                                                                                                                                                                                                                                            |           |                 |     |      |                            |      |      |      |
| Total Lock Waits Per Second   | sql_server.total_lock_waits_per_sec          | The number of locks per second that had to wait for resources.                                                                                                                                                                                                                                       |           |                 |     |      |                            |      |      |      |
| Batch Requests Per Second     | sql_server.batch_requests_per_sec            | The number of batches the server is receiving per second.                                                                                                                                                                                                                                            |           |                 |     |      |                            |      |      |      |
| SQL Compilations Per Second   | sql_server.sqL-compilations_per_sec          | The number of SQL compiles per second.                                                                                                                                                                                                                                                               |           |                 |     |      |                            |      |      |      |
| SQL Recompilations Per Second | sql_server.sql_recompilations_per_sec        | The number of SQL recompiles per second.                                                                                                                                                                                                                                                             |           |                 |     |      |                            |      |      |      |
| Checkpoint Pages Per Second   | sql_server.checkpoint_pages_per_sec          | The number of pages written to disk per second by a checkpoint operation.                                                                                                                                                                                                                            |           |                 |     |      |                            |      |      |      |
| Buffer Cache hit Ratio        | sql_server.buffer_cache_hit_ratio            | The ratio of how many pages are going to memory versus the disk.                                                                                                                                                                                                                                     |           |                 |     |      |                            |      |      |      |
| Page Life Expectancy          | sql_server.page_life_expectancy              | The number of seconds a page is in the buffer pool without references.                                                                                                                                                                                                                               |           |                 |     |      |                            |      |      |      |
| Page Splits Per Second        | sql_server.page_splits_per_sec               | The number of page splits occurring per second.                                                                                                                                                                                                                                                      |           |                 |     |      |                            |      |      |      |
| Windows Event Count           | windows_events.event_count                   | The count of Windows events that have occurred.                                                                                                                                                                                                                                                      | sum       |                 | 0   | none | zero                       | yes  | no   | no   |


## Computed

| Friendly Name                         | Fully Qualified Name (FQN)                                 | Description                                                                                                                                                                                                                                                                | Units   | Min | Max  | BASE | CORR | UTIL |
|---------------------------------------|------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------|-----|------|------|------|------|
| Total Interface Packet Errors         | netuitive.winsrv.network_interface.*.packets_total_errors  | Total network errors.Computation:network_interface.*.packets_outbound_errors +network_interface.*.packets_received_errors                                                                                                                                                  | errors  | 0   | none | yes  | no   | no   |
| Total Interface Packets               | netuitive.winsrv.network_interface.*.packets_total         | Total network packets.Computation:(network_interface.*.packets_received_per_sec +network_interface.*.packets_sent_per_sec) * 300                                                                                                                                           | packets | 0   | none | yes  | no   | no   |
| Interface Packet Error Percent        | netuitive.winsrv.network_interface.*.packets_error_percent | Percentage of packets that had errors.Computation:netuitive.winsrv.network_interface.*.packets_total == 0 ? 0 :(netuitive.winsrv.network_interface.*.packets_total_errors /netuitive.winsrv.network_interface.*.packets_total) * 100                                       | percent | 0   | 100  | yes  | no   | no   |
| Max Network Utilization Percent       | netuitive.winsrv.network_interface.maxutilizationpercent   | The highest utilization percentage across all network interfaces.Computation:data.max(netuitive.winsrv.network_interface.(.*).utilizationpercent)                                                                                                                          | percent | 0   | 100  | yes  | yes  | no   |
| Max Network Error Percent             | netuitive.winsrv.network_interface.maxerrorpercent         | The highest error percentage across all network interfaces.Computation:data.max(netuitive.winsrv.network_interface(.*).utilizationpercent)                                                                                                                                 | percent | 0   | 100  | yes  | no   | no   |
| Memory Utilization Percent            | netuitive.winsrv.memory.utilizationpercent                 | Memory utilization percent.Computation:(attribute[ram] == null || attribute[ram] == 0) ? 0 : ((attribute[ram] –memory.available_bytes) / attribute[ram]) * 100                                                                                                             | percent | 0   | 100  | yes  | yes  | yes  |
| Interface Utilization Percent         | netuitive.winsrv.network_interface.*.utilizationpercent    | Network utilization percent based on bytes per second compared to theavailable bandwidth.Computation:(network_interface.*.current_bandwith == 0) ? 0 :((network_interface.*.bytes_total_per_sec * 8) /network_interface.*.current_bandwidth) * 100                         | percent | 0   | 100  | yes  | no   | no   |
| Memory Unavailable Bytes              | netuitive.winsrv.memory.unavailable_bytes                  | Unavailable bytes of memory.Computation:(attribute[ram bytes] == null || attribute[ram bytes == 0) ?((attribute[ram] == null || attribute[ram] == 0) ? 0 : (attribute[ram] –memory.available_bytes)) : (attribute[ram_bytes] –memory.available_bytes)                      | bytes   | 0   | none | yes  | no   | no   |
| Page File Size                        | netuitive.winsrv.memory.page_file_size                     | Total size of the page file(s).Computation:(memory.committed_bytes / (memory.percent_committed_in_use / 100)) –((attribute[ram bytes] == null || attribute[ram bytes] == 0) ?((attribute[ram] == null || attribute[ram] == 0) ? 0 : attribute[ram]) :attribute[ram_bytes]) | bytes   | 0   | none | yes  | no   | no   |
| Page File Unavailable Bytes           | netuitive.winsrv.memory.page_file_unavailable_bytes        | Unavailable bytes in the page file(s).Computation:netuitive.winsrv.memory.page_file_size * (memory.page_file_percent_used/ 100)                                                                                                                                            | bytes   | 0   | none | yes  | no   | no   |
| Page File Available Bytes             | netuitive.winsrv.memory.page_file_available_bytes          | Available bytes in the page file(s).Computation:netuitive.winsrv.memory.page_file_size –netuitive.winsrv.memory.page_file_unavailable_bytes                                                                                                                                | bytes   | 0   | none | yes  | no   | no   |
| Processor Queue Length Normalized     | netuitive.winsrv.system.processor_queue_length_normalized  | The average processor queue length across all CPUs.Computation:system.processor_queue_length / attribute[‘cpus’].value                                                                                                                                                     | count   | 0   | none | yes  | no   | no   |
| Disk Utilization Percent              | netuitive.winsrv.logical_disk.*.utilizationpercent         | Disk utilization percent based on percentage used for each logical disk.Computation:100 – logical_disk.*.percent_free                                                                                                                                                      | percent | 0   | 100  | yes  | yes  | no   |
| Physical Disk Total Percent Busy Time | netuitive.winsrv.physical_disk._total.percent_busy_time    | 100 – data [‘physical_disk._Total.percent_idle_time’].actual                                                                                                                                                                                                               | percent | 0   | 100  | yes  | no   | yes  |