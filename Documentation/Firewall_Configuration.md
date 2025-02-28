# pfSense Firewall Setup

## Creating a Virtual Machine in VMware Workstation
1. Open VMware Workstation and go to **File > New Virtual Machine**.
2. Choose **Custom (advanced)**.
3. Select the appropriate **Virtual Machine Hardware Compatibility**.
4. Choose **I will install the operating system later**.
5. Select **Other** as the Guest OS and **FreeBSD 11 64-bit** as the version.
6. Enter a **VM Name** and select a **Location**.
7. Assign **1 CPU** and **1 core per processor**.
8. Set **256MB RAM**.
9. Choose **Bridged** or **NAT** for network configuration.
10. Use **LSI Logic SCSI Controller**.
11. Select **IDE Virtual Disk Type**.
12. Create a **New Virtual Disk**, set **5GB size**, and store as a single file.
13. Finalize the setup and click **Finish**.

### VM Hardware Adjustments
- Remove **USB Controller** and **Sound Card**.
- Attach the **pfSense ISO** file to the CD/DVD drive.
- Disable legacy hardware:
  - Power On VM to Firmware
  - Go to **Advanced > I/O Device Configuration**
  - Disable **Serial Port A, Serial Port B, Parallel Port, and Floppy Disk Controller**
  - Save and Exit

## Installing pfSense
1. Boot the VM and start the **pfSense Installer**.
2. Accept the copyright notice and choose **Install**.
3. Select the correct **keyboard layout**.
4. Choose **Auto (UFS) partitioning**.
5. Complete the installation and **reboot**.

## Initial Configuration
1. At the setup prompt, select **No** for VLAN setup.
2. Assign **WAN Interface: em0**.
3. Leave **LAN Interface** blank (press Enter).
4. Confirm configuration and proceed.
5. Verify internet connectivity using **option 7 (Ping Test)**.

## Configuring LAN Interface
1. Halt the system and power off the VM.
2. Edit VM settings:
   - Remove **CD/DVD drive**.
   - Add an **Ethernet Adapter** for LAN.
3. Power on the VM and assign interfaces:
   - **WAN: em0**
   - **LAN: em1**
4. Assign LAN IP Address:
   - Enter **IPv4 Address** and **Subnet Mask**.
   - Skip IPv6 configuration.
   - Choose **No** for DHCP server (if using AD DHCP).
   - Enable **HTTP for WebConfigurator**.

## Final Configuration
1. Access the **Web Console** using the LAN IP.
2. Log in with default credentials (**admin / pfsense**).
3. Configure System Settings:
   - Set **Hostname, Domain, DNS, Timezone**.
   - Save changes.
4. Install VMware Tools:
   - Go to **System > Package Manager**.
   - Install **Open-VM-Tools**.
5. Update pfSense:
   - Go to **System > Update** and apply updates.
6. Change **Admin Password**.
7. Reboot pfSense.

---
This setup ensures pfSense is fully operational as a firewall/router for your home lab.


