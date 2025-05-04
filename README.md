# 🔐 FortiGate Firewall Configuration Project

This project documents the configuration, deployment, and testing of a FortiGate Next-Generation Firewall (NGFW) to secure and manage enterprise network traffic. It includes sample configuration scripts, topology diagrams, and step-by-step setup for key firewall features.

## 📌 Project Goals

- Configure FortiGate as a perimeter firewall and internal segmentation device.
- Implement security policies for traffic filtering.
- Enable VPNs (IPSec and SSL) for remote access.
- Set up UTM features (IPS, antivirus, web filtering).
- Enable logging and reporting using FortiAnalyzer or syslog.

## 🧰 Tools and Devices

- FortiGate 60F (or VM02 in lab environment)
- FortiOS v7.x
- FortiAnalyzer (optional)
- Client PC(s) and Test Server(s)
- Virtual Lab (e.g., GNS3/VMware/VirtualBox)

## 🔧 Configuration Steps

### 1. Initial Setup

- Connect to FortiGate via GUI (`https://192.168.1.99`) or CLI via console.
- Assign IPs to internal and WAN interfaces:
  ```bash
  config system interface
      edit "wan1"
          set ip 192.0.2.2/24
          set allowaccess ping https ssh
      next
      edit "internal"
          set ip 192.168.1.1/24
          set allowaccess ping https ssh
      next
  end
