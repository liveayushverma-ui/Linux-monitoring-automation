# Grafana Dashboard Queries

## CPU Usage

```promql
100 - (avg by(instance) (rate(node_cpu_seconds_total{mode="idle"}[5m])) * 100)


##### Memory usage
(1 - (node_memory_MemAvailable_bytes / node_memory_MemTotal_bytes)) * 100


### Disk Usage
100 - ((node_filesystem_avail_bytes{mountpoint="/"} * 100) / node_filesystem_size_bytes{mountpoint="/"})


##### server Uptime#######

node_time_seconds - node_boot_time_seconds


###  Network Receive Traffic ######

rate(node_network_receive_bytes_total[5m])

#### Network Transmit Traffic#######

sum(rate(node_network_transmit_bytes_total{device!~"lo"}[5m])) by (instance)
