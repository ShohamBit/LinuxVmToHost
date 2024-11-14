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
7. If shown keyboadlayout just press enter
8. ![KeyboardLayout]
9. 
