# Lab 09 — Grafana Dashboard with Prometheus

## Objective
Collect Linux server metrics with Node Exporter and Prometheus, connect Grafana and build an operational dashboard.

## Monitoring flow

`Linux host → Node Exporter :9100 → Prometheus :9090 → Grafana :3000 → Dashboard and alerts`

## Docker Compose example

```yaml
services:
  node-exporter:
    image: prom/node-exporter
    ports: ["9100:9100"]

  prometheus:
    image: prom/prometheus
    ports: ["9090:9090"]
    volumes:
      - ./prometheus.yml:/etc/prometheus/prometheus.yml:ro

  grafana:
    image: grafana/grafana
    ports: ["3000:3000"]
    environment:
      GF_SECURITY_ADMIN_USER: admin
      GF_SECURITY_ADMIN_PASSWORD: ChangeThisLabPassword
```

## Prometheus configuration

```yaml
global:
  scrape_interval: 15s

scrape_configs:
  - job_name: node
    static_configs:
      - targets: ["node-exporter:9100"]
```

## Build the dashboard

1. Confirm the Prometheus target is **UP**.
2. Add Prometheus as a Grafana data source.
3. Select **Save & test**.
4. Build panels for CPU, memory, disk and network or uptime.
5. Set correct units, legends, titles, time range and refresh interval.
6. Save the dashboard and export its JSON.

## Useful PromQL

```promql
100 - avg by(instance)(rate(node_cpu_seconds_total{mode="idle"}[5m])) * 100
(1 - node_memory_MemAvailable_bytes / node_memory_MemTotal_bytes) * 100
(1 - node_filesystem_avail_bytes{fstype!~"tmpfs|overlay"} / node_filesystem_size_bytes{fstype!~"tmpfs|overlay"}) * 100
node_load1
rate(node_network_receive_bytes_total{device!="lo"}[5m])
time() - node_boot_time_seconds
```

## Troubleshooting “No data”

Work backwards:

1. Check panel query, labels and time range.
2. Run the query in Grafana Explore.
3. Query Prometheus directly.
4. Check Prometheus target status.
5. Test `curl http://host:9100/metrics`.
6. Verify network reachability and container addressing.

## Interview answer

> I work backwards from Grafana to Prometheus and then to the exporter. This isolates whether the failure is in the visualisation, query, data source, scrape path, network or exporter.

---
[Home](../README.md) • [GitHub](https://github.com/toannguyenitoz) • [LinkedIn](https://www.linkedin.com/in/toan-nguyen-it-oz/)