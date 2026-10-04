# Braiins Manager Linux Deployment & Network Discovery Lab

## Project Overview

This project documents my hands-on setup and troubleshooting of a Linux-based Braiins Manager Agent used for discovering and managing Bitcoin mining hardware on a local network.

I used an older HP ProBook running Linux Mint as the dedicated management computer.

## What I Did

- Installed Braiins Manager Agent on Linux Mint using a `.deb` package
- Configured the Agent ID and authentication
- Used `systemctl` to verify the Braiins service was running
- Used `journalctl` to inspect service logs and troubleshoot problems
- Checked Linux network interfaces and routing
- Identified Ethernet and Wi-Fi operating simultaneously on the same subnet
- Simplified the system to a single Ethernet connection
- Scanned the local `192.168.40.0/24` network for mining hardware
- Successfully completed a full 256-address network scan

## Troubleshooting

The initial network scan remained stuck at 0/256 even though the Braiins Manager Agent was running and communicating with the management platform.

I checked the Linux routing table and discovered that both Ethernet and Wi-Fi were active on the same network. Ethernet had the preferred route, but I disabled Wi-Fi to eliminate the additional network path.

After switching to Ethernet only and running a new scan, Braiins successfully completed the entire 256-address scan.

No mining devices were expected to be discovered because this was performed on a test network without physical ASIC miners.

## Skills Practiced

- Linux administration
- Network troubleshooting
- IPv4 subnetting
- Routing diagnostics
- Debian package installation
- Linux service management
- Log analysis
- Network device discovery
- Bitcoin mining infrastructure management
