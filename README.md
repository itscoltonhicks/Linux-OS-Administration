# Linux OS Administration
# Table of Contents
- [Introduction](https://github.com/itscoltonhicks/Linux-OS-Administration/blob/main/README.md#introduction)

- [Setting Up Our Linux OS Lab Environment](https://github.com/itscoltonhicks/Linux-OS-Administration/blob/main/README.md#Setting-Up-Our-Linux-OS-Lab-Environment)

- [Lab #1: Navigating a Linux GUI](https://github.com/itscoltonhicks/Linux-OS-Administration/blob/main/README.md#lab-1-navigating-a-linux-gui)

- [Lab #2: The File and Folder Structure of a Linux Operating System](https://github.com/itscoltonhicks/Linux-OS-Administration/blob/main/README.md#lab-2-the-file-and-folder-structure-of-a-linux-operating-system)

- [Lab #3: Monitor Running Processes With a Linux GUI](https://github.com/itscoltonhicks/Linux-OS-Administration/blob/main/README.md#lab-3-monitor-running-processes-with-linux-gui-tools)

- [Lab #4: Viewing System Logs With a GUI](https://github.com/itscoltonhicks/Linux-OS-Administration/blob/main/README.md#lab-4-viewing-system-logs-with-a-gui)

- [Lab #5: The Basics of Operating the Terminal](https://github.com/itscoltonhicks/Linux-OS-Administration/blob/main/README.md#lab-5-the-basics-of-operating-the-terminal)

- [Lab #6: Introductory Commands for Navigating the Linux Terminal](https://github.com/itscoltonhicks/Linux-OS-Administration/blob/main/README.md#lab-6-introductory-commands-for-navigating-the-linux-terminal)

- [Lab #7: Understanding Linux Flags, Tab Autocompletion, and Path Types](https://github.com/itscoltonhicks/Linux-OS-Administration/blob/main/README.md#lab-7-understanding-linux-flags-tab-autocompletion-and-path-types)

- [Lab #8: Linux File Administration on the Command Line](https://github.com/itscoltonhicks/Linux-OS-Administration/blob/main/README.md#lab-8-linux-file-administration-on-the-command-line)

- [Lab #9: File Permissions on the Command Line](https://github.com/itscoltonhicks/Linux-OS-Administration/blob/main/README.md#lab-9-file-permissions-on-the-command-line)
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

# Lab #3: Monitor Running Processes With Linux GUI Tools

Sometimes a process is slowing things down or causing issues on a system. 

Whenever that happens, we'll want to investigate system processes. This'll allow us to restore systems back to normal use. In this lab, we'll do this with GNOME System Monitor and XFCE Task Manager. 

They're GUI tools that help us monitor running processes on our system. 

To get started, we can find it located under "Systems."

<img width="384" alt="1  Open system monitor" src="https://github.com/user-attachments/assets/12ef1f29-7267-4841-a66f-55fc8ae83d9d" loading="lazy"/>

The System Monitor window will pop up and put us in the "Processes" tab by default.

Here we'll see the many processes currently running on our system and accompanying details—process name, which user is the owner, CPU & memory usage, Process ID, etc.

<img width="567" alt="2  Processes tab in system monitor" src="https://github.com/user-attachments/assets/4453b239-452b-43e6-9058-a6cfc4ac3e80" loading="lazy"/>

Next we can view the "Resources" tab to get a high-level overview of what's going on.

This displays graphical charts representing system resources being used over time. 

<img width="567" alt="3  Resources tab in system monitor" src="https://github.com/user-attachments/assets/991446a9-e2f3-4252-b961-f791296f3939" loading="lazy"/>

Finally, the "File Systems" tab gives us a snapshot of the attached disks and storages in use.

<img width="569" alt="4  File Systems tab in system monitor" src="https://github.com/user-attachments/assets/dd72f3a2-477a-4338-9b83-19a917a4cc0a" loading="lazy"/>

At this point, let's interact with processes through the System Monitor. 

Dock the System Monitor to the right half of the desktop. Now let's open Text Editor to see what happens in the System Monitor. 

We'll see a ```gedit``` process appear.

<img width="775" alt="5  gedit process in system monitor" src="https://github.com/user-attachments/assets/3b7672b2-c356-40d0-b752-113ca88d3db8" loading="lazy"/>

This is the process name for the text editor. It's important to know that binary executable files have different names under the hood than the name of the application running itself.

If we want to view more details about the process, we can right-click it and select "Properties."

<img width="675" alt="6  gedit process properties" src="https://github.com/user-attachments/assets/a2abe271-9800-4f0e-9639-4fb443676cbc" loading="lazy"/>

Now we'll walk through "stopping" and "killing" a process.

Someone may casually say to "stop" a process. And what they're actually saying is to end or kill the task. But technically, stopping a process is just pausing it (kind of like freezing a video). We can illustrate that by first right-clicking the ```gedit``` process and selecting "Stop."

A window will pop up asking if we're sure that we want to stop it. Click "Stop Process."

<img width="750" alt="7  stop gedit process" src="https://github.com/user-attachments/assets/3407e972-fa77-4888-a71d-0780a8a4d788" loading="lazy"/>

Try typing inside the text editor window and notice how nothing appears. 

That being said, the process is still receiving input. We can illustrate this by right-clicking the ```gedit``` process again and selecting "Continue." This effectively wakes up the process.

<img width="750" alt="8  continue gedit process" src="https://github.com/user-attachments/assets/630f9067-f8db-420c-8810-62ebfe93eb65" loading="lazy"/>

All the character keys we hit while it was stopped will now load and appear into the process.

<img width="800" alt="9  secret text appears for gedit process" src="https://github.com/user-attachments/assets/30623327-7c40-47b8-b5f2-4b0a86147211" loading="lazy"/>

We can apply the same principle to ending the task. 

Stop the ```gedit``` process again. Then try to "End Process" or kill it. 

<img width="650" alt="10  End process" src="https://github.com/user-attachments/assets/7a9e11bc-1263-4444-a456-79f9b0dc18f1" loading="lazy"/>

We'll notice how the text editor stays open. But when we "continue" the ```gedit``` process, the task will get terminated.

Understanding how processes work is important for system administrators and security professionals. 

If an application freezes or behaves unexpectedly, pausing or killing a process may resolve the issue. And some processes may consume too much CPU or memory. So knowing how to stop or kill these processes helps optimize system performance.

Not to mention, in the case of a security incident, we can stop or kill harmful processes before it compromises the system further.

Let's wrap up this section by using the XFCE Task Manager tool.

It's a simplified version of System Monitor. But it has a unique feature. Processes will get highlighted different colors based on changes in the system. With clear visual indicators of process states, it becomes easier to monitor system changes in real-time.

Let's illustrate this.

We can find it under ```Applications > Accessories > Task Manager```.

<img width="365" alt="11  Task manager in linux" src="https://github.com/user-attachments/assets/759ebb06-82d9-4041-9d1b-406e4f45dcfb" loading="lazy"/>

The view is similar to System Monitor, yet simplified.

<img width="640" alt="12  Task manager view in linux" src="https://github.com/user-attachments/assets/38557a2d-55bc-47ee-bda4-0fd59b0ace6f" loading="lazy"/>

Now let's open up text editor and see what happens.

<img width="768" alt="13  Gedit process highlighted in green" src="https://github.com/user-attachments/assets/cb7602a9-95dc-43fe-a414-5d00a83dd5b4" loading="lazy"/>

As the new ```gedit``` process starts, we see it appear highlighted in green. 

Once the Task Manager has stabilized, let's close the text editor.

<img width="795" alt="14  gedit process highlighted in red" src="https://github.com/user-attachments/assets/3e10bbfa-5c01-42f6-9b24-f76b7d67165b" loading="lazy"/>

Notice how the ```gedit``` process gets highlighted red. 

This shows us that the task is getting terminated, and it'll eventually disappear from the Task Manager view.

# Lab #4: Viewing System Logs With a GUI

System logs in Linux are plain text files that record events, actions, and messages from different parts of our computer. 

These logs are important because they help us:

- **Solve problems:** They help us figure out why something isn't working (e.g. when an application crashes). 
- **Monitor security:** They reveal suspicious activity.
- **Track changes:** They show us who made changes to the system and when.

In later section, we'll explore logs in the CLI. 

But for now we'll use the GNOME Logs GUI to get a feel for them. Let's open it up under ```Applications > System > Logs```. A window will pop up displaying logs in four different categories.

<img width="687" alt="1  GNOME Logs gui" src="https://github.com/user-attachments/assets/707a0a78-4af3-4f18-a498-80267c397254" loading="lazy"/>

Here's a brief description of each: 

- **Application Logs**: Records activity fro software applications like web browsers or text editors.
- **System Logs**: Includes messages from the kernel, boot logs, and background services (daemons). 
- **Security Logs**: Shows login attempts, authentication failures, firewall activity, and other security-related events.
- **Hardware Logs**: Monitor events related to hardware like hard drives or memory. 

We can search for logs by clicking the magnifying glass icon at the top.

Let's search for activities related to the ```gedit``` process. We'll see a list of logs. 

Then we can click one to view the details.

<img width="684" alt="2  Gedit process in logs" src="https://github.com/user-attachments/assets/872c457c-1d4d-48b2-82db-6ff2b6bb1b6c" loading="lazy"/>

Here's a quick breakdown of what we're seeing:

- **Sender**: This indicates the source or origin of the log message. In this case, the log comes from the system component ```dbus-daemon```.
- **Time**: This shows the date and time when the event occurred (and the log created).
- **Message**: This contains details about the event. For instance, we can see the User ID (UID) and Process ID (PID). We also see that we successfully activated the service.
- **Audit Session**: This refers to a session that is being monitored for security-related events. The number 2 means this is the second such session recorded.
- **Priority**: This indicates the severity or importance of the log message. In our example, a priority of 6 tells us that this is an informational message. 

# Lab #5: The Basics Of Operating the Terminal

The terminal is a command line interface in Linux.

It allows us to type text-based commands to interact with the operating system. It's like the control center for our Linux computer. While GUIs let us point and click, the terminal gives us precise control over everything our system can do. 

It's extremely important for system administrators and cybersecurity practitioners. 

Mastering the terminal helps us in a couple ways:

- We can perform tasks faster with commands compared to clicking through menus.
- We can do things that GUIs can't, like scripting repetitive tasks or accessing advanced system functions.
- We'll understand how Linux works at its core, improving our problem-solving and troubleshooting skills.

In this short lab, we'll get introduced to the terminal. 

Open a terminal under Applications. Or we can use the ```Ctrl + Alt + T``` shortcut to open one.

<img width="424" alt="1  Linux terminal" src="https://github.com/user-attachments/assets/ed70ce63-c85c-4c0b-a3a1-f53738196fdd" loading="lazy"/>

We can create multiple terminals in separate tabs, similar to having multiple tabs open in a single web browser window. Just click ```File > New Tab```.

<img width="425" alt="2  Two terminal tabs in a single window" src="https://github.com/user-attachments/assets/7058d7a1-5f46-47a4-8771-0204af9ca9a9" loading="lazy"/>

Or we can detach them into separate windows, docking them side-by-side. Just right-click a tab and select "Detach Terminal."

<img width="900" alt="3  two docked terminals" src="https://github.com/user-attachments/assets/e72e5126-b94d-4de0-8d43-73b46b715748" loading="lazy"/>

Having multiple terminals open is useful when comparing outputs for different commands. 

Now let's enter the ```exit``` command to terminate one of them. 

<img width="900" alt="4  exit command" src="https://github.com/user-attachments/assets/61ca1d76-a3c8-4730-96e2-70d9bd33df75" loading="lazy"/>

This is enough to introduce us to the terminal.

For our future labs, we'll mostly use the command line.

# Lab #6: Introductory Commands for Navigating the Linux Terminal

Using a terminal is like learning how to drive a manual car—it puts you in direct control and requires precision. 

A graphical user interface (GUI), much like an automatic car, is easier to use. The downside to a GUI is it offers less granular control over the underlying processes. This is why we need to learn how to use the terminal. But just like driving a manual car, mastering the command line comes from getting behind the wheel and taking it out for a spin.  

So in this lab, we'll start using basic commands to get a feel for how it works. We'll focus on orienting ourselves around a couple key Linux principles when using the terminal:

- **Who we are:** We need to understand which user account we're currently using to access the system.
- **Where we are:** We need to understand where we're accessing the terminal on disk.
- **What we're trying to do:** We need to understand what we're trying to accomplish on the system.

Commands are like instructions. And the CLI responds with outputs based on what we've asked it to do.

For example, if we open up a terminal, we can use the ```whoami``` command to get the current logged-in user account name.

<img width="372" alt="1  whoami command" src="https://github.com/user-attachments/assets/461e8cf0-46ab-4dcf-aedb-143821002c4a" loading="lazy"/>

When we type that command into the terminal, we're instructing the operating system to perform a specific action. 

In this case, we're asking for the current logged-in user account name. And the operating system responds with the name of the current user. The ```Colton``` username is dynamically retrieved and displayed based on the active user session, linking command prompt identity with system log user identification.

Next let's run the ```groups``` command to see which groups our user account belongs to.

<img width="512" alt="2  groups command" src="https://github.com/user-attachments/assets/f7943da0-e0b3-4db8-86eb-6e83b1ec8de0" loading="lazy"/>

The output of ```groups``` is separated by spaces which act like columned results.

We see the "sudo" group listed, among others. This signifies the user's membership in a system administrator group. And this grants our user with potential elevated permissions for system changes. 

Now let's run the ```id``` command to view the ID values of the groups we belong to.

<img width="628" alt="3  id command" src="https://github.com/user-attachments/assets/b69ae899-e677-4a11-a3c8-b465104742b4" loading="lazy"/>

We should recognize some ID values here. For example, we'll see 1000 as our User ID (UID), which we saw in the GNOME Logs tool a couple labs ago. 

Next let's use the ```pwd``` command to "print working directory". 

It'll show us the exact directory path within the computer's file system that the terminal is currently working from. 

<img width="626" alt="4  pwd command" src="https://github.com/user-attachments/assets/b6da1aba-83f2-41a1-b88d-cd1e5f88aa56" loading="lazy"/>

So we're currently operating this terminal within the ```/home/Colton``` directory.

Every command we run starts from the current user and the current directory location on disk. If we want to run commands somewhere else or as someone else, we'd need to indicate it—either change the directory, switch users, or specify a different path. 

Commands execute actions based on where we are, unless we specify otherwise.

To illustrate this point further, we can run the ```ls``` command to "list" the files and folders of the current directory.

<img width="627" alt="5  ls command" src="https://github.com/user-attachments/assets/50d79bc2-cc89-4c9f-b5f6-5514deccf68a" loading="lazy"/>

Notice how we only see folders within the ```/home/Colton``` directory. That's where the terminal is currently being accessed on disk.

If we wanted to change our current working directory in the terminal, we can use the ```cd``` command to go somewhere else.

Let's ```cd``` into the ```Desktop``` folder.

<img width="628" alt="6  cd command" src="https://github.com/user-attachments/assets/cab39963-9f07-4494-af4f-50ad110bca56" loading="lazy"/>

Now every command we enter, by default, will execute from the ```/home/Colton/Desktop``` directory. We can confirm this by using the ```ls``` command. We don't have any files or folders in the ```Desktop``` folder, so we won't receive any output.

<img width="626" alt="7  ls within empty directory" src="https://github.com/user-attachments/assets/fca315fe-39ce-4ba7-ac2c-2916a5e531e5" loading="lazy"/>

At this point let's clean up the command by entering ```clear```. We'll have a clear terminal for future commands now. 

So what if I wanted to change directories back up one folder? We can use the ```cd ..``` command to do this. The ```..``` specifies that we want to go back up one folder.

<img width="340" alt="8  cd   command" src="https://github.com/user-attachments/assets/11e87318-3245-48d1-9dfe-b727feb1971a" loading="lazy"/>

Now we're back in the ```/home/Colton``` directory.

Next we'll cover how to access the "manual pages." 

They're comprehensive guides for different commands on our Linux machine. They explain what each command does and how to use it. If we run into issues, we can check the manual pages to find solutions and understand what went wrong. We can also use it to expand our knowledge and skills around a specific command.

For example, we can run the ```man ls``` command to get the manual pages for the ```ls``` command. 

<img width="628" alt="9  man ls command" src="https://github.com/user-attachments/assets/f8d8f509-541e-4705-971f-d1e816decc8a" loading="lazy"/>

Notice how it provides descriptions for the command, the various ways we can use it, and how to format it.

Exit the man pages by hitting the ```q``` key.

Now if we don't want a comprehensive manual page for a command, we can use the ```whatis``` command to get a quick description for what a command does.

<img width="343" alt="10  whatis ls command" src="https://github.com/user-attachments/assets/c766c6a3-4984-4492-9ea5-74732b10989c" loading="lazy"/>

Great. We covered the basics of using the terminal.

In the next section, we'll continue adding layers of complexity. 

# Lab #7: Understanding Linux Flags, Tab Autocompletion, and Path Types

Using commands aren't always straightforward—they often come with flags or options that modify their behavior.

Flags or options tweak how commands behave. They perform advanced or more specified nuances of the command. They're usually attached with a tack or hyphen (```-```). And multiple flags can typically be combined together for specific outputs. 

They ultimately help us navigate Linux systems more efficiently.

If we open up a terminal and look at the manual page for the ```ls``` command, we can observe different flags.

<img width="550" alt="1  man ls command to display flags" src="https://github.com/user-attachments/assets/58e0de21-0e2a-4660-af7d-e0c4347bcada" loading="lazy"/>

```-a``` is a common flag that gets used with the ```ls``` command. It lists all files and directories, including hidden ones.

We can search within the man pages by hitting the ```/``` key and start typing. Once we press "enter," we'll see all the entries that match our search.

I'll search for ```-l```, which provides a "long listing format." It gives us detailed information for files and directories.

<img width="475" alt="2  search for -l flag in man pages" src="https://github.com/user-attachments/assets/4f8df57d-f492-4559-a97f-73b158fb4f00" loading="lazy"/>

Exit the man pages.

Now let's run a command with and without flags to observe the difference. We'll start with ```ls -a```. 

<img width="900" alt="3  ls -a command" src="https://github.com/user-attachments/assets/f68c97f7-45d5-46d6-bf88-e8fd58d30f17" loading="lazy"/>

Notice the difference between the two outputs. The output for the ```-a``` flag will display files and directories with a ```.``` before it. These are hidden with the standalone ```ls``` command.

Next I'll run another ```ls``` command with the flags ```-al```. This combines ```-a``` and ```-l``` together.

<img width="500" alt="4  ls -al command" src="https://github.com/user-attachments/assets/bf5372f3-bf5c-4392-a08a-d7242b501c13" loading="lazy"/>

We'll get additional information like permissions, file and folder sizes, and time stamps. 

And we can keep doing this to modify the output. For example, we can tack on the ```-h``` flag to make the file sizes "human-readable." 

<img width="445" alt="5  ls -alh command" src="https://github.com/user-attachments/assets/677d5542-7f48-452d-9f23-0ef98f1dfc32" loading="lazy"/>

Let's clear the terminal.

Next we'll cover the concept of tab autocompletion. 

This is a feature in the command line that automatically completes the command or file name we're typing. We just start typing, then hit the "Tab" key on our keyboard. It's important because it saves us time and reduces errors.

Let's illustrate this with the ```ls``` command.

I'll start typing the ```Documents``` folder to list the files and directories in it. But I'll only input a couple characters. Then I'll press "Tab" to autocomplete it.

<img width="712" alt="6  Tab autocompletion part 1" src="https://github.com/user-attachments/assets/223d0311-2f75-437d-b83b-7fc80f0c6aa4" loading="lazy"/>

AT this point, we should see a couple different options being outputted. This is because two folders start with ```Do``` for their directory name and couldn't complete the tab autocompletion.

Let's try again, but this time try to autocomplete after typing in ```./Doc```.

<img width="711" alt="7  Tab autocompletion part 2" src="https://github.com/user-attachments/assets/f60b6518-283c-4dce-be47-3dba08cd05dc" loading="lazy"/>

Great. It autocompletes for us.

At this point, it's important to cover the difference between relative and absolute paths in Linux. A relative path runs commands based to our current location in the filesystem. On the other hand, an absolute path runs commands based to the root directory, giving the full path from the root.

I'll create a new folder using the ```mkdir``` command so we can illustrate this concept. 

<img width="506" alt="8  mkdir command for testfolder" src="https://github.com/user-attachments/assets/fcfb2c43-3206-41c0-a526-a2f26e78333c" loading="lazy"/>

So let's say we want to change directories into our new ```testfolder```. 

We can do this using its relative path. Remember, by default the terminal will execute commands for our current working directory. So we can simply use the ```cd testfolder/``` command to change directories.

<img width="526" alt="9  cd into testfolder relative path" src="https://github.com/user-attachments/assets/95a5ae8c-2f3c-4b1f-8c8c-0b7278853eec" loading="lazy"/>

There's another way to use its relative path.

We can put ```./``` before the folder's name. This is the relative representation for "here." 

<img width="525" alt="10  cd into testfolder with relative path part 2" src="https://github.com/user-attachments/assets/a4f0c419-005a-45ae-95a8-758da52d3d5a" loading="lazy"/>

Notice how we achieved the same thing. 

But let's say we try to change directories with just the ```/```. 

<img width="513" alt="11  cd with no directory or file showing" src="https://github.com/user-attachments/assets/c0dc8fb6-1df5-43b8-aa84-1a1efa74841b" loading="lazy"/>

We get a message saying the file or directory doesn't exist. 

This is because we're using just the forward slash ```/```. This actually represent the root directory. And we're referencing the root directory, then we'd need to provide the full directory path or the absolute path.

For example, if we use ```pwd``` from our ```testfolder``` directory, we'll see the full directory path on disk. 

<img width="529" alt="12  pwd to get absolute path" src="https://github.com/user-attachments/assets/8fa76f75-f0b0-4671-8bcc-5ffc96fb38b2" loading="lazy"/>

Now if we go back up a directory and try to ```cd``` again with the absolute path, it'll work properly.

<img width="533" alt="13  cd with absolute path" src="https://github.com/user-attachments/assets/3d2edbd2-5aa4-40a5-8055-8383edddd61c" loading="lazy"/>

Understanding the distinction between relative and absolute paths will be very helpful for navigating the filesystem.

That being said, using absolute paths can be a pain to navigate around. So a useful command we can use is ```cd ~```.

The ```~``` key will take us back to our home directory, which is basically our own dedicated space on the system.

<img width="514" alt="14  cd to home directory with shortcut" src="https://github.com/user-attachments/assets/f3f3c0a5-41b5-4bed-af2f-3d46f997b349" loading="lazy"/>

# Lab #8: Linux File Administration on the Command Line

Managing files on the Linux command line is an imporant skill for IT system administrators and cybersecurity professionals. 

Everything in Linux is a file. So mastering file administration allows us to efficiently handle configurations, logs, and data. And this is useful when we're troubleshooting, managing users, or doing any essential task that keeps our systems running smoothly and securely.

In this lab, we'll cover the basics of file administration on the command line.

Start by opening up a terminal and navigate to the ```Desktop``` directory. We'll create a new folder here to illustrate the subsequent file administration tasks.

<img width="575" alt="1  Make testfolder in desktop directory" src="https://github.com/user-attachments/assets/330c6200-9d02-4d6f-b4f6-fd418ef1a196" loading="lazy"/>

Let's change directories into our new folder.

Now we'll use a new command called ```touch```.

The primary purpose of this command is to change file stamps. However, when we use the ```touch``` command with a file name that doesn't already exist in the directory, the command will create an empty file with that name. And we can use it as a shortcut for creating a new empty file.

<img width="537" alt="2  man pages for touch" src="https://github.com/user-attachments/assets/9c0993fd-2524-47fc-a553-2c52b03ac28b" loading="lazy"/>

So let's create a new file with the ```touch``` command.

<img width="849" alt="3  create new file using touch command" src="https://github.com/user-attachments/assets/e956e737-41e4-42e7-83a6-6ad5288c0f47" loading="lazy"/>

Great. Now that we've created a new file, let's add some text to it. 

We'll do this with the following command:

```
echo "Hello" > testfile
```

Quick command breakdown:
- ```echo "Hello"```: The ```echo``` command will display the text "Hello" in the terminal. The text is echoed and gets displayed as output.
- ```> testfile```: The ```>``` is a redirection operator. It redirects the output of the ```echo``` command to the name of a file. In this case, the text "Hello" is redirected into ```testfile```.

<img width="806" alt="4  echoed hello into a testfile" src="https://github.com/user-attachments/assets/c166a53a-8abb-4958-84c5-e81976101eb3" loading="lazy"/>

We can also append text to the file using the ```>>``` redirection operator.

In other words, if we ```echo``` text using two redirection operators, we'll be able to add new lines of text without affecting the original lines of text.

<img width="787" alt="5  Append text with two redirection operators" src="https://github.com/user-attachments/assets/4627e817-76a9-4387-b405-073515db2bbb" loading="lazy"/>

Notice how we have two lines of text.

But we may just want to read the files within the terminal, as it's a lot more efficient.

The ```cat``` command will help us do this. It stands for "concatenate" because we can join multiple files together with this command. However, for our purposes, we'll simply use it print the contents of the file on our terminal.

Let's ```cat``` our ```testfile```.

<img width="627" alt="6  cat command" src="https://github.com/user-attachments/assets/39357fe4-1d7d-4f29-95a2-7d54e2ffaffe" loading="lazy"/>

Notice how we can view the contents of the file.

So echoing text into files with redirection operators is useful for simple or quick tasks.

But we may want to edit and navigate through multiple lines of text. To accomplish this, we'd want a tool more suitable for longer files. That's where ```nano``` becomes handy.

```nano``` is text editor we can use in the Linux command line.

In our machine, it lives in the ```/bin/``` directory.

<img width="620" alt="7  which nano command" src="https://github.com/user-attachments/assets/2d5ea7b6-7b59-4666-9a96-b26a134a6222" loading="lazy"/>

So if we wanted to edit a file with ```nano```, we'd just use the following command:

```
nano testfile
```

After entering the command, we'll see our file's contents within the ```nano``` editor.

<img width="480" alt="8  open nano" src="https://github.com/user-attachments/assets/c66b664e-64d0-4519-b26a-e73ade6efc4a" loading="lazy"/>

We can add some text.

Then use ```Ctrl + X``` to exit ```nano```. It'll prompt us to save the file, so just type in ```Y``` and click enter once the file name appears. 

<img width="483" alt="9  Save new file in nano" src="https://github.com/user-attachments/assets/19e75184-b5b3-42ff-9e0b-924e273d8ce6" />

Finally, let's delete the file and folder we created for this lab.

We can delete a file using the ```rm``` command. Let's do that now with our ```testfile```.

<img width="900" alt="10  rm testfile command" src="https://github.com/user-attachments/assets/50250df1-1794-4443-bab5-f802c34c9dbd" loading="lazy"/>

Notice how the file is gone now.

Let's go back up a directory and try deleting our ```testfolder```.

<img width="616" alt="11  error when trying to remove a directory" src="https://github.com/user-attachments/assets/b1934189-74a9-410c-87f6-156341833739" loading="lazy"/>

We'll get an error saying that we can't remove it because it's a directory.

To troubleshoot this, we can go to the man pages for the ```rm``` command. We'll discover that if we want to remove a directory, we should use the ```-r``` flag. 

<img width="425" alt="12  man pages for rm" src="https://github.com/user-attachments/assets/cd742473-8ce9-45bc-94bf-a0d2816b3711" loading="lazy"/>

Our command will look like:

```
rm -r testfolder
```

Our folder has been successfully deleted.

<img width="624" alt="13  rm -r testfolder command" src="https://github.com/user-attachments/assets/feaf6a6d-1808-4df2-9e27-4e8d187cfc3e" loading="lazy"/>

# Lab #9: File Permissions on the Command Line

File and folder permissions in Linux are essential for keeping data secure and organized. 

Permissions act as security rules, controlling who can access or modify files. They ensure that only the right people (or programs) can read, write, or execute files. This is useful for managing servers, sharing resources, or securing sensitive data.
 
Ultimately, understanding permissions will help us prevent unauthorized access or data loss.

Let's open up a terminal and start looking at permissions.

Navigate to the root directory and run ```ls -al```. We'll see folders and files with permission on the left.

<img width="520" alt="1  ls -al command in root directory" src="https://github.com/user-attachments/assets/6b4bf48f-f9db-4e43-8d98-118e9e063d48" loading="lazy"/>

There are three tiers of permissions in Linux. We'll call them "user roles" for the remainder of the lab: 

- **Owner:** The person who created the file/folder.
- **Group:** A collection of users who share access to the file/folder.
- **Others:** Every other user on the system.

And we can apply three different permission types to each user role:

- **Read (r):** View the contents of a file/folder.
- **Write (w):** Modify or delete the file/folder.
- **Execute (x):*** Run a file or access a folder.

Let's see this in action by zooming in on the home directory for the ```root``` user.

<img width="505" alt="2  permissions of home directory for root user" src="https://github.com/user-attachments/assets/ac2806f2-c7b0-4d61-957c-b38eda743227" loading="lazy"/>

Here's what these set of permissions mean.

- The very first character indicates whether we're dealing with a folder or file. The ```d``` means it's a directory or folder.
- The next three characters represent the owner role permissions. Notice how the owner of the folder has read, write, and execute permissions.
- The next three characters represent the group role permissions. A hyphen or tack means that no permissions are granted. Therefore, users in the group role within the ```root``` user directory have no permissions.
- The final three characters denote the permissions for everyone else. Since we only see tacks, it means that everyone else on the system has no permissions for the ```root``` user directory.

So how do we know who's the owner and what group the ```root``` directory belongs to?

That's what these two columns are for.

<img width="525" alt="3  owner and group columns for permissions" src="https://github.com/user-attachments/assets/38c7a996-addc-409e-bd5b-6b8c7e17de6e" loading="lazy"/>

The left column is the owner's name, and the right column is the group's name. 

So let's say I wanted to view the permissions of the root user's home directory, which is the directory we've been looking at.

<img width="450" alt="4  permission denied to root" src="https://github.com/user-attachments/assets/8b45479e-12ba-4d9d-944e-a84cd737d8f6" loading="lazy"/>

Notice how we get a permission denied error. 

Recall that the ```group``` and ```others``` user roles didn't have permissions set. We're associated with the user roles so we can't look inside the directory. And since we're not the owner of the folder, and we're not accessing it with elevated permissions, we don't have permission to access it. 

Next let's play around with permissions to get a stronger sense for how this works.

Let's go to our home folder.

<img width="515" alt="5  cd to home directory" src="https://github.com/user-attachments/assets/a7d89bb8-2402-4fc7-b3f2-b7ad4785ea75" loading="lazy"/>

I've created an empty file on my home directory called ```nerd```.

We can confirm this by using the ```file``` command, which gives us information on the file type.

<img width="916" alt="6  file command on nerd file" src="https://github.com/user-attachments/assets/4f4f3b70-9546-4139-839b-a8b7c40efccc" loading="lazy"/>

We've confirmed it's an empty file. 

Now, we'll use the ```nerd``` file to illustrate how to modify permissions in Linux. We'll use the ```chmod``` command to do this. It's an important command because it allows us to modify permissions in Linux.

If we use the ```whatis``` command on it, we'll see how it allows us to "change file mode bits."

<img width="515" alt="7  whatis chmod command" src="https://github.com/user-attachments/assets/c7ea2fee-7e30-47b8-8faa-9190ef9808ef" loading="lazy"/>

It'll sound confusing at face value. 

So let's open up the man pages to learn more.

<img width="800" alt="8  man page for chmod" src="https://github.com/user-attachments/assets/6905f51e-371a-4586-82c4-44266400af5d" loading="lazy"/>

I highlighted an important area for our understanding of ```chmod```.

Permissions are set using numeric modes, and they're derived from numeric values that represent different permission types. So in the context of using ```chmod```, "read" permissions are assigned the value 4, "write" permissions are assigned the value 2, and "execute" permissions are assigned the value 1. 

<img width="795" alt="9  numeric values for chmod" src="https://github.com/user-attachments/assets/a7137faf-b097-48c3-b16d-5c5f4ce6fbb5" loading="lazy"/>

Now, when we can combine and add these three numeric values together, an octal digit will emerge as the sum (a number between 0 and 7). 

Each octal digit represents a unique combination of permissions for each user role. This will make more sense once we use ```chmod``` to change permissions.

But for now, let's run through each of the octal digits to see how each combination of permissions work:

- **0**: No permission (0)
- **1**: Execute only (1)
- **2**: Write only (2)
- **3**: Write + Execute (2+1)
- **4**: Read only (4)
- **5**: Read + Execute (4+1)
- **6**: Read + Write (4+2)
- **7**: Read + Write + Execute (4+2+1)

Do you remember how file permissions are displayed when we used the command ```ls -al```? 

The last nine characters tell us the permissions for each user role. And they're all separated in segments of three—the first segment representing the ```owner``` permissions, the second segment representing the ```group``` permissions, and the third segment represents the ```others``` permissions. 

We'll use the octal digits in the same order.

Technically, there are four octal digits. But we'll omit the first one since it's a bit more complex (and beyond the scope of this lab). The remaining three octal digits will represent the combination of permissions for the owner, group, and others user roles. 

<img width="800" alt="10  octal digits" src="https://github.com/user-attachments/assets/2f2851d1-850d-413c-b634-1cac689cd9a2" loading="lazy"/>

That was a lengthy explanation.

So let's walk through some examples in the command line to cement these ideas in our brain.

Go back to our ```nerd``` file. If we look at the current permissions, we'll see that the owner of the file has read and write permissions. The group user role has read and write permissions as well. Then everyone else only has read permissions.

<img width="514" alt="11  permissions for nerd file" src="https://github.com/user-attachments/assets/19860765-0564-46fa-97ec-de77dc695328" loading="lazy"/>

Let's change these permissions.

I want to give every user role full permissions (read, write and execute). So I need to add each numeric value for read (4), write (2), and execute (1). This is ```4+2+1=7```. The ```7``` is the octal digit that represents full permissions. 

And since we want every user role to have full permissions, we'll use ```7``` for all three octal digits. 

This is what the command looks like:

```
chmod 777 nerd && ls -al nerd
```

Side note: The ```&&``` operator is used to chain commands together, ensuring that the second command (```ls -al nerd```) runs only if the first command is successful. It just makes things more efficient for us.

<img width="513" alt="12  chmod 777" src="https://github.com/user-attachments/assets/b850ae2c-58bf-4404-9887-0cfcdb68d09b" loading="lazy"/>

Using ```777``` gives us the most permissive setting we can apply to files and directories. It's the riskiest since every user role has the highest level permissions. 

Next let's change permissions to a common setting for files—```chmod 644```.

This will give the ```owner``` read and write permissions. Then it'll give the ```group``` and ```others``` roles read only permissions. 

Here's what that would look like:

<img width="522" alt="13  chmod 644" src="https://github.com/user-attachments/assets/68e1d388-e2eb-4a06-83d5-fcf27a24a7f3" loading="lazy"/>

Finally, let's use a more restrictive permission setting that demonstrates the principle of least privilege—```chmod 700```.

This will give the ```owner``` full permissions. But it'll ensure that ```group``` and ```others``` have no permissions.

<img width="512" alt="14  chmod 700" src="https://github.com/user-attachments/assets/fab594c6-6efd-4b8f-967b-e591d3095c3b" loading="lazy"/>

Cool. We've covered the basics of using ```chmod``` to change permissions. 

# Lab #10: Diving Deeper Into Linux User Permissions and Sudo Basics

Managing permissions isn’t just about using commands like ```chmod```—it’s about understanding who should access what and why.

Permissions define whether users can read, write, or execute a file. And good system administration means we ought to be intentional with setting them. This ensures only authorized users can modify important files, preventing accidental or malicious changes.

So in this lab, we'll create a user and demonstrate how permissions impact their level of access.

Let's open up a terminal and make sure our ```nerd``` file still exists in ```/home/colton```. I also added some text to it.

<img width="760" alt="1  Checking for nerd file" src="https://github.com/user-attachments/assets/c0aba43e-7f39-4190-acf7-4ca5f4e44e65" loading="lazy"/>
