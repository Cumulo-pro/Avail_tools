# Avail Metrics and Grafana Dashboard
![grafana-01](https://github.com/Cumulo-pro/Avail-tools/assets/2853158/f5130960-cb79-4ea0-ace7-874bef6ae7c2)

This repository contains detailed information about Avail metrics and the associated Grafana dashboard.

## Resources

Explore the key resources available for setting up and managing Avail metrics and dashboards:

### Detailed Metrics Guide  
Get a comprehensive explanation of all the metrics available for monitoring Avail nodes.  
[![Metrics](https://img.shields.io/badge/Metrics-View%20Metrics-blue?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Cumulo-pro/Avail_tools/blob/main/avail-metrics/metrics.md)  

### Grafana Dashboard  
Download the latest version of the Grafana dashboard for real-time visualization of your Avail node metrics.  
[![Grafana Dashboard](https://img.shields.io/badge/Grafana%20Dashboard-Download-blue?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Cumulo-pro/Avail_tools/blob/main/avail-metrics/Avail%20Metrics%20Cumulo%20v3-1732449812844.json)  

### Alerts Configuration Guide  
Learn how to configure Prometheus and Alertmanager to receive critical alerts and monitor your node effectively.  
[![Avail Alerts Guide](https://img.shields.io/badge/Avail%20Alerts-View%20Guide-blue?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Cumulo-pro/Avail_tools/blob/main/avail-metrics/AVAIL_ALERTS.md)  

### Prometheus alert rules
Create or update the Prometheus alert rules file at `/etc/prometheus/rules/avail_alerts.yml` with the following content:
[![Avail Alerts](https://img.shields.io/badge/Avail_Alerts-View%20File-blue?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Cumulo-pro/Avail_tools/blob/main/avail-metrics/alerts_avail.yml)

---



## First steps 

Before you start, make sure you have port 9615 open.  

### Modify the availd.service file  
/etc/systemd/system/availd.service  

```bash
ExecStart=/home/arixScum9/avail/avail-node -d /home/arixScum9/avail/avail/node-data --chain turing --name Cumulo --validator --prometheus-port 9615 --prometheus-external
```

Restart node:  
```bash
sudo systemctl daemon-reload
sudo systemctl restart availd.service
sudo journalctl -f -u availd.service
```
![image](https://github.com/user-attachments/assets/ca1c642a-501b-42ff-84e7-2754ceb46235)

Check prometheus:  
Open a browser and use the url:9615

Or check it on your server:  
```bash
curl http://localhost:9615/metrics
```

### Configure Prometheus  
Log in to your Prometheus server and edit the configuration file:  
/etc/prometheus/prometheus.yml
```bash
- job_name: avail_node
    scrape_interval: 5s
    static_configs:
      - targets: ['your_ip:9615']
```
Restart Prometheus:  
```bash
sudo systemctl restart prometheus
sudo journalctl -u prometheus -f --no-hostname -o cat
```

## Avail Metrics

Avail metrics provide essential information for monitoring and evaluating the performance and status of the Avail network. These metrics cover a wide range of aspects, from block height to total bandwidth usage.

For a complete description of the available metrics, check out the metrics document below.

[![Metrics](https://img.shields.io/badge/Metrics-View%20Metrics-blue?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Cumulo-pro/Avail_tools/blob/main/avail_metrics/metrics.md)

## Grafana Dashboard

The Grafana dashboard for Avail metrics provides an interactive, real-time visualization of all relevant data. This dashboard facilitates continuous monitoring of the network's status and quick identification of any potential issues.

![image](https://github.com/user-attachments/assets/4334c292-d8af-4bb2-b296-65c57f9e032c)


You can download the Grafana Ddashboard V3 from the link below:

[![Grafana Dashboard](https://img.shields.io/badge/Grafana%20Dashboard-Download-blue?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Cumulo-pro/Avail_tools/blob/main/avail_metrics/Avail%20Metrics%20Cumulo%20v3-1732449812844.json)

---

# Configuring Alerts for Avail Nodes

This guide walks you through the process of setting up alerts for Avail nodes using Prometheus and Alertmanager. It ensures real-time monitoring and notification of node performance, synchronization, and connectivity issues. Follow the steps below to configure and test the alerting system.

[![Avail Alerts Guide](https://img.shields.io/badge/Avail%20Alerts-View%20Guide-blue?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Cumulo-pro/Avail_tools/blob/main/avail-metrics/AVAIL_ALERTS.md)
