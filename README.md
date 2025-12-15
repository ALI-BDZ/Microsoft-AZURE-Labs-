# Azure Lab: Introduction to Microsoft Azure

## Objective
Learn to use basic Azure services by creating a **Virtual Machine (VM)**, configuring a network, and setting up storage.

---

## Prerequisites
- An active **Microsoft Azure account** (free tier works).
- Access to the [Azure Portal](https://portal.azure.com).

---

## Steps

### 1. Create an Azure Account
- Sign up for a free account at [Azure for Students](https://azure.microsoft.com/fr-fr/free/students).
- Log in to the [Azure Portal](https://portal.azure.com).

### 2. Create a Virtual Machine (VM)
- Search for **Virtual Machines** in the Azure Portal.
- Click **Create** and configure:
  - **Subscription**: Select your free account.
  - **Resource Group**: Create a new group (e.g., `RG-TPVM`).
  - **VM Name**: Name your VM (e.g., `VM-TP`).
  - **Region**: Choose a location (e.g., `France Central`).
  - **Image**: Select `Ubuntu` (Linux).
  - **Size**: Choose `B1s` (small, free tier).
  - **Admin Account**: Set a username and password for SSH access.
- Click **Review + Create** and then **Create**.

### 3. Connect to the VM
- Go to **Virtual Machines** and select your VM.
- Click **Connect** and use SSH with the credentials you created.

### 4. Configure Storage
- Create an additional disk in **Disks** and attach it to your VM.
- Connect to the VM via SSH and:
  - Partition the disk: `sudo fdisk /dev/sdc`.
  - Format the disk: `sudo mkfs.ext4 /dev/sdc1`.
  - Mount the disk: `sudo mount /dev/sdc1 /mnt/data`.
  - Make the mount permanent by editing `/etc/fstab`.

### 5. Configure Network Security
- Go to **Networking** in your VM settings.
- Add a rule to allow **HTTP (port 80)** or **HTTPS (port 443)** traffic.

### 6. Deploy a Simple Web App (Optional)
- Install Apache: `sudo apt update && sudo apt install apache2`.
- Start Apache: `sudo systemctl start apache2`.
- Access the default Apache page via your VM’s public IP.

### 7. Clean Up
- Delete the **Resource Group** to avoid unnecessary charges.

---

## Key Concepts
- **Resource Group**: A container for Azure resources (e.g., VMs, disks).
- **Network Security Group (NSG)**: Controls inbound/outbound traffic to VMs.
- **SSD vs. HDD**: SSDs are faster but more expensive; HDDs are cheaper but slower.

---

## Questions to Consider
- Why are **Resource Groups** important in Azure?
- How do **NSGs** enhance VM security?
- What are the differences between **SSD** and **HDD** storage in Azure?
