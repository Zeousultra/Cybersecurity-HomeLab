# Active Directory Setup Guide

## Overview
This document details the process of setting up an Active Directory (AD) environment using **Windows Server 2019** and connecting a **Windows 10** client as a domain user. The setup ensures centralized management of users, groups, and policies within a domain network.

## Prerequisites
- **VMware Workstation 15 Player** installed and configured.
- **Windows Server 2019** installed on a virtual machine.
- **Windows 10 Pro** installed on another virtual machine.
- Static IP assigned to Windows Server.

## Step 1: Configure Static IP Address
1. Open **Network and Sharing Center** on **Windows Server 2019**.
2. Navigate to **Change adapter settings** > **Ethernet Properties**.
3. Set a **static IP address**, **subnet mask**, and **DNS (pointing to itself)**.

## Step 2: Install Active Directory Domain Services (AD DS)
1. Open **Server Manager** and click on **Manage** > **Add Roles and Features**.
2. Choose **Role-based or feature-based installation**.
3. Select **Active Directory Domain Services (AD DS)** and install required components.
4. Once installed, click the **flag notification** and choose **Promote this server to a domain controller**.

## Step 3: Promote the Server to a Domain Controller
1. Choose **Add a new forest**, and set your domain name (e.g., `homelab.local`).
2. Set **Directory Services Restore Mode (DSRM) password**.
3. Complete the setup and allow the server to reboot.

## Step 4: Configure DNS Settings
1. Open **DNS Manager** from **Server Manager**.
2. Verify that forward and reverse lookup zones are correctly configured.
3. Ensure the server’s IP is listed as the preferred DNS server.

## Step 5: Create Organizational Units (OUs) and User Accounts
1. Open **Active Directory Users and Computers (ADUC)**.
2. Create Organizational Units (e.g., `Users`, `Computers`, `Admins`).
3. Add user accounts and groups as needed.

## Step 6: Join Windows 10 Machine to the Domain
1. On the Windows 10 VM, go to **System Properties** > **Computer Name** > **Change**.
2. Enter the **domain name** and provide **admin credentials** when prompted.
3. Restart the client machine to apply the changes.

## Step 7: Enable SMB Sharing and Configure CA Certificates
1. Set up **SMB file sharing** to allow access to shared resources within the domain.
2. Install and configure **Certificate Authority (CA) services** to enhance security.
3. Verify that certificates are properly issued and applied to domain machines.

## Step 8: Verify Domain Connectivity
1. Log in to Windows 10 using a domain account.
2. Run `gpupdate /force` in the command prompt to apply group policies.
3. Verify that the client appears under **Active Directory Users and Computers** in the **Computers** OU.

## Conclusion
This setup ensures a functioning **Active Directory domain environment** with a centralized management system. Future enhancements include **implementing advanced Group Policy Objects (GPOs), strengthening security policies, and integrating SIEM logging**.

For more details, refer to the official Microsoft documentation or Adam Heath’s video tutorial on AD setup.

