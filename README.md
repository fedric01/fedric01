# Configuring Remote Desktop Access from macOS to an Azure Windows VM

## Project Summary
This tutorial guides IT Helpdesk trainees through setting up Remote Desktop from a Mac to a Windows Virtual Machine (VM) hosted on Microsoft Azure. It’s designed to mimic a Helpdesk task, such as remotely troubleshooting or managing systems. The tutorial covers Azure VM configuration, connection setup, and common troubleshooting steps.

- **Type:** Tutorial
- **Languages Used:** None (configuration-based)
- **Environments Used:** macOS Sonoma, Microsoft Azure (Windows 10 VM)
- **Technology/Applications/Services Used:** Microsoft Remote Desktop (Mac App Store), Azure Virtual Machines, Windows Remote Desktop Protocol (RDP)

## Media
The following visuals demonstrate key steps in the setup process:

1. **Screenshot 1:** Azure Portal with VM Details, showing the `windows-vm` virtual machine, its public IP address, and status.  
   [Azure Portal with VM Details]

<img width="1525" alt="IP" src="https://github.com/user-attachments/assets/c9f8de42-e166-41cb-a9eb-bdeab3985848" />



2. **Screenshot 2:** Entering Credentials in Microsoft Remote Desktop, using the VM’s IP and username.  
   [Entering Credentials]

   <img width="1516" alt="REMOTE CRED" src="https://github.com/user-attachments/assets/b97320c4-701d-411f-9a44-f314232506ac" />

5. **Optional Video:** A 1-2 minute demo of the setup and login process.  



https://github.com/user-attachments/assets/eb391f68-a2e1-4619-8609-212794c60858



https://github.com/user-attachments/assets/7e898804-ebe3-49bb-9993-fbebbfdc4827




https://github.com/user-attachments/assets/03a166c9



## Demonstration
Follow these steps to configure and use Remote Desktop from a Mac to an Azure Windows VM.

### Step 1: Install Microsoft Remote Desktop
- Open the Mac App Store, search for “Microsoft Remote Desktop,” and click “Get” to install.
- Launch the app from Applications or Launchpad.

### Step 2: Set Up the Azure Windows VM
- Log in to the Azure Portal (portal.azure.com) with your training credentials.
- Navigate to “Virtual Machines” and locate your Windows 10 VM, named `windows-vm`, in the resource group `LABTESTRCIO`, as shown in Screenshot 2.
- Enable Remote Desktop:
  - In the VM’s “Settings” > “Networking,” confirm an inbound rule allows port 3389 (RDP) from your IP or “Any” (for training).
- Note the VM’s public IP address (`20.81.201.170`) from the “Overview” page.
- Wait for the VM’s status to change from “Creating” to “Running” before proceeding.

### Step 3: Configure the Connection on Mac
- In Microsoft Remote Desktop, click “Add PC” or the “+” icon.
- Enter:
  - **PC Name:** The VM’s public IP address (`20.81.201.170`).
  - **Friendly Name:** “Azure Training VM.”
  - **User Account:** Add the VM’s admin credentials (username: `labuser`, password: __________).
- Optional: Adjust “Display” settings for resolution or enable “Redirect Folders” for file sharing.
- Click “Add” to save the connection.

### Step 4: Connect and Test
- Double-click the `windows-vm` entry in Microsoft Remote Desktop to connect.
- Accept certificate warnings (common in training environments).
- Verify the Windows VM desktop loads. Test functionality by:
  - Opening File Explorer to navigate folders.
  - Running Event Viewer to simulate checking system logs (a common Helpdesk task).
  - Copying text between macOS and Windows to test clipboard sharing.

### Troubleshooting Tips for Beginners
- **“Connection Failed” Error:**
  - Check if the VM is running (Azure Portal > Overview > Status should say “Running,” not “Creating”).
  - Verify the IP address (`20.81.201.170`) and port 3389 (Networking > Inbound Rules).
  - Restart your Mac’s network (e.g., toggle Wi-Fi).
- **“Invalid Credentials” Error:**
  - Confirm username (`labuser`) and password in Microsoft Remote Desktop.
  - Reset the VM’s password in Azure (VM > “Reset password”).
- **Slow Connection:**
  - Lower display resolution in Microsoft Remote Desktop settings.
  - Test internet speed (aim for 5 Mbps+ for RDP).
- **Certificate Warning:**
  - Safe to accept in training; in production, verify with IT.
- **Helpdesk Tip:** Log all steps and errors in a ticketing system (e.g., osTicket) for documentation.
