<div align="center">

# 🔐 Cybersecurity Lab Environment Setup

**Building a virtual lab for cybersecurity and ethical hacking practice**

</div>

<p align="center">
  <img src="https://img.shields.io/badge/Project-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Hypervisor-VirtualBox-0070C0?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Security%20OS-Kali%20Linux-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Network-NAT%20Network-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Program-Networkwalks-C00000?style=flat-square&labelColor=000000" />
</p>

---

## 📌 Project Overview

This project documents the setup of a virtual cybersecurity lab using **Oracle VirtualBox** and **Kali Linux** as part of the Networkwalks Week 1 project (WK1-PM1).

The aim is to prepare a controlled environment for learning networking and practicing authorized cybersecurity testing. The lab can be expanded with additional virtual machines for future exercises.

## 🎯 Objectives

- Install and use 7-Zip to extract the Kali virtual-machine package.
- Install VirtualBox and import Kali Linux.
- Create a NAT Network using the `10.0.0.0/24` subnet.
- Configure the Kali virtual machine's network adapter.
- Set and verify the Kali IP address required by the task.
- Check network and internet connectivity.
- Enable clipboard, drag-and-drop, and a shared folder as required.
- Create a clean virtual-machine snapshot.
- Record the setup with screenshots.

## 🏗️ Lab Architecture

<!-- Add your own architecture image here if you create one. -->
<!-- Example: ![Lab architecture](screenshots/lab-architecture.png) -->

Kali Linux runs as a virtual machine in VirtualBox and connects to the `NatNetwork` NAT Network. Additional lab virtual machines can be added to this network for future authorized practice.

## ⚙️ Lab Configuration

| Component | Configuration |
|---|---|
| Host OS | Windows |
| Host RAM | 8 GB |
| Processor | Intel Core i5-4210U |
| Hypervisor | Oracle VirtualBox |
| Security OS | Kali Linux (downloaded virtual-machine image) |
| Kali RAM | 2048 MB (initial configuration) |
| Virtual Network | NAT Network |
| Network Name | `NatNetwork` |
| Network Prefix | `10.0.0.0/24` |
| Required Kali IP | `10.0.0.2/24` |
| Default Gateway | `10.0.0.1` (verify against your VirtualBox NAT Network settings) |
| DNS | `8.8.8.8` (if configured) |

> **Important:** Update this table to match your final working settings. Do not claim a setting or test succeeded unless you verified it on your own machine.

## 🪜 Lab Setup Procedure

### Step 1: Install 7-Zip

Installed 7-Zip to extract the downloaded Kali Linux virtual-machine archive.

### Step 2: Install VirtualBox

Installed Oracle VirtualBox to run the Kali Linux virtual machine.

### Step 3: Create the NAT Network

Created a VirtualBox NAT Network named `NatNetwork` with the `10.0.0.0/24` network prefix.

**Screenshot:** Add your own VirtualBox NAT Network settings screenshot below.

<!-- ![NAT Network settings](screenshots/2-nat-network-settings.png) -->

### Step 4: Import Kali Linux

Downloaded the Kali Linux VirtualBox image from the official Kali Linux website, extracted the archive, and added the `.vbox` machine to VirtualBox.

The VM's network adapter was connected to `NatNetwork`.

**Screenshot:** Add your own Kali Linux VM screenshot below.

<!-- ![Kali Linux VM](screenshots/3-kali-linux-vm.png) -->

### Step 5: Configure and Verify Network Settings

The task requires Kali Linux to use `10.0.0.2/24` and have internet access. Verify the actual address with:

```bash
ip addr
```

Check internet connectivity with:

```bash
ping -c 4 google.com
```

**Screenshot:** Add a terminal screenshot showing your actual `ip addr` output and another showing the successful connectivity test.

<!-- ![Kali network settings](screenshots/4-kali-network-settings.png) -->

### Step 6: Enable VM Integration Features

Check the VirtualBox VM settings and enable clipboard sharing and drag-and-drop as required by the task. Configure the host shared folder so it is accessible from Kali at `/downloads`, following the task instructions.

**Screenshot:** Add your own settings screenshot if available.

### Step 7: Create a Clean VM Snapshot

After confirming the final network setup, take a snapshot in VirtualBox. Suggested snapshot name:

`Clean Kali - Network Setup`

**Screenshot:** Add your own snapshot screenshot below.

<!-- ![VM snapshot](screenshots/5-vm-snapshot.png) -->

## 🔎 Verification Checklist

| Check | How to verify | Status |
|---|---|---|
| Kali VM starts | Start the VM in VirtualBox | Complete |
| NAT Network exists | VirtualBox network settings | Complete |
| Kali IP is `10.0.0.2/24` | Run `ip addr` | Verify before submission |
| Internet works | Run `ping -c 4 google.com` | Internet reported working; keep a screenshot |
| Clipboard and drag-and-drop | VirtualBox VM settings | Verify |
| Shared folder at `/downloads` | VirtualBox shared folders / Kali | Verify |
| Clean snapshot created | VirtualBox → Snapshots | To do / verify |

## 🐞 Problems Encountered & Solutions

### Problem: VirtualBox reported that VT-x was disabled

When the virtual machine first started, VirtualBox displayed an error indicating that Intel hardware virtualization was disabled.

**Solution:**
1. Restarted the computer.
2. Entered the HP BIOS/UEFI settings.
3. Enabled Intel Virtualization Technology (VT-x).
4. Saved the settings and restarted.
5. Started the Kali virtual machine again.

### Network troubleshooting

If internet connectivity stops working after changing network settings, first check the VirtualBox NAT Network and Kali connection configuration. Verify the actual network connection name before running NetworkManager commands. The appropriate fix can depend on the VirtualBox and Kali versions.

## 💡 What I Learned

- How a virtual machine runs inside a hypervisor.
- How to create a NAT Network in VirtualBox.
- How to check IPv4 addresses and basic network connectivity in Kali Linux.
- Why a clean VM snapshot is useful before future experiments.
- Why documenting the setup and troubleshooting steps matters in cybersecurity work.

## 🔐 Security and Ethical Use

This lab is for educational use and authorized security testing only. Only test systems that you own or have explicit permission to assess.

## 🔗 Tools and Resources

- [7-Zip](https://www.7-zip.org/)
- [Oracle VirtualBox Downloads](https://www.virtualbox.org/wiki/Downloads)
- [Official Kali Linux Downloads](https://www.kali.org/get-kali/)
- [Networkwalks](https://networkwalks.com/)

## 👤 Author

**Aashutosh Pandey**  
BTech Student | Cybersecurity Learner

## 📌 Project Information

- **Program:** Networkwalks Cybersecurity Internship
- **Week:** 01
- **Task ID:** WK1-PM1
- **Project:** Cybersecurity Lab Setup with VirtualBox and Kali Linux
