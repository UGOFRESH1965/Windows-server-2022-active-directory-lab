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
