<img width="959" height="505" alt="image" src="https://github.com/user-attachments/assets/cf566cdb-53aa-4448-ad79-56b6b13f48c4" /><img width="959" height="506" alt="image" src="https://github.com/user-attachments/assets/390b4de0-9b94-4358-9993-d3dff72fb7ab" />Windows-Active-Directory

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

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/5195dac8-cbc0-4571-9561-dd616593be7c" />

You are selecting Refresh after canceling or stepping out of the setup wizard to update the console status for DC-01 (local).
To restart and complete the NAT setup, right-click DC-01 (local) again and click Configure and Enable Routing and Remote Access.
