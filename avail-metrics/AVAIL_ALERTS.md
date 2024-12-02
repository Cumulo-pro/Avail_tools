# Configuring Alerts for Avail   

This guide outlines the steps to configure alerts for the Avail node using Prometheus and Alertmanager. It assumes you have already set up Prometheus and Grafana.

---

## Prerequisites

- **Prometheus** is installed and running.
- **Alertmanager** is installed and running.
- A basic understanding of YAML configuration files.

---

## Step 1: Configure Prometheus Rules for Avail Alerts

Create or update the Prometheus alert rules file at `/etc/prometheus/rules/avail_alerts.yml` with the following content:

[![Avail Alerts](https://img.shields.io/badge/Avail_Alerts-View%20File-blue?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Cumulo-pro/Avail_tools/blob/main/avail-metrics/alerts_avail.yml)

Download or reference the file and save it to `/etc/prometheus/rules/avail_alerts.yml`. Validate the configuration using:
```bash
promtool check rules /etc/prometheus/rules/avail_alerts.yml
```

## Step 2: Configure Alertmanager

Use the Alertmanager configuration file provided in the following link:

[![Alertmanager Config](https://img.shields.io/badge/Alertmanager_Config-View%20File-blue?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Cumulo-pro/Avail_tools/blob/main/avail-metrics/alertmanager1.yml)

Save the file to `/etc/alertmanager/alertmanager.yml`.

### Replace the following:
- **BOT_TOKEN_1** and **BOT_TOKEN_2** with your respective Telegram bot tokens.
- **CHAT_ID_1** and **CHAT_ID_2** with your Telegram chat IDs.

---

## Step 3: Reload Prometheus and Alertmanager

Reload Prometheus to apply the alert rules:
```bash
sudo systemctl reload prometheus
sudo systemctl restart alertmanager
sudo systemctl status alertmanager
```

## Step 4: Verify the loading of rules in Prometheus  

Open the Prometheus web interface (usually at http://ip:9090/).  
Navigate to the “Status” > “Rules” section. You should see your alerts listed here, indicating that Prometheus has loaded the rules file correctly.  

![image](https://github.com/user-attachments/assets/97498c1b-a37d-4e8c-bc69-357d37bd5bb3)

## Final Verification  

If everything is set up correctly, you should start receiving alert messages in your designated Telegram bot. These alerts will provide real-time notifications of node status and performance issues, helping you to monitor and maintain your Avail node effectively.  

![image](https://github.com/user-attachments/assets/9fc8614e-ed0e-4c5d-ac28-d1ac62416903)

For additional details on Avail metrics and alert configurations, refer to the Prometheus Alerting Documentation.  

