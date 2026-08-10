Windows-Active-Directory

A step-by-step guide documenting the deployment of a Windows Server 2022 Domain Controller using VMware Workstation. This walkthrough details VM provisioning, OS setup, network configuration, and successfully integrating a Windows 10 client machine into the domain.

<img width="1918" height="1011" alt="Screenshot 2026-08-02 180651" src="https://github.com/user-attachments/assets/38ce11eb-c6e4-451a-ac1a-b1056d95d905" />

 We start by opening VMware Workstation and launching the wizard to create a new virtual machine.

 <img width="1919" height="1013" alt="Screenshot 2026-08-02 181420" src="https://github.com/user-attachments/assets/a0170558-e2eb-405d-b316-6420a65cec64" />

<img width="500" height="300" alt="Screenshot 2026-08-02 182048" src="https://github.com/user-attachments/assets/63684b76-886b-485d-8f26-6a2d5aa1914e" />
<img width="500" height="300" alt="Screenshot 2026-08-02 182733" src="https://github.com/user-attachments/assets/72f524f8-6970-4fc2-8725-54f5719ad2f0" />
<img width="500" height="300" alt="Screenshot 2026-08-08 150416" src="https://github.com/user-attachments/assets/e4b4c63b-e75c-4785-8dcd-6782e4bd7070" />

The wizard asks how we want to install Windows. We point it to the Windows Server 2022 ISO file we have downloaded, so it can use that to install the operating system.

<img width="500" height="300" alt="Screenshot 2026-08-08 151451" src="https://github.com/user-attachments/assets/12ca8cc3-9e27-423a-9208-d33076f945bf" />

Next, we give the virtual machine a name. We call it "Windows Server 2022" and choose where on our computer we want to save it.

<img width="500" height="300" alt="Screenshot 2026-08-08 152042" src="https://github.com/user-attachments/assets/bf0745dc-8858-4006-9edf-16e4868fe44f" />

Now we decide how much storage space to give it. The recommended amount is 60 GB, so we go with that. We also choose to split the storage into multiple files, which makes it easier to move the VM to another computer if needed.

<img width="500" height="300" alt="Screenshot 2026-08-08 152252" src="https://github.com/user-attachments/assets/8ee7ee54-57af-4490-903d-2e8ce4250f36" />

The wizard shows us a summary of everything we've set up so far. We double-check the name, storage size, memory (2 GB), processors (2), and network settings (NAT), then click Finish to create the VM.

<img width="500" height="300" alt="Screenshot 2026-08-08 152500" src="https://github.com/user-attachments/assets/c93d97aa-0f9b-4fa0-8fe5-1cc22477fdd0" />

<img width="500" height="300" alt="Screenshot 2026-08-08 153336" src="https://github.com/user-attachments/assets/add52e58-ca47-4afa-9d21-2567aadc742c" />

<img width="500" height="300" alt="Screenshot 2026-08-08 153715" src="https://github.com/user-attachments/assets/a006dfde-3f6c-4ff8-8287-9ead27333d8e" />

<img width="500" height="300" alt="Screenshot 2026-08-08 154413" src="https://github.com/user-attachments/assets/3c61e16e-0402-4c6c-8750-79518df55a45" />

We are adding a second network card to your Windows Server virtual machine so it can connect to both the internet (via NAT) and an internal local network (VMnet2) to manage client devices.

<img width="500" height="300" alt="Screenshot 2026-08-08 160024" src="https://github.com/user-attachments/assets/5e0a67a1-37cb-4ae3-86d4-86bef5595c3b" />

We are clicking Finish to officially add the new Network Adapter hardware component to your Windows Server virtual machine.

<img width="500" height="300" alt="Screenshot 2026-08-08 160255" src="https://github.com/user-attachments/assets/5dbe50d7-e6a0-43ce-9881-7e0a963bf605" />

We are setting Network Adapter 2 to a Custom virtual network (so you can select VMnet2) to isolate internal LAN traffic for your client machines.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/c07427b7-2a9e-4898-959a-aa208af4bfbf" />

We are selecting VMnet2 as the specific virtual network for Network Adapter 2 to create the isolated private LAN for your internal client devices

<img width="500" height="300" alt="Screenshot 2026-08-08 160653" src="https://github.com/user-attachments/assets/19934c7e-29d6-42ec-b134-75e56b0c6197" />

We are clicking OK to apply and save your custom VMnet2 network settings for Network Adapter 2.

<img width="1918" height="1012" alt="Screenshot 2026-08-08 161114" src="https://github.com/user-attachments/assets/7c08a358-c36a-42e2-9495-0341853577c6" />

We are clicking Power on this virtual machine to boot up Windows Server 2022 and begin the Operating System setup process.

<img width="500" height="300" alt="Screenshot 2026-08-08 161508" src="https://github.com/user-attachments/assets/1c04d983-2ae6-4d40-800c-7aa1e0cd4f29" />

We are clicking Next to confirm your default regional settings (Language, Time, and Keyboard layout) to begin the Windows Server 2022 setup process.

<img width="500" height="300" alt="Screenshot 2026-08-08 162650" src="https://github.com/user-attachments/assets/30bdc748-d285-451c-bb1c-7100720cbe37" />

<img width="500" height="300" alt="Screenshot 2026-08-08 163055" src="https://github.com/user-attachments/assets/1e6e223a-aa92-4542-a9fb-90ec1ca2b3f0" />

<img width="500" height="300" alt="Screenshot 2026-08-08 163443" src="https://github.com/user-attachments/assets/b4fde6d3-3524-4a74-a7c1-2a16e8d3bc37" />

<img width="500" height="300" alt="Screenshot 2026-08-08 163748" src="https://github.com/user-attachments/assets/ae3bd7ea-39e1-494e-8351-bff4596b817b" />

You are selecting Custom: Install Microsoft Server Operating System only (advanced) to perform a clean, fresh installation on your new virtual disk.

<img width="500" height="300" alt="Screenshot 2026-08-08 163956" src="https://github.com/user-attachments/assets/07c8bbc5-ee10-4b82-81e0-9d70e9fa8154" />

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/8e54a690-2e9d-4a56-bb41-b1b9d71d8bb4" />

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/b6a0863c-5b78-4815-93df-5ee85f86c187" />

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/05cd03c3-62ee-4064-aa7c-b3a32a16d6a1" />

You are setting a password for the built-in local Administrator account and clicking Finish to finalize the Windows Server 2022 setup.

<img width="1919" height="1005" alt="Screenshot 2026-08-08 171757" src="https://github.com/user-attachments/assets/1e90e554-5688-44c7-be6d-cb70f3a5b99a" />

You are sending Ctrl+Alt+Del to the virtual machine to open the login screen without triggering your physical computer's Lock screen.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/3219d4dd-5133-4b8d-abc9-093a9c63d542" />

You are logging in to the Windows Server 2022 desktop for the first time using the local Administrator account password you just created.

<img width="500" height="300" alt="Screenshot 2026-08-08 172154" src="https://github.com/user-attachments/assets/e12c14ea-656f-413b-836f-5f65c15ca3a6" />

You are clicking Yes on the Networks prompt to enable network discovery so the server can see and communicate with other devices on the private virtual network.

⚙️ Step 2: Basic Server Configuration & Hostname Setup

Before installing Active Directory roles and features, configure the initial system parameters:
1. **System Renaming:**
   - Press **`Win + I`** to open the **Settings** menu.
   - Click on System
  
   <img width="500" height="300" alt="Screenshot 2026-08-08 173223" src="https://github.com/user-attachments/assets/62cde604-41bd-48a6-96e9-79f9ff25f483" />
   
   - Navigate to About
   - Click on "Rename this PC"
     
   <img width="500" height="300" alt="Screenshot 2026-08-08 173411" src="https://github.com/user-attachments/assets/751ce115-a8c1-4cb1-806c-b3b56543c29b" />

   - Change the computer name to **`DC-01`** (Domain Controller 01).

   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/f47f2cb7-07c1-4556-adc1-32123f9b8189" />

   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/b5a94b3f-758c-4362-8fd2-0123c232546a" />

   Click on Restart later

   <img width="500" height="300" alt="Screenshot 2026-08-08 173923" src="https://github.com/user-attachments/assets/5813f31a-3bad-4fb8-b6d1-75e82b3df135" />

   <img width="500" height="300" alt="Screenshot 2026-08-08 175231" src="https://github.com/user-attachments/assets/d52cdf2a-3837-4a43-953b-3a9b735eddef" />

   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/c0999224-2a17-49fa-a438-082c9eb90364" />

   <img width="500" height="300" alt="Screenshot 2026-08-08 184404" src="https://github.com/user-attachments/assets/e197871b-8b59-4966-910a-288d7852f078" />

   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/447ddd98-3f3d-4988-944c-f83c6fcc2929" />

   To restart Windows Server for all changes we have made to reflect
   -Run Command prompt as administrator
   
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/2f8d1340-850f-43f1-aac2-086170c2cf82" />

<img width="500" height="300" alt="Screenshot 2026-08-08 185703" src="https://github.com/user-attachments/assets/bee5967e-8ec0-46b6-89b4-c52f9c9db2e1" />

We are sending Ctrl+Alt+Del to unlock the newly restarted Windows Server 2022 virtual machine and access the login screen.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/402294ee-741e-4a9b-9b22-8d2648ff1ba0" />

We are entering the Administrator password to log back into the server after rebooting it.

<img width="500" height="300" alt="Screenshot 2026-08-08 190301" src="https://github.com/user-attachments/assets/792b5a2f-bef6-4648-821c-e380f9ee6c6a" />

We are opening the network settings from the system tray to configure your network adapters and set a static IP for your internal interface (LAN).

<img width="500" height="300" alt="Screenshot 2026-08-08 190555" src="https://github.com/user-attachments/assets/54237808-158f-4dca-a840-272c66271f11" />

We are clicking Network & Internet settings to open the Network Connections menu where you will rename your network adapters (Internet and Internal) and configure the static IP address.

<img width="500" height="300" alt="Screenshot 2026-08-08 190818" src="https://github.com/user-attachments/assets/cf25c3f1-e901-4e81-937f-e8670207d7f4" />

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/54e8541d-0b7a-4b07-a2c5-43f03a7ef142" />

We are renaming **Ethernet0** to **Internet** (WAN) and **Ethernet1** to **Internal** (LAN), then configuring a static IP address (`172.16.7.1`) on the Internal adapter.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/19b06c37-e341-4888-aeb4-742410688833" />

We are selecting Properties on the Internal (LAN) adapter to configure its static IPv4 settings (172.16.7.1)

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/8241162a-ec7d-4d82-b40e-9a5fb45f6729" />

We are selecting Internet Protocol Version 4 (TCP/IPv4) and clicking Properties to manually assign your static IP address (172.16.7.1), Subnet Mask (255.255.255.0), Default Gateway (172.16.7.1), and Preferred DNS (127.0.0.1)

<img width="500" height="300" alt="Screenshot 2026-08-08 191821" src="https://github.com/user-attachments/assets/ecb77754-8d27-4f6b-95bf-bd7c0a5e47c7" />

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/08c6315f-ca96-41e2-8b1c-7ffe5c0cb49b" />

We are entering the static network settings for the Internal (LAN) interface (172.16.7.1, subnet mask 255.255.255.0, gateway 172.16.7.1, and DNS 127.0.0.1) and clicking OK to apply them.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/fcd62a44-ab2c-4cd0-b73b-b4106551bd40" />

We are reviewing the Network Connection Details to confirm that the static IP address (172.16.7.1) and subnet mask (255.255.255.0) have been successfully applied to the Internal (LAN) interface

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/b876bfe9-35ec-46f3-a2f5-24e37d43f405" />

We are opening the Command Prompt to verify your network connectivity and IP configuration using commands like ipconfig 

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/da654fab-e225-482e-9ad5-0d669c9e032d" />

We are running ipconfig to verify that both network adapters display their assigned configurations: Internet (WAN) with dynamic IP 172.16.103.115 and Internal (LAN) with static IP 172.16.7.1

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/13031727-af06-467c-bc1f-7acadaafabe3" />

We are testing internet connectivity and DNS resolution by running ping google.com to confirm that the server can successfully reach external networks through the WAN interface.

<img width="500" height="300" alt="Screenshot 2026-08-08 193353" src="https://github.com/user-attachments/assets/5ffee549-f76c-4562-a344-cba988a3b22d" />

We are clicking Add Roles and Features in Server Manager to begin installing server roles such as Active Directory Domain Services (AD DS) or Remote Access/NAT.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/e746bcf0-77b0-4af6-b75a-826bc5db7c00" />

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/d16f2617-a981-4ded-b2ad-b560b2b60c6c" />

We are selecting Role-based or feature-based installation and clicking Next to install specific roles directly on this server.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/f0c182a8-34d6-4ef9-a28f-33b609c9f519" />

We are selecting your local server (DC-01) from the server pool and clicking Next to confirm it as the destination target for installation

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/bb2e45f2-b633-455b-a08f-b0b5fbfc4ef5" />

You are clicking Add Features on the pop-up prompt to include the necessary administration tools (Group Policy Management, Active Directory PowerShell module, Administrative Center, and Snap-Ins) required for Active Directory Domain Services.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/0543bc3c-e228-4149-b31b-abde887ee273" />

You are clicking Next on the Features page to accept the default selected features (including Group Policy Management, which was automatically added with AD DS) and move to the AD DS summary section.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/8ed6481b-db41-4d29-88ce-f792cdfa05ba" />

You are clicking Next on the AD DS overview screen to move to the confirmation page and complete the installation of the Active Directory Domain Services role.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/67b8e37f-a56e-4e09-8b1f-2e996a590791" />

You are clicking Install to start installing Active Directory Domain Services and its associated administration tools on DC-01.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/f1725cd3-57eb-4576-a27d-3018bdfa95a6" />

We are clicking Promote this server to a domain controller to launch the Active Directory Domain Services Configuration Wizard and set up your new Active Directory forest.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/08775fa6-7423-469c-9492-132c77e87f53" />

We are selecting Add a new forest, specifying ugo.local as the Root domain name, and clicking Next to proceed with setting up the new Active Directory forest

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/ba6e9094-6e99-49c7-919c-512edf3b0d7a" />

We are entering and confirming the Directory Services Restore Mode (DSRM) password, leaving the functional levels set to Windows Server 2016 and keeping DNS Server and Global Catalog checked, then clicking Next.
NOTE: The password should not be the same as the password used initially
The DSRM password is only used in emergency recovery situations when booting into safe mode to repair or restore Active Directory database files. It is completely separate from standard domain user and administrator credentials.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/5cbdb903-2321-4562-9996-07112510fa9a" />

We are clicking Next on the DNS Options page, safely ignoring the yellow warning message about DNS delegation.

This warning appears because we are setting up a brand-new root domain (ugo.local) in an isolated environment, so there is no higher-level parent DNS zone to delegate from. Leave Create DNS delegation unchecked and proceed.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/1555ee36-30a8-4a34-b04e-4b4d3904e37b" />

We are verifying the auto-generated NetBIOS domain name (UGO) and clicking Next to proceed to the database paths page.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/46649a8a-120b-4872-bf70-26cf7ee9ffc4" />

We are clicking Next on the Paths page to accept the default locations for the AD DS database (C:\Windows\NTDS), log files (C:\Windows\NTDS), and SYSVOL folder (C:\Windows\SYSVOL).

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/ec5ffda7-6c81-41ae-84a5-094368576b01" />

We are reviewing your domain configuration settings—confirming the creation of the new forest ugo.local, NetBIOS name UGO, and functional levels—and clicking Next to run the prerequisite check.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/7ca4eaf3-827a-4d00-b692-109fe6ee0630" />

We are clicking Install after seeing that all prerequisite checks passed successfully, which will promote DC-01 to a Domain Controller and automatically reboot the system when complete.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/426e9eb6-9b71-45f7-a6d3-6b4bc2aebb0f" />

We are clicking Send Ctrl+Alt+Del in the VMware menu to unlock the Windows Server lock screen after its automatic reboot following the Domain Controller promotion.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/b8827b5e-9e96-4c30-8005-4e803b05ba77" />

We are entering your password to log in as UGO\Administrator, confirming that DC-01 has successfully promoted to a Domain Controller for the UGO domain

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/7f8bd72e-8893-4cf3-820d-7f60950824f2" />

We are opening Active Directory Users and Computers from the Server Manager Tools menu to begin managing domain objects such as users, groups, and organizational units (OUs) for ugo.local

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/04c8edb3-1086-4a38-8ac1-8229f47c30b7" />

We are right-clicking on our domain name (ugo.local) to open its context menu, where you can select New to create organizational units (OUs), users, groups, or other Active Directory objects

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/41afc93b-9c8b-413e-884c-b94c453a2e89" />

We are selecting Organizational Unit under the New sub-menu to create a new OU for organizing your domain's users, groups, or computers.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/32b0f1b9-cd13-46e4-a088-55eacbd2772f" />

We are entering Admins as the Organizational Unit name and clicking OK to create the new OU within ugo.local

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/2e45e049-3eef-40b4-9d42-911a2fe6a0f1" />

We are selecting User under the New sub-menu to create a new domain user account inside the Admins Organizational Unit.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/45e684f2-48fc-4a4e-a65e-13e86c1fbc0f" />

We are filling in the user details for Ugochukwu Ugochukwu (with logon name uugochukwu@ugo.local) and clicking Next to proceed to setting the account password.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/e658f4c8-f26a-494e-9c13-ab4bcd005882" />

We are setting and confirming the password for the new user, keeping User must change password at next logon checked, and clicking Next to move to the account creation summary.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/5157ba72-2a3a-4be0-81fe-74bed9ca5995" />

bWe are clicking Finish to complete the creation of the domain user account Ugochukwu Ugochukwu (uugochukwu@ugo.local) inside the Admins Organizational Unit.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/9caf8fde-23a6-4206-b792-bba09626433b" />

We are selecting Add to a group... from the context menu to assign security groups (such as Domain Admins) to the user account Ugochukwu Ugochukwu.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/941323e4-dec7-4945-8549-0e5a07a85461" />

Click on Advanced

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/4ad1e2aa-4ecc-491a-ba24-a04a983a328c" />

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/aa586003-4308-4458-a134-c624ff810ed7" />

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/9706e320-65eb-4960-a79b-c118783ad9fa" />

Scroll down in the search results list, select Domain Admins (located in ugo.local/Users), and click OK to add the user to the group

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/cdb95883-c4c3-4da3-928d-13bf4e4f6242" />

We are clicking OK on the Select Groups dialog to finish adding Ugochukwu Ugochukwu to the Domain Admins group.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/c7405790-91ba-4093-92df-cbe1917e2141" />

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/10b43c75-7fff-4797-bab4-aab9515c557e" />

We are accessing the VMware Workstation VM menu (or clicking Send Ctrl+Alt+Del), to switch user to test logging into the domain with your newly created user account (UGO\uugochukwu)

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/cbf732e2-06fa-4bca-8662-6c9547ff0f40" />

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/10b43c75-7fff-4797-bab4-aab9515c557e" />

<img width="959" height="506" alt="image" src="https://github.com/user-attachments/assets/51d1819d-1baf-4ff3-bd47-4c9f4967f22b" />

We are logging in as uugochukwu@ugo.local under Other user to authenticate with your newly created domain account for the first time.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/8d948bea-7ab0-44d2-bd06-1c5bcea65d29" />

We are clicking OK on the prompt stating "The user's password must be changed before signing in," which was triggered by the option we enabled during account creation.

Next, we will be prompted to enter a new password and confirm it to complete the sign-in process.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/fd7f6d13-cffc-48ad-9c44-c6f97d1091c9" />

We are entering your old password followed by a new password and password confirmation for uugochukwu@ugo.local.

Click the arrow button (or press Enter) to update the password and log into the domain desktop for the first time.

<img width="500" height="300" alt="Screenshot 2026-08-09 151331" src="https://github.com/user-attachments/assets/6c856389-3a6e-4607-92aa-519d1fe3a32d" />

We are clicking Add roles and features in the Server Manager dashboard to open the setup wizard for installing a new server role or feature on Windows Server 2022

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/4f2a12e2-44c1-403c-b4aa-5e792469d703" />

We are clicking Next on the Before You Begin page of the Add Roles and Features Wizard to proceed to selecting the installation type for DC-01.ugo.local.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/860e1b3b-2a76-43fa-95c1-e64df3681405" />

We are clicking Next on the Select installation type page to accept the default Role-based or feature-based installation option and move forward to selecting the target server.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/bfb6b040-37fb-4438-af0c-053ec44b3e35" />

We are clicking Next on the Select destination server page with DC-01.ugo.local selected from the server pool to proceed to selecting server roles

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/5de2bbd2-596c-4e44-97ed-7d2566362a75" />

We have checked the Remote Access role and are ready to click Next to proceed to the Features selection page (or configure Remote Access sub-services)

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/a2c28730-b44f-40cc-8500-b4248e489eb3" />

We are on the Select features step of the Add Roles and Features Wizard. Since no additional features are required for Remote Access beyond the default selections, click Next to proceed to the Remote Access configuration page

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/5aab34b6-b45e-4c89-b7b0-16631bea47eb" />

We are on the Remote Access overview page of the wizard. Click Next to proceed to the Role Services page, where you can select specific components like DirectAccess and VPN (RAS) or Routing.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/e4c9aee0-4ffe-4661-be8f-ff2df0ebbb6b" />

We are on the Select role services page for the Remote Access role.
To proceed:
Check the box for DirectAccess and VPN (RAS) (and/or Routing, depending on your lab requirements)

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/cca0c64b-cd72-438c-ac3d-1379dd6785d6" />

You are clicking Add Features on the popup to include the necessary management tools (like Web Server IIS and RSAT Remote Access Management Tools) for DirectAccess and VPN (RAS)

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/642fe25c-86aa-4589-92bf-eb8bc949593b" />

We have selected both DirectAccess and VPN (RAS) and Routing under Role Services. Click Next to proceed through the Web Server Role (IIS) information pages and advance toward the final confirmation step.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/e96929be-68d1-4b98-86ea-6524e957bb01" />

We are on the Web Server Role (IIS) overview page, which is required as a dependency for Remote Access. Click Next to proceed to the IIS role services selection page.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/f55e8c2e-20ad-448c-b77e-1e32f490c5f6" />

We are on the Select role services page for Web Server (IIS) with all default prerequisites selected. Click Next to proceed to the Confirmation screen and click Install to finish setting up Remote Access and IIS on DC-01.ugo.local

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/81cd922d-c606-48f3-aa65-8fb5b012c2d3" />

We are on the Confirm installation selections page, reviewing the listed roles and features for DC-01.ugo.local (including DirectAccess, VPN, Routing, RSAT tools, and Web Server IIS).
Click Install to start installing the selected roles and features on your server.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/429a0f30-bec5-4fa1-8445-b303b3b0afca" />

We are clicking Routing and Remote Access under the Tools menu in Server Manager to open the management MMC snap-in so you can configure and enable RRAS (such as NAT, VPN, or LAN routing) on DC-01.ugo.local.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/7e53081d-2375-4e54-bf91-06af8d76eeb9" />

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/4ed60a90-7fc4-49ec-9f46-268f920a6b21" />

We are clicking Next on the welcome page of the Routing and Remote Access Server Setup Wizard to proceed to the configuration options page (where you can select NAT, Remote access/VPN, or Custom configuration).

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/18de498e-6dab-4c9b-bb6c-92182864d93c" />

We are selecting Network address translation (NAT) on the Configuration page of the Routing and Remote Access Server Setup Wizard.
Click Next to proceed, where you will select the public-facing network interface that connects to the internet to complete the NAT configuration.

Click on Cancel

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/429a0f30-bec5-4fa1-8445-b303b3b0afca" />

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/5195dac8-cbc0-4571-9561-dd616593be7c" />

We are selecting Refresh after canceling or stepping out of the setup wizard to update the console status for DC-01 (local).
To restart and complete the NAT setup, right-click DC-01 (local) again and click Configure and Enable Routing and Remote Access.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/4ed60a90-7fc4-49ec-9f46-268f920a6b21" />

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/18de498e-6dab-4c9b-bb6c-92182864d93c" />

<img width="959" height="504" alt="image" src="https://github.com/user-attachments/assets/c234a261-6e01-44a6-a823-3992c2ded7c3" />

Click Next > at the bottom of the wizard window to proceed with Internet (WAN) as your public NAT interface.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/11175e11-92d2-4966-adf1-68ffc987096f" />

Click Finish to complete the Routing and Remote Access Server Setup Wizard. The RRAS service will start automatically, enabling Network Address Translation (NAT) on Internet (WAN) to provide outbound internet connectivity for your internal network clients.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/7160e74e-8e55-4a84-b7d3-3dbcbb65a0b6" />

We're all set! The green arrow on DC-01 (local) indicates that Routing and Remote Access (RRAS) is active and running with NAT enabled.

To verify or view your NAT setup in detail:
Expand IPv4 in the left tree menu.
Click on NAT to manage your public/private interfaces, check active connections, or configure port forwarding rules.

**The next thing we are configuring is DHCP Server**

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/5dd87f3c-301a-4ca8-a8be-bd5e97e4fa52" />

We are clicking Add Roles and Features under the Manage menu in Server Manager to start adding a new role or feature to your server.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/bf1bb090-8cc0-4312-9cc0-16c1df9003f9" />

Click on Next

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/84d6d7be-8e4b-4dd2-809c-5a4a94f9c768" />

Click on Next again

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/b709b7f7-0302-4b44-8c3c-9f296076bd0c" />

We are on the Select destination server page with DC-01.ugo.local selected in the server pool.
Click Next > to proceed to the Server Roles page.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/f1e2a21b-3a47-4a38-b565-f07d1c6e62f8" />

Check the checkbox next to DHCP Server in the Roles list.
A popup window will appear asking to add required management features—click Add Features, then click Next > to continue setting up the DHCP Server role.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/a9fc2a20-f8c4-483f-be73-75e7ede37012" />

We are on the Select features page. Since no extra features are required for DHCP Server beyond what was added automatically, click Next > to proceed to the DHCP Server introduction page.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/5654be23-b156-4427-8f23-f1115db33134" />

Click Next again 

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/1de4837b-52e4-4ade-8226-b256d0e4cec3" />

Click Install at the bottom right of the wizard to begin installing the DHCP Server role along with its management tools on DC-01.ugo.local

**We are going to be using this:
IP RANGE: 172.16.7.100 - 200
SUBNET MASK: 255.255.255.0
DEFAULT GATEWAY: 172.16.7.1
DNS SERVER: 172.16.7.1
**

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/b9940c83-bf29-4d55-bdac-cb6a06f44d41" />

You are clicking DHCP under the Tools menu in Server Manager to open the DHCP MMC console.
Once opened, you can create new IP address scopes, configure lease durations, and set up DHCP options (like gateway and DNS servers) for your network clients.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/99c796b0-f466-4c85-869d-fa907c66dbe8" />

Click on Next

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/a808e998-1908-42b6-b062-b7a3ba0caf24" />

We are on the Scope Name page of the New Scope Wizard with the name set to 172.16.7.100 -200 and description My Local PC connection to Server.
Click Next > to proceed to the IP Address Range screen, where you will enter the start IP address, end IP address, and subnet mask for this scope.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/277bf154-f4c0-44f9-9b5f-dc804a52c902" />

We are on the IP Address Range page of the New Scope Wizard.
Verify that your IP range (172.16.7.100 to 172.16.7.200) and subnet mask (255.255.255.0 / /24) are correct for our internal network.
Click Next > to proceed to the Add Exclusions and Delay page.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/04829083-bfe9-485e-98dc-3f51215d64d0" />

We do not need exclusions, leave the fields blank and click Next > to proceed to Lease Duration.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/edb18f59-0a0a-4a77-b936-f98f193166a8" />

Leave the default lease time set to 8 Days.
Click Next > to move to the Configure DHCP Options page.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/f5a3b517-4449-4b6b-8e57-4e55842c45a8" />

Ensure Yes, I want to configure these options now is selected.
Click Next > to proceed to the Router (Default Gateway) configuration step.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/67d6ee56-4612-45f7-b95a-4ff6b0b7db74" />

Click the Add button to move 172.16.7.1 into the list box below.
Click Next > to proceed to the Domain Name and DNS Servers settings page.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/905ad974-29ef-44c8-b13c-19d4370231e2" />

We are on the Domain Name and DNS Servers page with our parent domain set to ugo.local and DNS server IP set to 172.16.7.1.
Click Next > to proceed to the WINS Servers configuration screen.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/bdd09379-7c70-4dab-90fc-88e10f814a6a" />

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/f4455b1c-4bfc-47c2-ba4e-f38e059aec86" />

Keep Yes, I want to activate this scope now selected so the server begins servicing DHCP requests immediately.
Click Next > to proceed to the final completion screen, where you can click Finish to complete the wizard

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/874d2561-5b28-44ad-99ff-804cb2e18e93" />

Click Authorize to authorize this DHCP server in Active Directory.

Once clicked, right-click dc-01.ugo.local (or press F5) to refresh the view.
The red down-arrow icons next to IPv4 and IPv6 will change to green checkmarks, indicating the DHCP server is authorized and active in the domain.

**Now we are going to create users while logging in with the Domain Admin**

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/b366c4f7-9108-4d68-bcce-09bf3ccd1551" />

We are selecting Active Directory Users and Computers under the Tools menu in Server Manager.
Clicking this will launch the dsa.msc console, where we can manage domain users, groups, organizational units (OUs), and computer accounts for ugo.local.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/331d68d1-9712-4bc4-96fa-9de505f0145b" />

We are right-clicking ugo.local and selecting New > Organizational Unit.
Click Organizational Unit to open the creation dialog, where we can enter a name for the new OU (such as "Employees" or "Departments") to help organize your domain accounts.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/2c1d489f-29e8-4128-b9f2-b5112506e934" />

We are on the New Object - Organizational Unit dialog with the name set to Ugo Company LTD.
Leave Protect container from accidental deletion checked.
Click OK to create the new Organizational Unit under ugo.local

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/3af115f0-2871-48a2-b333-1505fface6a8" />

We are right-clicking the newly created Ugo Company LTD OU and selecting New > Organizational Unit.
Click Organizational Unit to create a sub-OU under Ugo Company LTD (such as IT, HR, Sales, or Users) to further structure our Active Directory hierarchy

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/3ecb6b60-b9e5-4845-8027-9362373189a1" />

We are creating a new Organizational Unit named IT inside ugo.local/Ugo Company LTD.
Keep Protect container from accidental deletion checked.
Click OK to create the IT sub-OU.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/8d480fea-e1aa-4666-ab87-e7b244db367f" />

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/b582d33f-6f78-4b50-8932-ce8771965261" />

We are creating another sub-OU named HR inside ugo.local/Ugo Company LTD.
Keep Protect container from accidental deletion checked.
Click OK to create the HR Organizational Unit

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/19d3e8a2-4c54-4686-9302-45ef510f72b7" />
We are creating another sub-OU named Sales inside ugo.local/Ugo Company LTD.
Keep Protect container from accidental deletion checked.
Click OK to create the Sales Organizational Unit

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/c65a1ade-98d7-4517-9497-2b4327d4f290" />

We are right-clicking the IT Organizational Unit and selecting New > Group.
Click Group to launch the creation dialog, where we can define a security or distribution group name (such as System Admin) and select its group scope and type.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/1f86774b-9e35-426e-a453-808a25079b24" />

We are on the New Object - Group dialog, creating a group named System Admin inside ugo.local/Ugo Company LTD/IT.
Keep Group scope set to Universal if cross-forest/multi-domain access is required.
Ensure Group type is set to Security.
Click OK to create the new group.

<img width="500" height="300" alt="Screenshot 2026-08-09 173503" src="https://github.com/user-attachments/assets/e777f55b-5091-436f-ab3f-377adecfc5db" />

We are pointing at the Create a new user in the current container icon on the Active Directory toolbar (the icon showing a single person with a small starburst/sparkle).
Click that toolbar icon (or right-click an empty area in the right pane and select New > User).
Enter the user details (First Name, Last Name, User Logon Name).
Click Next to set the initial password and account options, then click Finish to create the user inside the IT Organizational Unit.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/3a9cf7d1-3b2b-4f90-a8c4-62645d3d2cdb" />

We are on the New Object - User dialog creating the user account for Timi Lawal (tlawal@ugo.local) in the ugo.local/Ugo Company LTD/IT OU.
Click Next > to proceed to the password configuration screen.
Set a secure password for the user, configure password options (e.g., User must change password at next logon), and click Next >.
Click Finish to complete the user creation wizard.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/ac16c473-5d0d-4125-9900-9e35bc39f6f3" />

We have updated the selection to Password never expires.
Click Next > to proceed to the summary page.
Review the user creation summary and click Finish to finalize creating the user account in the IT OU.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/b8eaf17d-3c95-4b4b-b9e6-f60a45980e88" />

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/4f65226d-b998-4dec-a949-7e9de5f72ba1" />

Click Add to a group... to open the group selection dialog.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/84221e27-5aa4-4963-ab00-70b329f7ecf4" />

In the Enter the object names to select box, type System Admin.
Click Check Names to resolve the name, then click OK.
Click OK on the confirmation prompt stating that the add to group operation was successful

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/66ec2a77-2721-429f-a4e2-f14a96811dcb" />

We are right-clicking the Sales Organizational Unit and selecting New > Group.
Click Group to open the creation dialog.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/6ed72128-75ed-417a-8ff6-9cc9be6f870a" />

Enter a group name for the Sales department (Managers).
Ensure Group scope is set to Global and Group type is set to Distribution, then click OK.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/492bed13-7eb8-4eb2-ba80-6146eae03358" />

Click that toolbar icon (or right-click an empty area in the right pane and select New > User).
Enter the user details (First Name, Last Name, User Logon Name).
Click Next to set the initial password and account options, then click Finish to create the user inside the Sales Organizational Unit.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/95694250-97ef-42a2-ac61-250f90d6738c" />

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/2f047d04-0e65-4773-a49c-e24c44e617c7" />

We are right-clicking the IT Organizational Unit again to create a new Group.
Click Group to open the creation dialog.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/27eaff18-3c4e-4fd2-a5d5-ddcae5014717" />

Type the group name (IT Support).
Ensure Group scope is Global and Group type is Security, then click OK.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/ec946a64-670b-4d32-9245-5b1d7a1e92bc" />

Click that toolbar icon (or right-click an empty area in the right pane and select New > User).
Enter the user details (First Name, Last Name, User Logon Name).

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/5f3f1b63-37ca-45f6-a2e8-bac7ad4073c5" />

Click Next to set the initial password and account options, then click Finish to create the user inside the IT Organizational Unit.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/b0d3d535-3c76-4b41-a73d-fe30960fad15" />

We are adding Bode Williams to a group.
Click Add to a group... from the context menu.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/252d03a4-ede2-45bf-8a26-9b8a582b3eae" />

In the selection prompt, type IT Support (or the desired group name).
Click Check Names, then click OK.
Click OK on the confirmation dialog to complete adding Bode Williams to the group.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/2f8d0a9e-019e-4833-9bf0-95b704665da1" />

We are right-clicking Ugo Company LTD and selecting Delegate Control... to launch the Delegation of Control Wizard.
Click Delegate Control... to open the wizard.
Click Next on the Welcome page.

Click Add... to select the users or security groups (e.g., System Admin or IT Support) you want to give administrative permissions to.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/ecc24b84-207e-4989-9474-b5e696d81c18" />

Select the specific tasks to delegate (e.g., Create, delete, and manage user accounts or Reset user passwords), then click Next and Finish.

We have selected Bode Williams (bwilliams@ugo.local) to receive delegated control.
Click OK to confirm the selected user.
Click Next > on the Users or Groups page.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/f08a07f2-6c9b-48a5-a95a-fa0be9750101" />

Select the tasks we want to delegate (such as Create, delete, and manage user accounts or Reset user passwords and force password change at next logon), then click Next >.
Click Finish to complete delegating control to Bode Williams.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/edb46872-bed9-4348-85ec-8cacfc6676d4" />


We are right-clicking Ugo Company LTD again to delegate control.
Click Delegate Control... to launch the wizard.
Click Next on the welcome page.
Click Add..., type the group name (IT Support), click Check Names, and then click OK.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/2e402806-05d6-4e4a-be94-4f3078b5dbfa" />

Select the permissions to delegate (such as Create, delete, and manage user accounts), then click Next and Finish.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/8982efcd-dc20-4cff-8e41-e40b560382dc" />

We have opened the VM menu in VMware Workstation.
Click Send Ctrl+Alt+Del to access the Windows Server log screen or lock menu.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/183d92c1-7d1c-4c2b-927f-3eea74bc4047" />

Select Switch User to switch accounts and test logons for your new users (bwilliams)

**We are bringing in a client now**

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/e167ceac-0b1c-4c1f-b2bd-747f659172ca" />

Click on New Virtual Machine

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/20c0dd66-bab1-4edc-a465-4274c179b6cf" />

<img width="500" height="300" alt="Screenshot 2026-08-09 185313" src="https://github.com/user-attachments/assets/bcf18344-132b-439b-b9db-45a8b6983500" />

<img width="500" height="300" alt="Screenshot 2026-08-09 185643" src="https://github.com/user-attachments/assets/9ae6e435-1776-4225-bd11-d70f125ae1d0" />

Click on Next

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/9e6c7a0c-3c30-4e2c-9ca8-da3a9122489b" />

Click on Next

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/b055c6dd-282d-4ee7-8e42-1e06f4271b3c" />

Click on Next

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/c312c083-7d07-4a34-9496-db3269f290bc" />

We are configuring encryption for the virtual TPM required by Windows 11.
Keep Only the files needed to support a virtual TPM selected (this provides better performance than encrypting the entire VM disk).
Make sure you remember or save the encryption password you typed.
Keep Remember the password for this virtual machine in Credential Manager checked so VMware won't ask for it every time we power on the VM.
Click Next >.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/c50b20fb-7ad5-4678-a81e-1f240fc0ad86" />

We are on the Specify Disk Capacity step set to 64 GB.
Leave Maximum disk size (GB) set to 64.0 (or increase it if you need additional storage).
Choose your preferred disk storage format:

Store virtual disk as a single file: Recommended for better disk performance.

Split virtual disk into multiple files: Recommended if you plan to move this VM to another computer via USB drive.

Click Next >.

Click Finish on the summary page to create the Windows 11 virtual machine.

<img width="500" height="300" alt="Screenshot 2026-08-09 190733" src="https://github.com/user-attachments/assets/a86fe7d7-9517-4da9-b795-c6246c770ed8" />

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/34b66bb5-dfd0-4bd2-8f58-736cb63d8bbd" />

Click OK at the bottom of the Virtual Machine Settings window to save the network configuration (VMnet2).
Click Power on this virtual machine (green play icon in VMware).
Important: Click inside the black VM screen immediately as it turns on and press any key on your keyboard 

<img width="500" height="300" alt="Screenshot 2026-08-09 191404" src="https://github.com/user-attachments/assets/8e95ff42-e891-4eba-a16b-c69b8e319169" />


<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/2574057f-6bb5-4709-be8d-26635cb2017a" />

Click Next on the current screen (Language and regional settings).
Click Install now.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/1a9a8bdd-3cf9-4111-ad24-39114173c138" />


<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/ad1be6b4-01c4-4b5d-9dac-fb5e28a197f2" />

We are right-clicking the main Ugo Company LTD Organizational Unit and selecting New > User.
Click User to open the user creation wizard.


<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/26b1812d-5854-44ec-be0b-5adbdeb890c6" />

Enter the user's details (First name, Last name, and User logon name).
Click Next >, set the password and password options, then click Next > and Finish.


<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/7a31fc44-36db-4c6e-b4f3-7df775522ac9" />

We are creating the user account for Malik Vuwa (mvuwa@ugo.local) directly inside ugo.local/Ugo Company LTD.
Click Next >.
Enter and confirm the password for Malik Vuwa.
Select your password options, then click Next >.
Click Finish to complete creating the user account.


<img width="959" height="505" alt="image" src="https://github.com/user-attachments/assets/a9116fc6-b92d-4983-88e9-a7eed94f37f0" />

We are naming the new Organizational Unit Service Executives inside ugo.local/Ugo Company LTD.
Keep Protect container from accidental deletion checked to prevent accidental deletion of the OU.
Click OK to create the Service Executives OU.
The new OU will now appear listed under Ugo Company LTD alongside IT, HR, and Sales.


To move Malik Vuwa into the Service Executives Organizational Unit:
In the left pane of Active Directory Users and Computers, click on the parent folder Ugo Company LTD to view its contents in the right pane.
In the right pane, right-click on Malik Vuwa and select Move....
In the Move dialog box, expand ugo.local > expand Ugo Company LTD.
Click to select the Service Executives OU.
Click OK.


<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/a5d1bb0e-27c8-46a2-8e16-267e2352d3eb" />

Clicking Properties will open the detailed account properties window for Malik Vuwa.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/e6024722-9cb9-492a-90b6-a35171362e5a" />

The Unlock account checkbox becomes active when a user is locked out after entering the wrong password too many times (based on your Active Directory Account Lockout Policy).

When checked:

It clears the lockout flag on the user's account (mvuwa), allowing them to attempt logging in again immediately without waiting for the automatic lockout duration timer to expire.

Then click apply and Ok

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/b43c223c-45f2-4f73-b042-9952759dd88a" />

**To reset User's password:**
Click Reset Password... (currently highlighted in blue).

In the dialog box that pops up:

Enter a New password and confirm it.

Check User must change password at next logon if you want Malik to create their own password when logging in.

Check Unlock the user's account if Malik was locked out.

Click OK to apply the new password

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/e0775ae1-0f39-4fa3-be13-9d8504c9a6da" />

The User must change password at next logon option forces the user to set a brand new password the moment they attempt to log into their computer.


### 🔑 Password Reset & User Notification Process

#### **1. Active Directory Password Reset Configuration**
When resetting a domain user account's password in Active Directory Users and Computers (ADUC):

* **Temporary Password Assignment:** A temporary default password (e.g., `passmein2$`) is generated for the initial login.
* **Force Password Change at First Logon:** The option **"User must change password at next logon"** is checked.
  * **Security & Compliance:** Forces the user to establish a private, non-shared password immediately upon authentication, ensuring administrators do not retain knowledge of active credentials.
  * **Session Requirement:** If the target user is currently logged into a session, they must log off and authenticate again for the mandatory password prompt to take effect.

 

**We can as well draft this and have it sent to Malik**
---

#### **2. Service Desk Notification Template**

**Subject:** Action Required: Your Active Directory Password Reset Request

Dear Malik,

Kindly be informed that your password reset request has been processed.

Please use the temporary default password below to log in. Upon your first successful authentication, the system will automatically prompt you to establish your own preferred password:

* **Default Password:** `passmein2$`

> **Security Note:** If you did not request a password reset, please notify the IT Service Desk immediately.

Best regards,  
**IT Service Desk**  
*Ugo Company LTD*



**### ⏳ Automated Account Offboarding: 6-Month Contract

#### **Scenario Context**
A 6-month temporary contractor, **Malik Vuwa**, has been onboarded into the **Service Executives** Organizational Unit (`ugo.local/Ugo Company LTD/Service Executives`) starting **August 9, 2026**. 

To comply with identity lifecycle management policies and least privilege standards, IT administration must automate account termination exactly six months from start date (**February 9, 2027**).

---

#### **Administrative Implementation**
1. **Target Account:** `mvuwa@ugo.local`
2. **Configuration Path:** `Active Directory Users and Computers` ➔ `Ugo Company LTD` ➔ `Service Executives` ➔ `Malik Vuwa Properties` ➔ **Account** Tab.
3. **Expiration Policy Applied:**
   * Selected **Account expires: End of:**
   * Set target date to **Tuesday, February 9, 2027** (6 months from creation date).
   * Clicked **Apply** to save the rule to Active Directory, followed by **OK**.

---

#### **Technical & Security Impact**
* **Automated Deactivation:** At **11:59:59 PM on February 9, 2027**, Active Directory automatically expires the account. Malik will be blocked from initiating new domain logons across workstations, VPNs, and internal network resources.
* **Session & Kerberos Revocation:** Active sessions attempting to renew Kerberos service tickets after the 6-month threshold will fail, revoking access to domain shares even if desktop sessions remain open.
* **Compliance Standard:** Eliminates "orphan" contractor accounts automatically without requiring manual IT intervention on the contract completion date.**

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/eded9480-d5fe-4438-8283-94f1a386d338" />
Click on Properties > Accounts

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/b07a276a-0eab-4d84-85d4-c43869b13dba" />



### ⏱️ Time-Restricted Guest Access & Same-Day Offboarding

#### **Scenario Context**
An external consultant, **Toni Babalola**, requires temporary domain access in the **Service Executives** Organizational Unit (`ugo.local/Ugo Company LTD/Service Executives`) to conduct an audit on **Sunday, August 9, 2026**.

To implement strict Zero-Trust boundaries, IT administration must enforce two critical access controls:
1. **Logon Hours Enforcement:** Limit active system logons strictly to standard working hours (e.g., 8:00 AM – 5:00 PM) to prevent unauthorized off-hours authentication.
2. **Same-Day Expiration:** Guarantee automatic account termination at midnight on the same day.

---

#### **Administrative Implementation**

##### **Step 1: Configure Restricted Logon Hours**
1. **Path:** `Active Directory Users and Computers` ➔ `Ugo Company LTD` ➔ `Service Executives` ➔ `Toni Babalola Properties` ➔ **Account** Tab.
2. Click the **Logon Hours...** button.
3. Highlight unauthorized hours (e.g., all hours outside 8:00 AM – 5:00 PM) and select **Logon Denied** (indicated by white blocks).
4. Ensure only authorized hours are marked as **Logon Permitted** (indicated by blue blocks), then click **OK**.

##### **Step 2: Configure Account Expiration**
1. On the **Account** tab under **Account expires**, select **End of:**.
2. Set the target date to **Sunday, August 9, 2026**.
3. Click **Apply** to write the security settings to Active Directory, followed by **OK**.

---

#### **Technical & Security Impact**
* **Off-Hours Authentication Prevention:** If Toni attempts to authenticate outside the defined **Logon Hours** matrix, the Domain Controller will immediately reject the request with an authorization error (`Logon failure: user not allowed to log on to this computer`).
* **Active Session Handling:** Depending on Group Policy settings (*"Network security: Force logoff when logon hours expire"*), existing sessions will either be forcefully disconnected or prevented from accessing network resources once logon hours end.
* **Complete Same-Day Termination:** At **11:59:59 PM on August 9, 2026**, Active Directory permanently expires the account, ensuring no lingering access remains for subsequent days.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/d89294d9-29f8-48f4-8237-ff913ab9ca26" />
Let's create a new user

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/5ab4b92d-8169-49e4-9556-fca942211f77" />

Click Next >.

Set and confirm the temporary password for Toni Babalola (passmein2$).
Click Next > and Finish
  
<img width="500" height="300" alt="Screenshot 2026-08-09 211823" src="https://github.com/user-attachments/assets/0ee51431-81a1-4535-839c-25433c2d5fd9" />

Click the **Logon Hours...** button

<img width="500" height="300" alt="Screenshot 2026-08-09 212159" src="https://github.com/user-attachments/assets/ae563851-b802-41b6-80f1-f413b9becec7" />

Ensure only authorized hours are marked as **Logon Permitted** (indicated by blue blocks), then click **OK**.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/faa87215-7faa-429b-91d2-19cbc0d8e657" />
Go back to properties > Click on Accounts

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/7b71b875-482b-4641-a617-548c5944f984" />
 Click **Apply** to commit changes to Active Directory, followed by **OK**

**Now Let's go back to our Windows 11 setup**

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/b573cb20-f0df-4a13-afb2-dc4c7d74cea9" />

We are setting up a local user account on a Windows 11 client machine during the initial Out-of-Box Experience (OOBE).

Click Next to proceed.

Enter a password for this local user account when prompted (or leave it blank for no password, though a password is recommended for lab environments).

Complete the security questions or privacy settings prompts to reach the Windows desktop.


<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/36d09452-f06e-43d3-a63d-3156e0fdb8a6" />
Press Windows + I to open Settings

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/86675a5b-381e-4afb-ab35-5849be3e4014" />

Click About
Under Related settings, click:
Advanced System settings (this opens "System Properties")

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/64001dc8-fccc-4435-a888-271e0a897bf7" />

In the System Properties window:
Go to the Computer Name tab
Click Change
Select Domain (not workgroup)

Enter the domain name: ugo.local
When prompted for credentials: 
You must use a valid domain admin account format, for example:

ugo.local\uugochukwu
Final steps:
Enter the admin password
Click OK
Wait for confirmation 

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/58df3506-8236-46b0-b5be-a9f243970b3d" />

Click on Active Directory Users and Computers (currently highlighted in blue under the Tools menu) to open the domain management console.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/89e5ff99-8fec-4238-bfcf-4d82d9b6f41f" />

We are currently looking at the Computers default container in Active Directory Users and Computers, which contains a computer account named HQ.

This is the default landing folder for computer accounts in Active Directory.

When a machine (like HQ) joins the ugo.local domain, it automatically lands here. To apply company security policies to it, you must move it into an Organizational Unit (OU) under Ugo Company LTD.

**Go back to Windows 11**

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/f0f0b6ea-2a83-428c-a287-c064ef71f6b7" />

Open Command prompt 
Type ipconfig 

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/5d3f7260-53aa-4fe6-8e08-fa323e58a5de" />

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/d07bcdb9-2c34-46cd-9a7e-99a364a806af" />

Our Windows 11 machine is properly connected to the local network and domain infrastructure.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/c72a9380-2f97-4582-9e07-520ef3ca37d2" />

The "whoami" command output confirms that you are successfully logged in as the domain user ugo\tbabalola

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/9d1d3987-3591-430c-a86f-f376eebb59f4" />

The "arp -a" command displays the ARP (Address Resolution Protocol) table, which maps IP addresses to physical MAC addresses on your local network segment

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/664720c6-a87c-4069-8d6d-c6087936ed7b" />

The ping google.com output confirms active external internet connectivity and functional DNS resolution on your client machine.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/01c0825a-e2f5-4a79-a108-c982d13b3170" />

The klist output displays the cached Kerberos tickets for the currently authenticated domain session (tbabalola @ UGO.LOCAL)

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/a7a44522-e431-4ebc-a565-eb3969eb0cf7" />

The ipconfig /all command displays the full, detailed network configuration of your client workstation.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/f6b51a09-2d6b-4435-aa41-651d3f8630b8" />

The ping ugo.local output confirms that domain name resolution and basic ICMP reachability to your Active Directory Domain Controller are working properly.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/3f580114-a7ac-4b9b-918c-449cc5c4863e" />

The nslookup ugo.local output verifies DNS query resolution and reveals the underlying domain controller structure.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/c21a7c7c-1beb-4cb6-a5ec-f4db83b320ee" />

The net user /DOMAIN command lists all user accounts created across the ugo.local Active Directory domain (queried directly from domain controller \\DC-01.ugo.local)

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/1397c2c8-f256-4778-bd8f-ea6749f19da7" />

The net user tbabalola /DOMAIN command displays the detailed Active Directory properties for the user tbabalola

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/a216987b-daef-4ce1-a21f-c3953553d440" />

Clicking Disable Account will immediately prevent the HQ computer object from authenticating with Active Directory (ugo.local).

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/b48b831b-c03d-4526-a3ca-aa0cf93e846c" />

Click Yes to confirm disabling the computer account.

**Go back to Windows 11**

Switch User

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/04c2a373-d8a6-466e-ba97-830618443cfb" />

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/16c648ff-57ae-4fe1-af33-9e2b13312a6f" />

Press Enter (or click the arrow button next to the password field) to submit the login credentials for tbabalola.

Because you disabled the HQ computer account on the domain controller in the previous step, Windows will attempt to authenticate with ugo.local and trigger the expected security error:

"The trust relationship between this workstation and the primary domain failed."

This confirms that disabling the computer account successfully blocks domain logons across the endpoint.

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/3638587e-b6ea-45ee-b593-7963344aad74" />
