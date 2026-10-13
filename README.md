# HomeLab — Private Cloud & Security Lab

A self-hosted infrastructure and cybersecurity lab built to explore virtualization, containerization, network connectivity, security monitoring, and infrastructure troubleshooting.

## Overview

This project documents the design, deployment, and maintenance of a personal lab environment using local virtualization and open-source technologies.

The goal is to develop practical skills in infrastructure administration, networking, security monitoring, and remote access while documenting real-world troubleshooting scenarios.

## Technologies

- **Proxmox VE** — Virtualization and virtual machine management
- **Ubuntu Server** — Linux server administration
- **Docker & Docker Compose** — Containerized service deployment
- **Wazuh** — Security monitoring and SIEM/XDR capabilities
- **Tailscale** — Secure remote connectivity and subnet routing
- **Networking** — IP addressing, routing, port publishing, and connectivity troubleshooting

## Lab Architecture

The lab runs on local infrastructure and uses virtual machines to separate services and network roles.

- **Proxmox host:** Manages the virtualized environment.
- **Wazuh VM:** Runs the Wazuh manager, indexer, and dashboard using Docker Compose.
- **VPN gateway VM:** Provides remote access to selected private network resources through Tailscale.
- **Additional Linux VM:** Used to explore service deployment and infrastructure administration.

*Architecture diagrams and sanitized configuration examples will be added as the documentation evolves.*

## Key Learning Areas

- Deploying and managing virtual machines.
- Running multi-container applications with Docker Compose.
- Configuring security monitoring services.
- Understanding private network routing and remote access.
- Troubleshooting IP address changes and container port bindings.
- Documenting infrastructure changes and recovery procedures.
- Applying security best practices when handling configuration and credentials.

## Security Approach

This repository is intended for documentation and sanitized examples.

- No production credentials, private keys, or access tokens should be committed.
- Sensitive configuration values must be replaced with placeholders.
- Network diagrams and screenshots should be reviewed before publication.
- Remote access should be restricted to authorized devices and users.

## Project Status

**In progress.**

The lab is being developed iteratively, with configuration notes, architecture documentation, and troubleshooting guides added as components are validated.

## Disclaimer

This is a personal learning environment, not a production cloud platform. The project demonstrates hands-on experimentation with infrastructure and cybersecurity technologies.

## Author

Personal homelab project focused on infrastructure, networking, and cybersecurity.
