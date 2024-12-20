# Linux OS Administration
# Table of Contents
- [Introduction](https://github.com/itscoltonhicks/Linux-OS-Administration/blob/main/README.md#introduction)

- [Setting Up Our Linux OS Lab Environment](https://github.com/itscoltonhicks/Linux-OS-Administration/blob/main/README.md#Setting-Up-Our-Linux-OS-Lab-Environment)

- [Lab #1: Navigating a Linux GUI](https://github.com/itscoltonhicks/Linux-OS-Administration/blob/main/README.md#lab-1-navigating-a-linux-gui)

- [Lab #2: The File and Folder Structure of a Linux Operating System](https://github.com/itscoltonhicks/Linux-OS-Administration/blob/main/README.md#lab-2-the-file-and-folder-structure-of-a-linux-operating-system)
# Introduction

Cybersecurity is a subset of IT.

This is why it's important to have a strong foundation in IT systems administration. Linux OS plays a crucial role in this foundation. It's one of the most widely used operating systems in server environments, cloud infrastructures, embedded systems, IoT devices, and supercomputing. Understanding Linux OS is key for effective system administration—it helps manage and protect critical infrastructure, support end-users, and drive automation and innovation. It’s the backbone of many modern technologies and enterprises.

In this project, I'll be covering the fundamentals of Linux OS administration.

# Setting Up Our Linux OS Lab Environment

Many people like using the [Windows OS](https://github.com/itscoltonhicks/Windows-OS-Administration/blob/main/README.md) because it's built for ease. 

The Windows OS relies heavily on graphical windows and icons, which we call a Graphical User Interface (GUI). The Linux OS is different. It thrives in the Command Line Interface (CLI). 

Linux users open a terminal, enter commands, and interact directly with the operating system.

It’s efficient and powerful, but it can feel intimidating at first—like staring at a blank page with no instructions.

That's why we'll be configuring our Linux OS with a GUI called XFCE (XForms Common Environment). The XFCE graphical desktop will give us a visual representation of what's happening under the hood of Linux. It's lightweight, so it won't eat up system resources. 

This makes it the perfect place to start.

Think of it like driving a car.

A GUI is like an automatic transmission. It gets you moving. You don't need to know what's happening behind-the-scenes to hit the gas and steer. The CLI, though—that’s driving manual. 

You feel the engine. You shift the gears. You're in control.

Learning the CLI is harder at first, but it makes us more skillful Linux systems administrators. 

So we'll start with the GUI to get our bearings. We'll look at the system, poke around, and learn about the Linux architecture. But after a couple labs, we'll move to the CLI to really understand what's going on under the hood. 

We'll strip back the visuals, write commands, and drive Linux the way it was meant to be driven.

So let's get started by creating our lab environment:

1. We'll deploy a Linux Ubuntu machine in Azure Cloud.

2. Then we'll add the XFCE packages to our existing Ubuntu machine, configuring it with a desktop environment. 

Start by opening up Azure and navigating to the "Virtual Machines" service. 

<img alt="1  Create a VM" src="https://github.com/user-attachments/assets/f859d95c-a78f-488f-a148-8f7bdf8c30a7" loading="lazy">

We're going to create an Ubuntu Virtual Machine (VM). 

Ubuntu is a Linux distribution made from a software collection that includes the Linux kernel. You can think of it as a flavor of Linux. And there are many flavors out there. 

Give the VM a name, resource group, and select Ubuntu version 20.04. 

<img width="741" alt="2  Create a ubuntu server" src="https://github.com/user-attachments/assets/58c1d765-3a2e-49b8-9168-5bc125672bf3" loading="lazy"/>

Then we'll select the VM size and create credentials for the administrator account type. 

I like to have 2 vCPUs for performance. Then I'll give it a username and password.

<img width="732" alt="3  Add VM size and credentials" src="https://github.com/user-attachments/assets/0022d26b-1444-4d82-9aaf-8ee4a2b64e4b" loading="lazy"/>

I'll choose a standard HHD disk since this is a lab environment.

<img width="731" alt="4  Standard HHD disk" src="https://github.com/user-attachments/assets/ee9e5f38-189e-4ca1-9828-7e3fc420bb67" loading="lazy"/>

Add the Linux VM to a virtual network.

Then we can review and create the machine at this point.

<img width="732" alt="5  Add vnet for linux vm" src="https://github.com/user-attachments/assets/5d8f1134-04d7-454a-af49-1278b97185d3" loading="lazy"/>

Now we have our Linux Ubuntu VM. 

<img width="900" alt="6  Linux VM created" src="https://github.com/user-attachments/assets/5a7a78e1-eb26-4371-8fbf-392e5e7eb471" loading="lazy"/>

But this only gives us the CLI. We still need to add the XFCE graphical desktop to it, so we'll want to remotely access our Linux VM and add the XFCE packages to it. [I used Microsoft's learning resources to set this up.](https://learn.microsoft.com/en-us/azure/virtual-machines/linux/use-remote-desktop?tabs=azure-cli)

We can access our terminal by using the ```ssh``` protocol.

```
ssh <username>@<IP Address>
```

Provide the password once prompted.

<img width="600" alt="7  ssh into linux" src="https://github.com/user-attachments/assets/62b85504-792d-4729-85b1-6c46c1a3f320" loading="lazy"/>

Now we've accessed our Linux VM. 

The first command we'll do is check for the latest updates for all the software on the system. It ensures our system is running smoothly and securely. 

```
sudo apt-get update
```

<img width="597" alt="8  sudo apt-get update" src="https://github.com/user-attachments/assets/e4306351-04ff-4984-bba2-ab972da1e793" loading="lazy"/>

Next we'll install the XFCE desktop environment on our Linux system:

```
sudo DEBIAN_FRONTEND=noninteractive apt-get -y install xfce4
```

This will take a few minutes to install. We'll see a series of messages that indicate the progress of the installation process.

<img width="800" alt="9  add xfce packages" src="https://github.com/user-attachments/assets/351338a0-4504-413f-81cb-de3b6038c126" loading="lazy"/>

Now we'll install the XFCE session manager on our Linux system. 

The session manager is a crucial part of the XFCE desktop environment. It allows us to manage our desktop sessions—such as logging in, logging out, and saving our settings.

```
sudo apt install xfce4-session
```

<img width="800" alt="10  install xfce" src="https://github.com/user-attachments/assets/be6f1853-c637-492c-9d22-623635d611bf" loading="lazy"/>

At this point, we want to install the ```xrdp``` package on our Linux system. 

This basically lets us use Remote Desktop Protocol (RDP) to access our Linux machine.

```
sudo apt-get -y install xrdp
```

<img width="800" alt="11  sudo apt-get -y install xrdp" src="https://github.com/user-attachments/assets/834ed010-d254-47e2-8eb2-fbc0f016021d" loading="lazy"/>

Now to make sure the ```xrdp``` service works properly, we want to make sure it's enabled whenever our Linux VM is running. 

This makes our Linux VM ready to be accessed remotely whenever the machine is turned on.

```
sudo systemctl enable xrdp
```

<img width="944" alt="12  sudo systemctl enable xrdp" src="https://github.com/user-attachments/assets/0a54de2b-4bdd-452d-b2d1-c42c09ee3eba" loading="lazy"/>

In Ubuntu 20.04, which is the version I'm using, we need to add the ```xrdp``` user to the ```ssl-cert``` group due to the way SSL certificates are handled by default.

This is a specific configuration requirement to allow the ```xrdp``` service to access the necessary SSL certificates for secure connections.

```
sudo adduser xrdp ssl-cert
```

<img width="800" alt="13  sudo adduser xrdp ssl-cert" src="https://github.com/user-attachments/assets/5b518904-c3d1-465e-a03c-8b4eeb05fdd2" loading="lazy"/>

Then we'll make sure that every time we connect to our machine via remote desktop, the XFCE desktop environment will be used.

```
echo xfce4-session >~/.xsession
```

Finally we'll restart the ```xrdp``` service to apply all the changes we made.

```
sudo systemctl restart xrdp
```

<img width="800" alt="14  echo xfce session and system restart" src="https://github.com/user-attachments/assets/9662eed8-828d-439c-b946-e6b669172cbe" loading="lazy"/>

Since we'll start accessing our Linux machine through remote desktop, we need to allow traffic through port 3389.

Port 3389 is the default port for Remote Desktop Protocol (RDP). So I'll go to my Network Security Group (NSG) in Azure and add an inbound port rule. NSGs are basically cloud firewalls in Azure. 

<img width="939" alt="15  inbound port rule for linux vm" src="https://github.com/user-attachments/assets/76b610cf-9e4f-460b-b272-d76a1d25efea" loading="lazy"/>

I misconfigured it the first time by accident, so ignore the "8080Inbound" naming convention for the new rule. Unfortunately we can't change names once it's set.

Now we'll use our Remote Desktop client to access the machine. 

<img width="302" alt="16  rdp" src="https://github.com/user-attachments/assets/f72fb602-c841-4dec-860c-d35d5184964e" loading="lazy"/>

We'll get sent to a login page where we can input our username and password.

<img width="502" alt="17  log into linux vm" src="https://github.com/user-attachments/assets/7c62395a-319f-4ab8-9a0e-9b70fd13480c" loading="lazy"/>

And just like that, we have the XFCE graphical desktop set for our Linux Ubuntu VM.

<img alt="18  xfce view" src="https://github.com/user-attachments/assets/78c7beb5-b7e4-4742-b617-20355e1788a0" loading="lazy"/>

# Lab #1: Navigating a Linux GUI

Linux desktop environments vary in their design, features, and customization options.

We'll look at the XFCE variant. The XForms Common Environment is a lightweight software for the graphical desktop. But it's also visually appealing and user friendly. This makes it a great GUI for our Linux environment.

Start up our Linux workstation.

We'll bring our mouse cursor to the top left of the desktop to the "Applications" dropdown menu along the taskbar. Notice how this is where we can find applications and other software.

<img width="750" alt="1  Applications View" src="https://github.com/user-attachments/assets/4aab30ba-9626-4dad-806e-48d43d462a5c" loading="lazy"/>

Click the "File Manager" option. This is where we can find common folder locations our user account can access. This is similar to what we've seen with the [Windows OS.](https://github.com/itscoltonhicks/Windows-OS-Administration)

<img width="482" alt="2  File Manager" src="https://github.com/user-attachments/assets/6e9539f4-e38a-4536-bba4-d94b71a9bd25" loading="lazy"/>

We can click around the left pane to navigate to different locations. We can also click the "view" tab and select different options to change our view preferences.  

<img width="441" alt="3  Manage file explorer preferences" src="https://github.com/user-attachments/assets/54ec39c8-4163-4f73-92ca-75a63061a991" loading="lazy"/>

We can use the ```CTRL+F``` command or ```F3``` in the File Explorer to reveal a search function to find files and folders.

<img width="439" alt="4  Find function in file explorer" src="https://github.com/user-attachments/assets/a7b42d13-df6e-45a9-9794-029484ab5982" loading="lazy"/>

Close the File Explorer now with the X button at the top right to close the window, again very similar to the Windows OS.

Now navigate to the system settings which can be found along the task bar in ```Applications > Settings > Settings Manager```.

<img width="626" alt="6  Settings Manager" src="https://github.com/user-attachments/assets/2d3beb46-270d-4fc4-aa1a-b5853ccdfa14" loading="lazy"/>

This is where we can change things like display options, backgrounds, notifications, and other system settings.

At this point, let's look at how to find an application beyond just using the "Application" dropdown menu. 

We can click the search icon at the bottom of the desktop. A window will pop up, and we can search any application that exists on our system. For instance, I can find the Firefox Web Browser by searching for it.

<img width="786" alt="7  Application finder" src="https://github.com/user-attachments/assets/dc467ff1-89f7-429c-8a93-a6442752fe9a" loading="lazy"/>

It's also important to know how to interact with folders and files on the Linux GUI. 

Open up the "Home" folder and navigate to the "Desktop" folder. Once there, let's right-click the empty space and create a new folder.

<img width="600" alt="8  Create a folder" src="https://github.com/user-attachments/assets/a920393b-bfea-4a67-92a9-a72a403a6418" loading="lazy"/>

A new folder will appear on our desktop view, since the "Desktop" folder is just a representation of what we're seeing on the desktop itself.

<img width="600" alt="9  Creating a TestFolder" src="https://github.com/user-attachments/assets/9433ac26-1d4e-4720-9c3c-596b3c8c531b" loading="lazy"/>

If we right-click the folder and select "Properties," we'll see a couple tabs containing details about the folder.

The "General" tab tells us it's a folder and where it's located on disk.

<img width="609" alt="10  General tab for folders" src="https://github.com/user-attachments/assets/e4c36ec7-e05e-4db1-8453-c0c84abafc95" loading="lazy"/>

The "Emblems" tab allows us to add icons to organize or label our folders. 

<img width="610" alt="11  Emblems tab for folders" src="https://github.com/user-attachments/assets/8335caa0-a3e0-496d-9627-0703db26f5da" loading="lazy"/>

And the "Permissions" tab shows us who has access to the folder, and the level of access provided.

<img width="616" alt="12  Permissions tab for folders" src="https://github.com/user-attachments/assets/c4893659-2735-4f04-bd7a-1cb572bf5ae0" loading="lazy"/>

Next, let's create a file inside our new ```TestFolder```. Go to the directory, right-click the empty space, and create an empty file. 

<img width="600" alt="13  Create file in linux" src="https://github.com/user-attachments/assets/2e6cd8f8-9353-456c-8f72-245d8b996d69" loading="lazy"/>

You'll be prompted to give it a name. I'll name mine ```TestFile```.

We can double-click the file to open it. Add text. And save it.

<img width="550" alt="14  Newly saved test file" src="https://github.com/user-attachments/assets/278f97d1-2a70-4ee6-923a-8caf0641fa91" loading="lazy"/>

Now when we want to delete folders or files, we can right-click it and choose "Move to Trash." 

<img width="550" alt="15  Move folder to trash" src="https://github.com/user-attachments/assets/c9aac3f1-e804-4348-8431-2c8da1cd29e6" loading="lazy"/>

Next select the "Trash" location in the left pane to see where our deleted files go for restoration or permanent deletion.

Then just like in Windows, we can permanently delete folders and files.

<img width="602" alt="16  Delete folders in trash bin" src="https://github.com/user-attachments/assets/d8c01eab-317d-4cd9-92d2-cd5e061f370a" loading="lazy"/>

# Lab #2: The File and Folder Structure of a Linux Operating System

In Linux, everything is a file. 

So it's worth understanding how the file and folder structure works. And it all starts in the root directory, denoted by the ```/``` character. The root directory is the top-level directory in a Linux filesystem. All other directories branch off from here.

We can view the root directory within the file explorer window.

<img width="539" alt="1  View of linux filesystem" src="https://github.com/user-attachments/assets/d9650776-7eca-4be2-a7e6-e4be90e078e9" loading="lazy"/>

Here we'll see all our directories listed.

Let's briefly cover some common ones:

- ```/bin```: Contains essential user command binaries (or programs). These are basic commands needed to operate the system. 
- ```/etc```: Stores system-wide configuration files and shell scripts used to boot and initialize the system. Key configuration files like ```/etc/passwd``` and ```/etc/fstab``` are located here.
- ```/sbin```: Contain essential system binaries. These commands are crucial for system administration.
- ```/usr```: Contains user utilities and applications. It holds the majority of the system's software.
- ```/var```: Contains variable data files like logs, databases, and spool files. This is useful when investigating event logs. 
- ```/dev```: Contains device files. This provides an interface to interact with hardware devices.
- ```/home```: Contains personal directories for all users. For example, ```/home/Colton``` is my home directory.
- ```/lib```: Holds essential shared libraries and kernel modules needed to boot the system and run basic commands. These libraries are important for system functionality.
- ```/mnt```: Temporarily mounts filesystems or external devices. It's often used for maintenance tasks. 
- ```/opt```: Used for installing optional software packages. Software not included by default in the system might be installed here. 
- ```/proc```: Provides information about system processes. It allows us to look under the hood of our system and see how it's operating.  
- ```/root```: Home directory for the root user (different from the root directory). This is the folder for the system administrator account and requires privileged access.

That's a lot of information.

So let's walk through a few of these in our Linux environment. 

We'll begin in the ```/home``` folder.

If we go down the file system, we'll see the ```Colton``` user. Inside that user's home folder we'll find all the sub-folders nested within it.

<img width="541" alt="2  User home folder" src="https://github.com/user-attachments/assets/58937bbf-b4f8-4ba9-94d4-f33f91803220" loading="lazy"/>

Now let's go back to the root directory by going up the file system.

Notice how the ```/root``` directory has a big "X" on it. 

<img width="540" alt="3  Root user folder" src="https://github.com/user-attachments/assets/2e7d0555-d997-4b3e-b709-6161f6b82205" loading="lazy"/>

This is because it's protected and requires heightened privileges. Remember, this is the home directory for the system administrator.

Finally, let's look at the ```/proc``` folder.

All these folders contain information for a given process with a Process ID (PID).

<img width="540" alt="4  proc folder in linux" src="https://github.com/user-attachments/assets/fd0fe456-186f-4f86-9c2a-54213eb91944" loading="lazy"/>

These files and directories aren't actually on the disk. They only exist in memory. And they're generated dynamically based on what's happening in our system. So they'll start up and disappear as the operating system is in use. 

For example, the ```uptime``` file will give us information on the current uptime on the operating system.

<img width="537" alt="5  uptime file in proc directory" src="https://github.com/user-attachments/assets/d7b8fcaa-ecb1-4f09-b2f5-9c361aa345ba" loading="lazy"/>

Notice a key difference between Linux and Windows. Linux doesn't use a registry like Windows but stores everything in a basic file to be recalled and worked with as needed at any time.
