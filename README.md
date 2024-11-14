# LinuxVmToHost

# How to Set Up a VM Server on Windows with SSH and VS Code

## Prerequisites

- A Windows machine with virtualization enabled.
- An installed VM hypervisor like **VirtualBox** or **Hyper-V** (we’ll use VirtualBox in this guide).
- **Windows Subsystem for Linux (WSL)** (if using VirtualBox for the VM setup).
- **VS Code** installed on your local machine.

## Step 1: Install VirtualBox (or Hyper-V)
- Go to the [VirtualBox Downloads](https://www.virtualbox.org/wiki/Downloads) page and install VirtualBox for Windows.
- For **Hyper-V** setup, check [Microsoft’s Hyper-V documentation](https://docs.microsoft.com/en-us/virtualization/hyper-v-on-windows/) for detailed steps.

## Step 2: Create and Set Up the VM
1. Download a **Linux distribution** ISO (like Ubuntu) for the VM. [You can Downloade Ubunto Server here.](https://ubuntu.com/download/server)
2. ![vm home screen pic]()
3.  Open **VirtualBox**, click on **New**, and follow the steps to create a new VM.
4. ![New VM]()
5. Give it a name like UbuntuDev and select your iso
6. Fill a simple to remmber password. (NOTE: we will use an rsa key so it doesnot realy matter)
7. ![Password]()
8. Adjust Hardware allocation( 2 CPU and 4096 Ram is good)
9. ![Hardware Settings]
10. Create a Virtual HD ( 200 GB is Good)
11. ![VirtualHDSize]()
12. Summary
13. ![SummaryOfVM]

## Step 3: Set Up the Machine
1. Cliekc finish and wait for the machine to boot
2. this is the window you want to see this:
3. ![LanguagePick]()
4. press Enter
5. Decline the update and continue without updating
6. ![UpdatingVM]()
7. press enter on any of these screens
8. ![KeyboardLayout]()
9. ![ServerType]()
10. ![NetworkConnections]()
11. ![ConfigureProxy]()
12. ![UbuntuArchiveMirror]()
13. ![GuidedStorgeConfiguration]()
14. Here press Done and Continue
15. ![StorgeConfiguration]()
16. Here you want to setup your server i pick test and 1-8 password
17. ![ProfileSetup]()
18. Skip upgrading to ubunto pro
19. ![UpgradeToUbuntuPro]()
20. Make sure `Install OpenSSH server` is checked
21. ![SSHSetup]()
22. Enter Until downLoad
23. ![FeaturedServerSnaps]()
24. Wait for it to install
25. ![InstallSystem]()
26. Turn off the machine

## Step 4: Set Up open ssh 
1. set up Port Forwarding from host port 2222 to VM port 22
2. machine's settings -> Network -> Advanced -> Port Forwarding
3. Create a new rule with the following credentials:
  ```
  Name: SSH
  Protocol: TCP
  Host IP: 127.0.0.1
  Host Port: 2222
  Guest IP: 10.0.2.15
  Guest Port: 22
  ```
4. ![PortForwardingRules]()
5. Boot the machine ( you can run this is a headless)
6. open cmd 
7. login to the machine 
8. ![LoginToVM]()
   
## Step 5: *optinal* Set Up auto connect via rsa 
1. find id_rsa.pub ( usely is under C:/Users/UserName/.ssh)
2. if doesent exist create with:
   ``` bash
   ssh-keygen -t rsa
   ```
3. Copy to clip board the rsa key
4. Open ~/.ssh/authorized_keys
5. Add the conntents of id_rsa.pub
6. verify the key works
7. exit and connect again, if requested any password it doesnt work 





