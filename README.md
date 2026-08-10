# Windows Server 2022 Active Directory Lab

A complete step-by-step guide for deploying a Windows Server 2022 Domain Controller in VMware Workstation and joining a Windows client to the domain.

This lab covers:

- Virtual machine provisioning
- Dual-NIC networking (Internet + isolated internal LAN)
- Active Directory Domain Services (AD DS) installation and forest creation
- DHCP and RRAS (NAT) configuration
- Organizational Units, users, groups, and delegation of control
- Domain join from a Windows client
- Account lifecycle management (expiration, logon hours, password reset)

> **Lab Environment Only**  
> This guide is intended for learning and home-lab use. Do not use the passwords, IP addresses, or configuration shown here in a production environment.

---

## Prerequisites

- VMware Workstation (or VMware Workstation Player)
- Windows Server 2022 ISO
- Windows 10/11 ISO (for the client machine)
- Host machine with at least:
  - 8 GB RAM (16 GB recommended)
  - 100+ GB free disk space
  - Virtualization enabled in BIOS

---

## Lab Topology

| Component              | Details                                      |
|------------------------|----------------------------------------------|
| Domain                 | `ugo.local`                                  |
| Domain Controller      | `DC-01`                                      |
| Internal Network       | `172.16.7.0/24` (VMnet2)                     |
| DC Internal IP         | `172.16.7.1`                                 |
| DHCP Scope             | `172.16.7.100` – `172.16.7.200`              |
| Default Gateway / DNS  | `172.16.7.1`                                 |
| Internet Connectivity  | NAT via second network adapter               |

**Network Adapters on DC-01:**
- **Internet** → NAT (outbound internet access)
- **Internal** → Custom VMnet2 (isolated lab network)

---

## Table of Contents

1. [Create the Windows Server 2022 Virtual Machine](#1-create-the-windows-server-2022-virtual-machine)
2. [Install Windows Server 2022](#2-install-windows-server-2022)
3. [Initial Server Configuration](#3-initial-server-configuration)
4. [Configure Network Adapters](#4-configure-network-adapters)
5. [Install Active Directory Domain Services](#5-install-active-directory-domain-services)
6. [Promote Server to Domain Controller](#6-promote-server-to-domain-controller)
7. [Configure Routing and Remote Access (NAT)](#7-configure-routing-and-remote-access-nat)
8. [Install and Configure DHCP](#8-install-and-configure-dhcp)
9. [Build Active Directory Structure](#9-build-active-directory-structure)
10. [Create the Windows Client Virtual Machine](#10-create-the-windows-client-virtual-machine)
11. [Join the Client to the Domain](#11-join-the-client-to-the-domain)
12. [Verification Commands](#12-verification-commands)
13. [Account Lifecycle Management](#13-account-lifecycle-management)

---

## 1. Create the Windows Server 2022 Virtual Machine

1. Open **VMware Workstation**.
2. Click **Create a New Virtual Machine**.
3. Select **Typical** configuration and click **Next**.
4. Choose **Installer disc image file (iso)** and browse to your Windows Server 2022 ISO.
5. Select the appropriate Windows Server edition when prompted.
6. Set the virtual machine name to `Windows Server 2022` and choose a storage location.
7. Set the disk size to **60 GB** (or higher) and select **Store virtual disk as a single file** or **Split into multiple files** according to your preference.
8. Review the summary (recommended: 2 GB RAM, 2 processors, NAT networking) and click **Finish**.

### Add a Second Network Adapter

1. Select the newly created VM and click **Edit virtual machine settings**.
2. Click **Add** → **Network Adapter** → **Finish**.
3. Select the second network adapter and set it to **Custom: Specific virtual network** → **VMnet2**.
4. Click **OK** to save the settings.

---

## 2. Install Windows Server 2022

1. Power on the virtual machine.
2. Press any key when prompted to boot from the ISO.
3. Select language, time, and keyboard settings → **Next**.
4. Click **Install now**.
5. Enter the product key (or select the evaluation edition).
6. Choose **Windows Server 2022 Standard (Desktop Experience)** (or Datacenter if preferred).
7. Accept the license terms.
8. Select **Custom: Install Microsoft Server Operating System only (advanced)**.
9. Select the virtual disk and click **Next** to begin installation.
10. When prompted, set a strong password for the local **Administrator** account and finish the setup.

After the first reboot, press **Ctrl + Alt + Del** (via the VMware menu) and log in with the Administrator account.

When the **Networks** prompt appears, choose **Yes** to enable network discovery.

---

## 3. Initial Server Configuration

### Rename the Server

1. Press `Win + I` to open **Settings**.
2. Go to **System** → **About**.
3. Click **Rename this PC
