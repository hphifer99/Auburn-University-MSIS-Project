# Privacy-First Local Home Surveillance System  
**MSIS Capstone Project – Hayden Phifer**

This repository contains the final report, architecture documentation, and presentation materials for my Master of Science in Information Systems Management capstone project.

The project designs and implements a privacy-first home surveillance system that eliminates reliance on vendor cloud infrastructure while preserving secure remote monitoring, operational reliability, and full data ownership.

---

## Project Overview

Commercial home camera systems are commonly marketed as safety products, but they rely heavily on third-party cloud platforms that introduce privacy, security, and trust risks. This project addresses that trade-off by building a surveillance system that keeps all video local by design and allows remote access only through a self-managed VPN.

The system enforces a local-only recording model in which video never leaves the home network unless accessed by an authenticated VPN client. Cameras are treated as untrusted devices, isolated from the Internet, and prevented from communicating with external services.

---

## Architecture Summary

- IP camera providing RTSP stream  
- Camera isolated on a dedicated VLAN with outbound Internet access blocked  
- Continuous local recording on a repurposed workstation acting as a recorder  
- Encrypted backups stored on a BitLocker-protected volume  
- Secure remote access provided exclusively through WireGuard VPN  
- No exposed web portals, cloud relays, or public-facing streaming endpoints  

Firewall logging and traffic inspection were used to verify that outbound camera connections were repeatedly attempted and successfully blocked, confirming enforcement of the local-only security posture.

---

## Key Features

- Local-only continuous video recording  
- Network segmentation and strict firewall enforcement  
- Encrypted backups at rest  
- Secure remote viewing via self-managed WireGuard VPN  
- Automatic recovery from stream interruptions and recording failures  
- No vendor cloud storage or third-party access  

---

## Technologies and Tools

**Networking and Security**
- UniFi Dream Router 7  
- VLAN segmentation and firewall policy enforcement  
- WireGuard VPN  

**Recording and Storage**
- Reolink E1 Pro IP camera (RTSP)  
- OBS Studio for continuous recording  
- Cobian Reflector for automated encrypted backups  
- BitLocker encrypted storage  

**Platform**
- Windows 10 IoT Enterprise  
- Repurposed Alienware X51 R3 workstation  

---

## Skills Demonstrated

- Security-focused network architecture  
- VLAN design and firewall policy enforcement  
- VPN configuration and secure remote access  
- Encrypted storage and backup strategy design  
- Long-running application tuning and failure recovery  
- Privacy-preserving system design  

---

## Disclaimer

This repository contains academic project documentation only. It does not provide a production-ready surveillance product or installation scripts. Network addresses, credentials, and identifying details have been removed or anonymized.

---

## Author

Hayden Phifer  
Master of Science in Information Systems Management, Graduate Certificate Cybersecurity
Project focus areas: cybersecurity, network security, privacy-preserving systems
