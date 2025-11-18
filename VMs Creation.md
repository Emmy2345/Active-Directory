# 💻 Setting Up Windows Client and Server Virtual Machines on VMware Workstation Pro

This guide outlines the steps to create a **Windows Client Machine** and a **Windows Server Machine** using **VMware Workstation Pro**.

---

## 📥 Prerequisite Downloads

Before starting, you'll need the ISO images for your desired operating systems.

* **Windows Server ISO Image:** (https://www.microsoft.com/en-us/evalcenter/download-windows-server-2022)
* **Windows Client Machine ISO Image (e.g., Windows 11):** (https://www.microsoft.com/en-us/software-download/windows11)

---

## 🖥️ 1. Create Windows Client Machine (e.g., Windows 11)

This section details the steps for creating a client virtual machine, including the required security features like TPM and encryption.

### Virtual Machine Creation Steps

| Step | Action |
| :--- | :--- |
| **1** | On the **Home** tab in VMware Workstation Pro, click **"Create a New Virtual Machine"**. |
| **2** | Select **"Typical (recommended)"** option. Click **"Next"**. |
| **3** | Select **"Installer disc image file (iso)"** option. **Browse** to the download location where you saved the Windows ISO Image file. Click **"Next"**. |
| **4** | **Name** the Virtual Machine. Choose the **location** where you want the VM to be saved at. |
| **5** | In the **Specify Disk Capacity** window - Choose **60GB** or the recommended amount. Select **"Store virtual disk as a single file"**. Click **"Next"**. |
| **6** | Click **"Customize Hardware"**. |

### Hardware Customization (Step 7)

* **Recommended Settings:**
    * **Memory:** **16GB**
    * **Processors:** **4**
    * **Network Adapter:** **NAT**

Click **Finish**.

### Security Configuration

After creation, go to **Edit settings** for the new VM:

* Navigate to the **Options** tab.
* Enable **Encryption**. Set a strong password.
* Add a **Trusted Platform Module (TPM)** or **Trusted Module Platform**.

### Operating System Installation

| Step | Action |
| :--- | :--- |
| **8** | Once the VM is started, follow the installer prompts: Select **Windows 11 Pro** (or your client version) $\rightarrow$ **Custom** $\rightarrow$ Select your virtual **Drive** $\rightarrow$ **Install**. |
| **9** | **Set the Administrator Password** when prompted during the final setup. |

---

## ⚙️ 2. Create Windows Server Machine (e.g., Server 2022)

This section details the steps for creating the server virtual machine.

### Virtual Machine Creation Steps

| Step | Action |
| :--- | :--- |
| **1** | On the **Home** tab in VMware Workstation Pro, click **"Create a New Virtual Machine"**. |
| **2** | Select **"Typical (recommended)"** option. Click **"Next"**. |
| **3** | Select **"I will install the operating system later"** option. Click **"Next"**. |
| **4** | Select **"Microsoft Windows"**. Select the desired version. In this case, **"Windows Server 2022"**. |
| **5** | **Name** the Virtual Machine. Choose the **location** where you want the VM to be saved at. |
| **6** | In the **Specify Disk Capacity** window - Choose **60GB** or the recommended amount. Select **"Store virtual disk as a single file"**. Click **"Next"**. |
| **7** | Click **"Customize Hardware"**. |

### Hardware and ISO Configuration

| Step | Action |
| :--- | :--- |
| **8** | **Recommended Settings:** **Memory - 16GB**. **Processors - 4**. **Network Adapter - NAT**. |
| **9** | Select **"New CD/DVD (SATA)"** tab and **Set the ISO Image file location** here. |
| **10** | Click **Close** on the hardware window, then **Finish** on the wizard. |

---

## 🚀 3. Start and Install Windows Server Machine

Since the ISO was attached after creation, we need to power on the VM to the firmware to ensure it boots from the installation media.

### Installation Steps

| Action |
| :--- |
| In the VMware **Library** tab, **Right-Click** your Windows Server Machine. |
| Select **"Power"** $\rightarrow$ Select **"Power On to Firmware"**. |
| Use the arrow keys on the keyboard to navigate to **"EFI VMware Virtual SATA CDROM Drive (1.0)"**. |
| Click **"Enter"** on the keyboard twice. |
| Follow the installer prompts: Choose **language** $\rightarrow$ **Next** $\rightarrow$ **Install**. |
| Select **"I don't have a product key"**. |
| Select **"Windows Server 2022 Datacenter Evaluation (Desktop Experience)"** $\rightarrow$ **Next**. |
| **Accept Terms** $\rightarrow$ **Custom** $\rightarrow$ **Select Drive** to install the OS. |
