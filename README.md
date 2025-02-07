# 🛠️ Self-Hosted VPN & Media Stack

This is a **self-hosted media and torrent stack** designed to offer secure access to various services and applications using a **NordVPN** container with a **VPN network** setup. It integrates a variety of tools such as **qBittorrent**, **Overseerr**, **Tautulli**, **Jackett**, **Radarr**, **Sonarr**, and **Flaresolverr**.

## 🚀 Getting Started

### Requirements:
- **Docker** and **Docker Compose** installed.
- A **NordVPN** account with an **API token**.
- Basic knowledge of **Docker** containers and networking.

### Configuration:
1. **NordVPN**: The stack is configured with NordVPN for secure access to all services. You'll need a valid **NordVPN token** and specify the desired **server location** and **connection technology** (NordLynx).
2. **Service Ports**: Each service in the stack exposes its own ports for communication and access.
3. **Volumes**: Volumes are mapped to persistent storage on the host to preserve configurations and data.

### Services in the Stack:
- **VPN**: 
  - Provides a secure NordVPN connection using NordLynx technology.
  - Configured to expose necessary ports for other services.
  - Healthcheck to monitor connectivity.

- **qBittorrent (ThrowTorrent)**:
  - Web UI access through port `8090` for managing torrents.
  - Runs behind the VPN network for secure downloading.

- **Overseerr**:
  - A media request system for managing media requests and interacting with Radarr and Sonarr.

- **Tautulli**:
  - A monitoring and analytics tool for Plex or Jellyfin media servers.

- **Jackett**:
  - A proxy server for accessing **torrent indexers** with support for various trackers.

- **Radarr**:
  - Automates the process of downloading movies through torrents.

- **Sonarr**:
  - Automates TV show downloads using torrents.

- **Flaresolverr**:
  - A CAPTCHA solving service for use with various torrent providers or media indexers.

## 📝 Environment Variables

For each service, you'll need to modify the relevant **environment variables** to meet your needs.

- **VPN Container**:
  - `TOKEN=REDACTED`: Replace with your NordVPN API token.
  - `CONNECT=United_States`: Replace with the server you want to connect to.
  - `TECHNOLOGY=NordLynx`: Choose between **NordLynx** or **OpenVPN**.
  - `NETWORK=10.27.27.0/24`: Network range to allow access to. "Replace it with your own network range"

- **Other Services**:
  - Most services use `PUID`, `PGID`, and `TZ` environment variables for user permissions and timezone configuration.

## 🛠️ How to Use:
1. Clone the repository to your local machine or server.
2. Update the `TOKEN` environment variable with your NordVPN token.
3. Customize the port mapping and other environment variables as needed.
4. Run `docker-compose up -d` to start the containers.

## 📄 Ports:
- `8090`: qBittorrent Web UI
- `5055`: Overseerr
- `8181`: Tautulli
- `9117`: Jackett
- `8989`: Sonarr
- `7878`: Radarr
- `8191`: Flaresolverr

## 🔒 Security Considerations:
- **VPN Usage**: All services are routed through the VPN container, ensuring privacy and security.
- **Port Exposure**: Only necessary ports are exposed. Adjust firewall rules to secure further.
- **Sensitive Data**: Ensure the NordVPN token is kept secure and not publicly exposed.

## ⚖️ Legal Disclaimer:
This setup is intended for personal use and should only be used for downloading and streaming legally acquired content. By using these services, you agree to comply with all applicable laws and regulations. The repository creator is not responsible for any illegal activities or misuse of the system.

