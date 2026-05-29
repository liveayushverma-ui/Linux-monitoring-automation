# Linux Server Monitoring Automation Project

## Project Overview

This project demonstrates a Linux server monitoring setup using Prometheus, Node Exporter and Grafana.

The monitoring server runs Prometheus and Grafana.  
The target Linux server runs Node Exporter.  
Prometheus collects system metrics from Node Exporter, and Grafana visualizes those metrics using dashboards.

## Tools Used

- Linux
- Prometheus
- Node Exporter
- Grafana
- Ansible
- Git
- systemd
- Firewall management

## Architecture

```text
+----------------------------+
| Monitoring Server          |
|                            |
| Prometheus :9090           |
| Grafana    :3000           |
+-------------+--------------+
              |
              | Scrapes metrics
              |
+-------------v--------------+
| Target Linux Server        |
|                            |
| Node Exporter :9100        |
+----------------------------+
