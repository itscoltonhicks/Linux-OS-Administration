# Linux OS Administration (Project In Progress)
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

- [Lab #10: Diving Deeper Into Linux User Permissions and Sudo Basics](https://github.com/itscoltonhicks/Linux-OS-Administration/blob/main/README.md#lab-10-diving-deeper-into-linux-user-permissions-and-sudo-basics)

- [Lab #11: Group Permissions in Linux](https://github.com/itscoltonhicks/Linux-OS-Administration/blob/main/README.md#lab-11-group-permissions-in-linux)

- [Lab #12: Finding and Searching on the Command Line](https://github.com/itscoltonhicks/Linux-OS-Administration/blob/main/README.md#lab-12-finding--searching-on-the-command-line)

- [Lab #13: Process Management on the Command Line](https://github.com/itscoltonhicks/Linux-OS-Administration/blob/main/README.md#lab-13-process-management-on-the-command-line)

- [Lab #14: Linux Services with ```Systemctl```](https://github.com/itscoltonhicks/Linux-OS-Administration/blob/main/README.md#lab-14--linux-services-with-systemctl)

- [Lab #15: Data Streams and Command Redirection](https://github.com/itscoltonhicks/Linux-OS-Administration/blob/main/README.md#lab-15-data-streams-and-command-redirection)

- [Lab #16: Create Scheduled Tasks with ```Crontab```](https://github.com/itscoltonhicks/Linux-OS-Administration/blob/main/README.md#lab-16-create-scheduled-tasks-with-crontab)
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

**Side Note**: *Later in the project I adjust my NSG to only allow remote access from my IP address. This is more ideal if you don't want a bunch of brute force attempts (and possibly a DoS incident).* 

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

Let's open up a terminal and make sure our ```nerd``` file still exists in ```/home/Colton```. I also added some text to it.

<img width="760" alt="1  Checking for nerd file" src="https://github.com/user-attachments/assets/c0aba43e-7f39-4190-acf7-4ca5f4e44e65" loading="lazy"/>

Great. Now we'll add another user account.

So any administrative task in Linux typically requires elevated permissions. This helps maintain system security and integrity. So, in the case of adding another user account, we'll want to use the ```sudo``` command. This allows us to execute commands as the "root user" or "superuser", giving us the elevated permissions required to carry out the task.

<img width="900" alt="2  sudo man pages" src="https://github.com/user-attachments/assets/2e3e1fb8-e810-482e-9b90-eb4dc5eed7f6" loading="lazy"/>

We can run the ```sudo -l``` command to list information about what administrative commands our current user can execute with ```sudo```. 

<img width="769" alt="3  sudo -l command" src="https://github.com/user-attachments/assets/2b326124-1783-4aff-9b85-82647763c2d4" loading="lazy"/>

Highlighted above, we can run any command as any user on any host using ```sudo```.

So before creating a new user, let's illustrate the basics of how ```sudo``` works. I'll create a new file with ```sudo``` to display what it means to execute a command as the root user.

I'll call the file ```SudoPermissionFile```:

```
sudo touch SudoPermissionFile
```

Now we can check the permissions for this file. 

Notice how it's owned by the root user and root group.

<img width="789" alt="4  file permissions for root user" src="https://github.com/user-attachments/assets/93d9efae-904d-4935-8fd6-4c2015338c25" loading="lazy"/>

This is an example of how using ```sudo``` executes a command as the root user. 

If we try adding text into this file without using ```sudo```, we'll get a permission denied error. 

<img width="805" alt="5  permission denied to add text without sudo" src="https://github.com/user-attachments/assets/9feb1ad5-1ef5-4258-aafb-16a13c433197" loading="lazy"/>

This is happening because the ```Colton``` user doesn't have write permissions for this file.

So we'd need to prefix the command with ```sudo``` in order to add text. 

<img width="772" alt="6  redirection operator isn't passing sudo beyond it" src="https://github.com/user-attachments/assets/432fa324-628a-4737-bf03-75fcc4661482" loading="lazy"/>

Whoops, looks like we're still getting a permission denied error. 

This is happening because the redirection operator is executed by the shell, not the ```sudo``` command. The ```echo "hello"``` command has elevated permissions. But the redirection operation ```>``` acts like a secondary gatekeeper who also needs elevated permissions. The redirector doesn't carry ```sudo``` permissions beyond it.

So we'll need to execute the command as an entire ```sudo``` statement by using ```bash -c```:


```
sudo bash -c "echo 'hello' > SudoPermissionFile"
```

<img width="774" alt="7  sudo bash -c command" src="https://github.com/user-attachments/assets/8922d02f-80a6-4266-9bb9-8c83f3738a6b" loading="lazy"/>

Here's a quick command breakdown:

- ```sudo```: Runs the command with administrator privileges.
- ```bash -c```: This tells our Bash shell to run a specific command or a series of commands within quotes. It allows us to run the entire sequence of commands using ```sudo```.
- ```echo 'hello' > SudoPermissionFile```: This writes "hello" into the file named ```SudoPermissionFile```. This is being executed as the root user. 

Now let's delete this file using the ```sudo``` command:

<img width="808" alt="8  sudo rm command" src="https://github.com/user-attachments/assets/ddcdf0c1-88f8-498f-b6b7-2bd6fb8af8bb" loading="lazy"/>

So we've covered the basics of ```sudo```.

Now we're ready to create a new user. We'll do this with the ```adduser``` command. And it'll be executed as the root user:

```
sudo adduser shellbandit
```

After executing the command, we'll see a a few things appear:

- A new group named ```shellbandit``` is added.
- A new user with the User ID 1001 is created. 
- A home directory for ```shellbandit``` is created.
- A prompt for a password.

After entering the password, we'll be prompted with some additional information. We can keep them blank or fill them in, then press the ```y``` key when we're done. 

<img width="529" alt="9  sudo adduser command" src="https://github.com/user-attachments/assets/27385209-6232-4986-887f-d7b2ec93f52f" loading="lazy"/>

Now we have our second user.

Let's open up a new terminal and dock it—one for the ```Colton``` user, and the other for our ```shellbandit``` user. Next we'll log into our new user account in the new terminal. We'll do this with the ```su``` command. This allows us to run commands with a substitute user and group ID. 

So we can run a persistent shell as another user simply with the command of ```su <username>```. 

<img width="925" alt="10  man pages for su" src="https://github.com/user-attachments/assets/7542a684-c39a-4a18-9d22-ff56102080ba" loading="lazy"/>

We'll use it with our ``shellbandit``` user and get prompted for the password.

```
su shellbandit
```

Once complete, the terminal will assume we're in a ```shellbandit ``` shell. 

<img width="925" alt="11  New shell session with shellbandit user" src="https://github.com/user-attachments/assets/92f3789e-7ee6-4ad7-ad5b-099bb966c991" loading="lazy"/>

Let's quickly run through a few commands to get familiar with our new user:

- Run ```whoami``` to confirm we're operating the terminal with our new user account.
- Run ```groups``` to see that ```ShellBandit``` doesn't belong to any other group than their own.
- Navigate to the home directory and list all directories nested within it. We'll notice how the ```/home/ShellBandit``` directory was created for the new user. 

<img width="925" alt="12  investigate our new shellbandit user" src="https://github.com/user-attachments/assets/338ddd30-227d-406f-a6ba-d33a52b9c142" loading="lazy"/>

Now let's try to read the ```nerd``` file from our ```shellbandit``` user. We need to navigate to Colton's home directory to access it.

This will reveal whether or not our permissions are working as intended.

<img width="925" alt="13  permission denied to cat nerd file from shellbandit user" src="https://github.com/user-attachments/assets/6f567b08-cb1a-4fcf-95e5-04e0eec596bc" loading="lazy"/>

Next we'll modify permissions so our ```shellbandit``` user can read it.

I'll go back to the ```Colton``` shell session and run ```chmod 707```. This will give everyone else on the system full permissions (read, write, and execute). 

```
chmod 707 nerd
```

We can view the newly set permission in our ```shellbandit``` terminal and notice how it instantly updates.

<img width="925" alt="14  chmod 707 command" src="https://github.com/user-attachments/assets/e794d5ec-0ef9-4112-9cac-15b786bb4789" loading="lazy"/>

Now we can read the file from our ```shellbandit``` user. 

<img width="925" alt="15  cat nerd file from shellbandit user after new permissions" src="https://github.com/user-attachments/assets/457eec99-b35c-4d0a-83ce-528fcf6651db" loading="lazy"/>

We can also append text to it.

<img width="925" alt="16  append text from shellbandit user account" src="https://github.com/user-attachments/assets/a35d52e5-f29d-4b0e-be78-11b7a693ade6" loading="lazy"/>

So that's how user permissions work in practice. We're done now, so let's clean up our environment.

We can ```exit``` the ```shellbandit``` shell. 

<img width="925" alt="17  exit a shell instance" src="https://github.com/user-attachments/assets/275602a7-f49e-4f73-be92-f30b571f1e56" loading="lazy"/>

Notice how we didn't get logged out of the terminal. We simply returned to our original user account. This is because ```su``` created a new shell session on top of our original one. Think of it like adding a new layer over the existing one.

So, when we entered ```exit```, we removed that layer and went back to our original shell session.

Next we can delete our ```shellbandit``` user from the system.

We'll use the ```deluser``` command for this. We'll run it using ```sudo``` so it can execute with proper permissions:

```
sudo deluser shellbandit
```

<img width="557" alt="18  sudo deluser command" src="https://github.com/user-attachments/assets/acb77c65-a43e-43ef-a4f0-802fa12d23e8" loading="lazy"/>

I'll also delete the ```nerd``` file, and any other resources I created for this lab.

# Lab #11: Group Permissions in Linux

User groups provide a streamlined way to grant permissions and eliminate the need for multiple layers of individual permission settings.

We accomplish this by associating user accounts with groups (along with additional file setting configurations). This saves time, reduces errors, and simplifies user management. Understanding how to properly set up user groups and permissions ensures data integrity and secure access control. So in this lab, we'll walk through various commands for assigning group-based permissions.

We're going to make a group, add two people to it, and change some file settings so everyone has the right permissions.

Let's open up a terminal and create two new users.

<img width="525" alt="1  adding two new users" src="https://github.com/user-attachments/assets/9c947428-8ff4-40ab-9326-70e162c34dca" loading="lazy"/>

We've added two new users to the system, ```anakin``` and ```luke```.

Next we'll create a new group using the ```addgroup``` command:

```
sudo addgroup jedicouncil
```

<img width="550" alt="2  sudo addgroup command" src="https://github.com/user-attachments/assets/03367aba-ea47-4425-847a-10398c66934a" loading="lazy"/>

Now that we have our new group, we'll want to add both of our users to it.

We can accomplish this by using the ```usermod``` command. It allows us to modify user account information. We'll run it as the root user, then use the flags ```-aG``` to specify which group we'll be adding users to. 

Here's the command for our first user:

```
sudo usermod -aG jedicouncil anakin
```

Quick command breakdown:

- ```sudo```: This runs the command with administrator privileges.
- ```usermod```: This command allows us to modify user account information.
- ```-aG```: The ```-a``` flag adds ```anakin``` to the new group without removing him from other groups (i.e. it appends). And the ```-G``` flag specifies the name of the group we're adding ```anakin``` to, which is the ```jedicouncil``` group.
- ```jedicouncil```: The name of the group.
- ```anakin```: The user account.

Now repeat the same command for the ```luke``` user.

```
sudo usermod -aG jedicouncil luke
```

<img width="513" alt="3  usermod -aG command" src="https://github.com/user-attachments/assets/efc2dbf0-c0e1-4e11-a510-bb87845060b0" loading="lazy"/>

So to verify that we added the users to the group, we can run the ```groups``` command against a specific user name.

<img width="513" alt="4  groups command" src="https://github.com/user-attachments/assets/7a7afc4d-eef2-48c0-b97c-e484741f393e" loading="lazy"/>

At this point, it's helpful to know where some of this information is stored on disk.

We'll look at the following files:

- ```/etc/passwd```
- ```/etc/shadow```
- ```/etc/group```

Let's start with ```/etc/passwd```.

If we ```cat``` that file, we'll see a list of user account information. It stores things like the username, UID, GID, and the user's home directory path.

<img width="600" alt="5  cat etc passwd file" src="https://github.com/user-attachments/assets/c480c558-9cdf-42e9-be93-000b10e63865" loading="lazy"/>

The file is pretty bloated though. So we can use the ```grep``` command to filter for specific keywords or patterns. 

Let's ```grep``` the same file, filtering for both of our new users.

<img width="505" alt="6  grep command for etc passwd file" src="https://github.com/user-attachments/assets/650c5d63-8870-4b7a-9327-760f93344395" loading="lazy"/>

By "grepping" the ```/etc/passwd``` file, we can quickly confirm if our new users exist on the system (which they do).

Next we'll look at the ```/etc/shadow``` file. 

This file stores hashed passwords for user accounts. And for that reason, it requires ```sudo``` permissions to access it. Only system administrators should have access to it. So let's ```grep``` this file as the root user, using both of our new user accounts as the search pattern. 

First for the ```anakin``` user:

```
sudo grep anakin /etc/shadow
```

Then for the ```luke``` user:

```
sudo grep luke /etc/shadow
```

<img width="866" alt="7  sudo grep etc shadow file" src="https://github.com/user-attachments/assets/51258e37-4857-4fd8-8301-471e321ca09a" loading="lazy"/>

Finally we'll look at the ```/etc/group``` file. 

It keeps track of all the groups on the system. And it'll contain all the users that belong to each group.

Let's ```grep``` the ```/etc/group``` file, using ```jedicouncil``` as the search pattern.

<img width="869" alt="8  sudo grep etc group file" src="https://github.com/user-attachments/assets/1565ed46-76bf-46c3-971c-90c4c90659e8" loading="lazy"/>

We'll see that both of our users belong to our new group.

Great. Now let's continue illustrating group permissions by docking two terminals—one session as ```anakin```, and one session as ```luke```. 

We'll use the ```su``` command to change users.

<img width="925" alt="9  docked view of two new users" src="https://github.com/user-attachments/assets/ec3564db-a0fb-49fd-a49a-e8b84b27e661" />

Next we'll create a file from the ```anakin``` shell.

```anakin``` will be the file owner. Then we'll make the file accessible to all members of the ```jedicouncil``` group. To keep with our Star Wars theme, I'll create file called ```tatooineWeatherReport```.

Then I'll echo the text ```Weather updates from Tatooine (spoiler: always sunny).``` into the file.

```
echo "Weather updates from Tatooine (spoiler: always sunny)." > tatooineWeatherReport
```

<img width="925" alt="10  adding new file about tatooine weather" src="https://github.com/user-attachments/assets/a5f986b5-a125-406b-886c-415c8725add9" loading="lazy"/>

Now we'll use ```chmod 770``` on the file to give the group full permissions to the file.

<img width="925" alt="11  chmod 770" src="https://github.com/user-attachments/assets/302b8d90-152e-4799-a14d-5c6076813226" loading="lazy"/>

Lastly, notice in the image above that the second column still says ```anakin```. 

This is the group name assigned to the file. We need to change this to ```jedicouncil``` so that all members of this group can access the file. The ```chown``` command helps us to do this.

It allows us to change file ownership using the following syntax.

<img width="501" alt="12  chown man pages" src="https://github.com/user-attachments/assets/6da496bb-13fc-4188-88d9-040f748a4708" loading="lazy"/>

So we'll use the following command to change the group assigned to the file:

```
chown anakin:jedicouncil tatooineWeatherReport
```

<img width="501" alt="12  chown man pages" src="https://github.com/user-attachments/assets/9bbebd0e-b2bf-48f3-b007-9a41fa1c89c8" loading="lazy"/>

Now everyone in the ```jedicouncil``` group should be able to access the file.

We can illustrate this by hopping into the ```luke``` shell and navigating to where the ```tatooineWeatherReport``` file lives on disk, which is Anakin's home directory.

<img width="925" alt="14  luke viewing tatooine file" src="https://github.com/user-attachments/assets/a7b30ea6-f252-461d-915e-3ac1a5277390" loading="lazy"/>

As we can see in the image above, ```luke``` can read the file because they're a member of the ```jedicouncil``` group. 

Let's ```exit``` the ```luke``` user shell.

We're now operating the terminal from our original user account.

If we try to view the file from here, we'll get a permission denied error.

<img width="925" alt="15  permission denied for tatooine file in colton shell" src="https://github.com/user-attachments/assets/cc98be57-0aa1-4e86-8217-db0ae269bad7" loading="lazy"/>

The ```Colton``` user account—which falls under the ```others``` user role for the file permissions—doesn't have any permissions set.

That's it for group permissions. We'll clean up the environment by exiting the terminals, removing the file, and deleting the new user accounts (just like in previous labs).

Except this time, we'll also delete the ```jedicouncil``` group by using the ```delgroup``` command:

```
sudo delgroup jedicouncil
```

<img width="515" alt="16  sudo delgroup command" src="https://github.com/user-attachments/assets/5c50f2a7-f54b-4604-8a4c-64a23af53cc1" loading="lazy"/>

# Lab #12: Finding & Searching on the Command Line

Trying to find files through a Linux terminal can feel like searching for a needle in a haystack. 

And that's why we have the ```find``` command. It's like a metal detector for sifting through that haystack—it helps locate specific files, folders, or data buried deep within directories. It's also important for troubleshooting a system issue or triaging an incident.

So in this lab, we'll walk through how to use ```find```.

The ```find``` command is very powerful.

It allows us to search for files in a directory hierarchy. The man pages are packed with flags that specify user-defined conditions. These conditions filter *what* to search for, *where* to search, and *how* to match specific attributes.

Feel free to scroll down the man pages to view these flags.

<img width="650" alt="1  man pages for find" src="https://github.com/user-attachments/assets/8efc7f77-57e9-4e71-977c-fc10c8f8641e" loading="lazy"/>

We'll walk through some common flags.

But first, we'll add a few things to our system to demonstrate these different flags in action:

- We'll create a file in lowercase.
- We'll create a file in uppercase.
- We'll give one of the files ```700``` permissions, providing the file owner read, write, and execute access.
- We'll make a directory.

<img width="525" alt="2  add files and directory for find command" src="https://github.com/user-attachments/assets/1f1344ff-2020-4923-b0da-f446aed238f8" loading="lazy"/>

Great. Now let's walk through common flags for ```find```.

## Search by File Name

So when we know the name of a file (or a portion of it), we can use a "file name" condition to easily sift through files.

We'll start each command with ```find .```.  The ```find``` command is naturally how we start the search, and the ```.``` dot specifies the current directory as the starting point for the search. 

Then we'll use the ```-name``` flag with the exact case sensitive file name:

```
find . -name passwords.txt
```

<img width="506" alt="3  find   -name command" src="https://github.com/user-attachments/assets/82bd5500-57c2-43b7-8257-2c65974ba4c7" loading="lazy"/>

But let's say that we don't know the full file name. 

We only know a portion of it. Well we can wrap some text inside of quotes and asterisks. For example, if we use ```"*pass*"```, then the output will be any file that contains the text ```pass``` within it. 

The asterisks function as wildcards, allowing any number and combination of characters is valid in the location of each asterisk.

```
find . -name "*pass*"
```

<img width="603" alt="4  find   -name command with wildcards" src="https://github.com/user-attachments/assets/73749508-931a-4825-887d-3328a5ef6647" loading="lazy"/>

Observe how we've retrieved multiple files that contain ```pass``` somewhere within their name, including two of the files we created earlier.

However, we'll also notice that we don't see our uppercase file in the output.

This is because the ```-name``` flag searches for files with case sensitive results. So if we're unsure of case sensitivity or just want to guarantee we're not missing a file, we can use the ```-iname``` flag to search with case insensitive results. 

Let's use this flag to find our uppercase file:

```
find . -iname "*pass*"
```

<img width="609" alt="5  find   -iname command" src="https://github.com/user-attachments/assets/a97d11dd-aefc-4b22-83ad-609d7db5ff6f" loading="lazy"/>

Now we're able to see our uppercase file.

The ```-name``` flag can also be used to find files with specific file extension types. 

For instance, let's say we only want to find files with the ```.txt``` file extension. We'd just use the same command and put the file extension in quotes. Then we'd add an asterisk to the front of the extension, indicating that the file can be named anything as long as it ends with ```.txt```.

```
find . -iname "*.txt"
```

<img width="628" alt="6  find txt files" src="https://github.com/user-attachments/assets/d8a26210-5369-45fb-80d0-55939e40b6c0" loading="lazy"/>

## Search by Type

Maybe we'd like to search for a specific type of object.

For example, let's say we only want to search for files when we're cleaning up our system. The ```-type``` flag helps us do this. 

To build upon our previous search commands, let's only look for case insensitive files:

```
find . -iname "*pass*" -type f
```

<img width="638" alt="7  type f flag for find command" src="https://github.com/user-attachments/assets/41432280-869e-475e-b1f1-61ad99c51393" loading="lazy"/>

The ```f``` option specifies we're looking for files only.

But we'll notice that our newly created directory won't be shown. So we can use the ```d``` option to specify directories only:

```
find . -iname "*pass*" -type d
```

<img width="612" alt="8  type d flag for find command" src="https://github.com/user-attachments/assets/e26b5d39-4f13-42b3-8d21-11dec67fde6b" loading="lazy"/>

## Search by Ownership

Perhaps we'd like to search for results based on user or group ownership of files.

This is useful for identifying orphaned files, files owned by specific users, or files that might pose security risks due to incorrect ownership.

Let's start by searching for files owned by a specific user, which we can use the ```-user``` flag for.

```
find . -iname "*pass*" -type f -user Colton
```

<img width="610" alt="9  Search for files by user ownership" src="https://github.com/user-attachments/assets/a4c736b4-0a64-47da-881f-050679f10b47" loading="lazy"/>

This shows us all the files that the ```Colton``` user owns.

Now let's search for files that belong to a specific group, which is where the ```-group``` flag becomes useful. I'll use ```Colton``` as the name of the group.

And I'll focus the next search on directories.

```
find . -name "*pass*" -type d -group Colton
```
<img width="505" alt="10 Search for directory by group ownership" src="https://github.com/user-attachments/assets/a1906211-8fc0-44fe-81fd-8d9e4249c928" loading="lazy"/>

Now we'll only see one directory that belongs the group named ```Colton```. 

## Search by Permissions

We might want to find files based on their read, write, or execute permissions.

This is helpful for identifying files with insecure permissions, to enforce best practices, and prevent unathorized access. For example, what if we only wanted to find files where the owner has full permissions? Then we could use the ```-perm``` flag and its corresponding file mode bits.

We'd use a command like this:

```
find . -iname "*pass*" -type f -user Colton -perm 700
```

<img width="513" alt="11  search by perm 700" src="https://github.com/user-attachments/assets/1f14276e-685b-498b-a259-a9a4f5224ad1" loading="lazy"/>

Now we'll only see files where the file owner named ```Colton``` has read, write, and execute permissions on it. Even though we used ```-iname``` for a case insensitive result, the ```PASSWORDS.txt``` file didn't show up because the file owner doesn't have full permissions. 

## Search by Size

Perhaps we'd like to find files by its size.

This is hepful for cleaning up storage, identifying large or unusually small files, and managing disk usage. We'd use the ```-size``` flag to accomplish this. Then we'd specify the size itself. 

For example, let's say we're looking for files that are exactly 1 kilobyte in size:

```
find . -type f -size 1k
```

<img width="450" alt="12  search by -size 1k" src="https://github.com/user-attachments/assets/46623501-4a4e-4836-9637-eec4f4a53ce5" />

We'll get a list of files that are 1 kilobyte in size. But if we wanted to specify files smaller or larger than 1 kilobyte, then we'd use ```-``` or ```+``` before the ```1k```.

Let's look for files smaller than 1 kilobyte.

```
find . -type f -size -1k
```

<img width="771" alt="13  search by size -1k" src="https://github.com/user-attachments/assets/5b6b9d91-c9be-4786-b83e-839e45a4e26a" loading="lazy"/>

Now we'll see our newly created files listed.

## Search by Modification Time

Maybe we want to find files that have been recently modified.

This is useful for incident response and system troubleshooting, especially when searching for logs or recent file changes. This is when we'd use the ```mmin``` flag. Then we'd just specify the modification time in minutes.

For example, here's how we'd search for file changes within the past minute. We use ```-1``` to denote "within the last minute:"

```
find . -type f -mmin -1
```

This command is correct, but we won't see any output from the "password" files we created earlier.

The reason is because we haven't modified those files yet. We've only created them. So if we added some text to one of the files and repeat the command, we'll see one of our "password" files in the output.

<img width="515" alt="14  search by file modification in minutes" src="https://github.com/user-attachments/assets/886fce96-c5a1-4aa4-a4cc-7b43954c45bd" loading="lazy"/>

That wraps up the basics for using the ```find``` command. 

# Lab #13: Process Management on the Command Line

The command line is a powerful tool for managing and inspecting system processes.

Everything in Linux is a file. And we can interact with processes, memory, and system stats as files on the command line. Unlike graphical interfaces (GUIs), the command line offers speed, flexibility, and deeper insights into what's happening under the hood of Linux. It's essential for system administrators, cybersecurity professionals, and developers who need precise control over system operations.

So in this lab, we'll use various commands and tools to navigate system processes. 

Let's start by opening up a terminal and running a command called ```top```.

It's similar to System Monitor and Task Manager. It displays a "table of processes" running on the Linux system. And it does this in real-time on the command line.

<img width="575" alt="1  top command" src="https://github.com/user-attachments/assets/f17682fa-32b6-412f-a9ca-5519cbe377cc" loading="lazy"/>

Notice how it's running continuously and dynamically, changing as the operating system is in use. 

We can enter the ```h``` key to get some help on how to use the ```top``` tool. We'll see actions we can perform, like ```l```, ```t```, and ```m```. 

<img width="542" alt="2  get help for top tool" src="https://github.com/user-attachments/assets/935bae4f-ecc8-4fbd-b952-8ab9c1a38dd1" loading="lazy"/>

Let's illustrate these three actions inside of ```top```.

Entering ```l``` will display the load average or overall system consumption.

<img width="525" alt="3  load average in top" src="https://github.com/user-attachments/assets/158a4094-20fc-4f58-aa3b-e077a2aa8904" loading="lazy"/>

Entering ```t``` shows us different tasks and CPU stats.

<img width="525" alt="4  task and cpu info in top" src="https://github.com/user-attachments/assets/a4961d31-b209-41fb-a492-59eca631ca6f" loading="lazy"/>

Entering ```m``` gives us a different view on memory consumption.

<img width="525" alt="5  memory info in top" src="https://github.com/user-attachments/assets/361644d0-3cef-42fd-8385-b4f038c69093" loading="lazy"/>

Great. We can also search or "locate" processes with ```shift + L```.

I'll open up ```text editor``` on the system, enter ```shift +L```, and type in ```gedit``` (its process name in Linux).

<img width="775" alt="6  locate gedit string in top" src="https://github.com/user-attachments/assets/53375f76-cf13-46db-86f8-9b055a806b15" loading="lazy"/>

We'll see the ```gedit``` process highlighted.

<img width="775" alt="7  gedit process highlighted in top" src="https://github.com/user-attachments/assets/4cb361cc-f216-41bb-81bb-63bea854a0dd" loading="lazy"/>

Then we can kill a process by entering the ```k``` key and type the associated PID for the ```gedit``` process.

<img width="934" alt="8  kill a process in top" src="https://github.com/user-attachments/assets/d08dae8c-ab47-4b58-9aa6-42b11ae6a546" loading="lazy"/>

Once we click ```Enter``` to confirm the kill command, the ```text editor``` will no longer be running as an active instance. 

<img width="900" alt="9  gedit process killed in top" src="https://github.com/user-attachments/assets/b81bba49-cfce-4848-9e39-4f3a1b3d4214" loading="lazy"/>

That's the basics of using ```top``` to monitor system processes.

Next we'll run through additional commands to explore how processes work deeper under the hood of Linux.

Let's begin with the ```free``` command. This simply displays the amount of free and used memory in the system. 

<img width="540" alt="10  free command" src="https://github.com/user-attachments/assets/2f3feff9-70c1-464b-bd08-7d06cbfc42d1" loading="lazy"/>

We can use the ```-h``` flag to view the  human-readable format of our memory consumption.

<img width="532" alt="11  free -h command" src="https://github.com/user-attachments/assets/72420b39-de0c-4c19-ab5b-71460edcce6e" />

Next let's look at the ```df``` command.

This tells us the disk space usage on the file system. We'll see all of our disks and partitions (which are just smaller storage sections separated on a disk). These file partitions are largely set up for isolation and backup purposes. 

We can use the command with or without the ```-h``` flag.

<img width="475" alt="12  df command" src="https://github.com/user-attachments/assets/1e9b7594-cda7-4779-9453-794f9c8ccb63" loading="lazy"/>

Now let's look at the ```ps``` command.

It's powerful because it'll give us a snapshot of the current processes running on the system.

<img width="506" alt="13  ps command" src="https://github.com/user-attachments/assets/c34eb016-8205-45a3-8cf4-108079186dec" loading="lazy"/>

The command by itself doesn't give us many details.

So if we want to see every process on the system, we can use the ```aux``` flags together. It'll show us information on all the processes currently running, the user running each process, and background service processes.

<img width="650" alt="14  ps aux command" src="https://github.com/user-attachments/assets/2470d41f-2a8b-4398-969c-d08f47627cef" loading="lazy"/>

This becomes powerful when we pipe the output of ```ps aux``` to the ```grep``` command. 

This will filter for specific processes and display it on our terminal. The pipe operator ```|``` passes the output from one command to the subsequent one, much like a conveyer belt. 

To illustrate this, we open up the ```text editor``` again and run the following command to filter for it:

```
ps aux | grep gedit
```

<img width="626" alt="15  ps aux with grep command" src="https://github.com/user-attachments/assets/746b99b9-baed-41cf-a78d-7d7a7dd85094" loading="lazy"/>

Now we see a snapshot of the ```gedit``` process currently running on our system.

Similar to using the ```top``` tool, we can kill a process directly on the command line. All we need is the process ID (PID) and the ```kill``` command.

<img width="643" alt="16  kill gedit process in terminal" src="https://github.com/user-attachments/assets/9d4d5867-2dd2-4c4f-a644-5f407fd6c92f" loading="lazy"/>

We'll notice how the ```text editor``` has disappeared. We can confirm this by trying to get another screenshot of the ```gedit``` process. This time, we'll notice how the specific process associated with the editor is gone.

To wrap up this section, we'll inspect the ```/proc``` directory on the command line.

Remember that ```/proc``` contains information for system processes and they're organized by PIDs. There are also additional system information files there as well (e.g. ```uptime```).

<img width="940" alt="17  ls proc directory" src="https://github.com/user-attachments/assets/ed0a788f-e5f5-43cf-91f8-64dec1fa7a28" loading="lazy"/>

And since these files exist in memory, they dynamically change based on what's happening in the system.

We can illustrate this by opening up ```text editor``` again. I'll also use the ```ps aux | grep gedit``` command to grab the PID. 

Then we'll inspect the ```/proc``` directory again and see how our ```gedit``` PID was added.

<img width="845" alt="18  processes dynamically change in proc directory" src="https://github.com/user-attachments/assets/61d84755-427b-487b-a7ae-c077fda71b54" loading="lazy"/>

We can also look inside the PID folder ```2559``` and see the files associated with the ```gedit``` process.

<img width="795" alt="19  list files inside of gedit process file" src="https://github.com/user-attachments/assets/a0a03469-db44-47a2-a70c-3a789fa89906" loading="lazy"/>

This information is very useful. It helps us further understand what a process is doing, how it’s interacting with the system, and whether it’s behaving as expected (or causing problems).

We can also illustrate how command binaries and files work together. 

For instance, we can use the ```uptime``` command to view the information on the terminal. And all this command did was pull that information from the ```uptime``` file. 

<img width="795" alt="20  uptime command and cat uptime file in proc directory" src="https://github.com/user-attachments/assets/96194111-94cb-47a8-98f1-224836fb14d7" loading="lazy"/>

That wraps up our lab. We can begin to see that, when we become more familiar with the command line, we have much greater control over our Linux machines.

# Lab #14 : Linux Services with ```Systemctl```

The ```systemctl``` command is used to control and manage Linux services (commonly referred to as daemons).

A service is a special program that runs in the background, independent of direct user interraction. We need the ```systemctl``` command to start, stop, and check these services. It's kind of like a remote control where we can turn services on, off, and check them when needed. 

If we check the man pages, we'll see how the ```systemctl``` command allows us to control the ```systemd``` system and service manager.

<img width="830" alt="1  services with systemctl" src="https://github.com/user-attachments/assets/135f3f6e-ba53-4e1b-84a9-b3a3c060fd07" loading="lazy"/>

```systemd``` is a system and service manager that manages all the services on our machine. 

It keeps everything organized and running smoothly. It's important for ensuring services start in the correct order and don't crash. So it's like the air traffic controller making sure all the planes (services) take off and land without crashing into each other.

Let's run ```systemctl``` and see what comes up. I'll use the ```--no-pager``` flag to display all the output at once (but you can run it without the flag to get the same output). 

<img width="795" alt="2  systemctl command" src="https://github.com/user-attachments/assets/6c7fcb07-c4ad-41d4-b72d-c71bf2fcdb26" />

We'll see all active "units" on the system:

There are various columns worth noting:

- **Unit**: This shows the name of the service or unit that the system is managing. It's important because we need to know which services we're looking at.

- **Load**: This shows us if a service's configuration has been loaded properly. It's important for checking if services are set up correctly.

- **Active**: This shows the high-level state of the service. It's important to know whether or not a service is in use.

- **Sub**: This provides us more detailed information on a service's state. This is important for giving us a clearer picture of what the service is doing.

- **Description**: This gives a brief explanation of what the service does. It's important for context.

Some Linux systems will also display a **job** column that shows the current job being executed on the service, if any. It helps us see which actions are being performed by a service.

Now when we type ```systemctl``` and hit the Tab key for "tab autocompletion," we'll see a list of options that the ```systemctl``` command can take. These are subcommands for performing actions with ```systemctl```, as well as unit names we can manage.

We'll narrow our options by looking at the various ```list``` subcommands for ```systemctl```. They display detailed information about various units and components of the system.

<img width="899" alt="3  systemctl options with tab autocomplete" src="https://github.com/user-attachments/assets/c6a7c8bf-af14-4211-b7ea-5c672bc47570" loading="lazy"/>

If we want to list all the units (tasks and services) on the system, including inactive and dead ones, we can run the following command:

```
systemctl list-units --all
```

The ```--all``` flag ensures we see the inactive units.

<img width="795" alt="4  systemctl list-units --all" src="https://github.com/user-attachments/assets/1f719304-c7b2-41e8-855b-b39e0514f49d" loading="lazy"/>

Notice how inactive and dead units are highlighted red. 

Since we're focusing on services in this lab, we'll use the ```list-units``` subcommand and append the ```--type=service``` flag to it. This ensures we only see service units:

```
systemctl list-units --type=service
```

<img width="795" alt="5  systemctl list-units --type=service" src="https://github.com/user-attachments/assets/b276bcde-cf7b-4215-8513-7158287cc6d9" loading="lazy"/>

Now we see a proper list of just services.

But we're still missing the inactive and dead services from this view. So we can add the ```--all``` flag to the service request version of ```list-units```.

```
systemctl list-units --type=service --all
```

<img width="900" alt="6  systemctl list-units --type=service --all" src="https://github.com/user-attachments/assets/27322e8a-b494-4cec-8620-5db4fdf7e38d" loading="lazy"/>

Great. Now we see all services, which is helpful for troubleshooting. 

We can get an even more targeted view of inactive services by using the ```--state=inactive``` flag to the command.

```
systemctl list-units --type=service --state=inactive

```

<img width="900" alt="7  systemctl list-units --type=service --state=inactive" src="https://github.com/user-attachments/assets/8d8218f8-a438-4131-b8de-5bb776e3838a" loading="lazy"/>

Now we'll only see inactive services.

We can also pipe a ```grep``` search to this command to find specific services.

For instance, here's how we'd search for the ```ssh``` service:

```
systemctl list-units --type=service | grep "ssh"
```

<img width="585" alt="8  grepping a systemctl service request" src="https://github.com/user-attachments/assets/b281c1c0-2571-4535-a337-21ee7048ed6f" loading="lazy"/>

Once we know which service we'd like to inspect, we can use the ```status``` command to view details.

We'll do this with the SSH service.

SSH (Secure Shell) is a networking protocol used for secure communication between devices. And there are typically two types of services when it comes to networking protocols. There's one for the client, and one for the server. 

We can view these differences by using the ```status``` command for ```ssh```, but tab autocompleting it before executing the command.

```
systemctl status ssh <tab autocomplete>
```

Using tab autocomplete will show us how there is ```ssh.service``` and ```sshd.service```.

<img width="588" alt="9  tab autocompleting systemctl status ssh" src="https://github.com/user-attachments/assets/aaa9edd9-43d9-4dec-ae67-acbb986039d0" />

The ```ssh.service``` allows us, as the client, to connect over SSH connections.

The ```sshd.service``` is the SSH daemon, which are like helper services that provide additional functionality. This one functions as a server. This means that the ```sshd.service``` allows other endpoints (clients) to connect to us with the SSH protocol.

So now let's actually look at the status of ```sshd.service```.

```
systemctl status sshd.service
```

We'll see the status information of the service.

We can see the activity status, PIDs, memory consumption, and a related logs at the bottom.

<img width="630" alt="10  systemctl status sshd service" src="https://github.com/user-attachments/assets/de09d93f-5916-4819-8358-06b3d32f3042" loading="lazy"/>

So we might want to do more than just inspect services.

Perhaps we want to interact with them. There are commands we can use with ```sudo``` to do this. For instance, we can ```reload``` a service.

This would be useful when we've made changes to a service's configuration files and want those changes to take effect (without interrupting the service by killing it).

```
sudo systemctl reload sshd.service
```

<img width="550" alt="11  reload sshd service" src="https://github.com/user-attachments/assets/cb4539c9-febd-4c91-91a0-6ec209188d65" loading="lazy"/>

The ```status``` command shows us logs associated with the reloading of the service.

We can also ```restart``` the service. This completely stops and interrupts the service for a brief moment, then starts it back up.

This is useful if a service is hung up.

```
sudo systemctl restart sshd.service
```

<img width="521" alt="12  restart sshd service" src="https://github.com/user-attachments/assets/8cbf96a4-3d0a-4320-8858-f0b701f7a49b" loading="lazy"/>

Previous logs aren't displayed immediately after a restart, whereas using the ```reload``` command retains the previous logs while appending the new ones related to it reloading. 

This means that using the ```restart``` command resets the service completely, as if starting from a fresh slate. 

We can also fully stop a service by using the following command:

```
sudo systemctl stop sshd.service
```

<img width="529" alt="13  stop sshd service" src="https://github.com/user-attachments/assets/2066624a-c409-4a48-9094-0d5546d1db3f" loading="lazy"/>

We can see how the service isn't running anymore.

And we can start it back up with the following command:

```
sudo systemctl start sshd.service
```

<img width="534" alt="14  start sshd service" src="https://github.com/user-attachments/assets/bba68768-d02b-4084-ac51-61e8ddf15b56" loading="lazy"/>

It's active and running again.

At this point, there are two final states to be aware of—```enabled``` and ```disabled```. These states determine startup behavior at boot. We need to use the ```list-unit-files``` subcommand to view this. The ```list-units``` focuses on displaying the state of units currently loaded into memory. This is good for seeing what's happening in real time. But the ```list-unit-files``` subcommand displays the unit files that exist on disk. This contains information on how a unit is configured (like whether or not it's enabled).

Let's first view enabled services, which will tell us which services will start at boot.

```
systemctl list-unit-files --type=service --all --state=enabled
```

<img width="650" alt="15  list only enabled services on system" src="https://github.com/user-attachments/assets/9b36ce05-014f-43a3-bbbe-791ad9136ca2" loading="lazy"/>

Quick command breakdown:

- ```systemctl```: The command-line tool for interacting with ```systemd``` system and service manager.
- ```list-unit-files```: This lists unit files instead of the actual running units.
- ```--type=service```: This flag specifies that only service units should be listed.
- ```--all```: This flag indicates that all unit files should be listed (including disabled, static, or generated units). 
- ```--state=enabled```: This flag further filters the list to include only service unit files that are enabled.

Once we see all the enabled services on the system, we can run a similar command to see the disabled ones.

This reveals which services do not start at boot.

```
systemctl list-unit-files --type=service --all --state=disabled
```

<img width="627" alt="16  list only disabled services on system" src="https://github.com/user-attachments/assets/6e7bd6d0-6745-4f05-8407-aaf6d3b1fe7e" loading="lazy"/>

Now we understand the basics of inspecting and interacting with services on the command line.

# Lab #15: Data Streams and Command Redirection

Data streams in Linux are like invisible highways that move data from one place to another.

They allow our computer to send and receive information between various programs and files. We need data streams because they help our Linux machine communicate efficiently. If we didn't have them, it'd be like trying to transfer water between locations without a pipe or hose—messy and inefficient.

Information wouldn't be able to flow smoothly between programs and files.

There are three main types of data streams in Linux:

- **Standard Input (STDIN)**: This is where data enters the system. We can type a command or feed data from a file. This is like water flowing into a pipe.
- **Standard Output (STDOUT)**: After the command processes the input data, it sends the result out through ```STDOUT``` to be displayed on the terminal screen (or saved). This is like water flowing out of the pipe on the other end.
- **Standard Error (STDERR)**: If something goes wrong with the data stream, the error message flows through ```STDERR``` and alerts us about the issue on the terminal screen. This is like a leak in the pipe, causing water to spill out and alert us to a problem.

Everything revolves around these streams of data.

To illustrate this, we can run the ```echo "hello"``` command.

The ```echo "hello"``` command functions as ```STDIN```. And the echoed response displays on our terminal screen through ```STDOUT```. 

<img width="510" alt="1  echo hello" src="https://github.com/user-attachments/assets/204a25b4-b47d-4601-850a-d798fc5b9ddd" loading="lazy"/>

Now we'll try inputting the same text with a command that doesn't exist. This will output an error statement through a ```STDERR``` data stream.

The terminal is capturing my keystrokes and filling the command line with ```STDIN```. But we won't get a valid output through the ```STDOUT``` data stream. Instead, we'll get an output with error information.

Both ```STDOUT``` and ```STDERR``` provide us output. However, ```STDOUT``` gives us valid output, whereas ```STDERR``` gives us error information in the output.

<img width="525" alt="2  echoed hello command with stderr" src="https://github.com/user-attachments/assets/40ed22d0-c262-4909-a648-0d3e36736684" loading="lazy"/>

At this point, we have a basic understanding of data streams.

But the real magic happens when we manipulate these data streams. This allows us to control the flow of data—where data goes, how it's processed, and how to respond to issues. And we can do this by using redirectors.

We've used a few redirectors in previous labs. So let's review them and add additional ones to our arsenal:

- ```>```: This redirects ```STDOUT``` somewhere else (commonly a file).
- ```>>```: This appends ```STDOUT``` somewhere else (commonly a file).
- ```<```: This redirects ```STDIN``` from a file or another input source.
- ```<<EOF```: This redirects ```STDIN``` from multiple lines of text until the ```EOF``` marker is reached.
- ```|```: This redirects ```STDOUT``` as ```STDIN``` for the subsequent set of commands. 

Let's walk through each redirector and observe how data streams work.

To reinforce concept, we'll start with a command we've already used multiple times:

```
echo "hello" > hello.txt
```

<img width="805" alt="3  echo hello with redirector" src="https://github.com/user-attachments/assets/61b6fa29-a459-441a-ba63-da5099fa2f58" loading="lazy"/>

So here we're seeing that ```>``` takes the text "hello"—the ```STDOUT``` from ```echo "hello```—and redirects it into a file named ```hello.txt```. 

We can confirm that the ```STDOUT``` was redirected into the ```hello.txt``` file by using the ```cat``` command on it.

<img width="796" alt="4  cat hello txt" src="https://github.com/user-attachments/assets/115ea21e-aa39-4880-9399-2be9a2e5098c" loading="lazy"/>

And in the same way, we can use the ```>>``` redirector to append ```STDOUT``` to the same ```hello.txt``` file.

<img width="789" alt="5  appending redirector" src="https://github.com/user-attachments/assets/dc4a9416-84bb-4a9f-b647-fae13746f2b5" loading="lazy"/>

Let's reinforce these concepts by playing with the ```cat``` command a bit.

So ```cat``` normally reads a file as input and sends it to ```STDOUT```, which displays on the terminal screen. But what happens when we run ```cat``` without a file name? 

If we don't provide a file name, ```cat``` doesn't know what to display, so it switches into "waiting mode." It'll start listening for input from the keyboard (```STDIN```). This is happening because the ```cat``` command is designed to work with data streams. And without a file to use as input, it prompts us to provide input directly from the keyboard. 

It's like we're telling the terminal, *"I want you to read something out loud."* But it responds by saying, *"Okay, well I don't have a file to read. Tell me what to read!"* 

The terminal prompts us to start typing so it can use it as ```STDIN```. Then the terminal will repeat our words back to us immediately. This is the ```STDOUT```.

<img width="808" alt="6  cat without STDIN" src="https://github.com/user-attachments/assets/5948862e-2c22-449a-93d4-1d80cdac199b" loading="lazy"/>

We can enter ```Ctrl + C``` to end the input/output session.

Now let's add ```> textfile.txt``` to the ```cat command:

```
cat > textFileForat.txt
```

Here's what'll happening.

I'm basically telling the terminal: *"This time, don't just repeat the text through ```STDOUT```. Redirect the ```STDOUT``` to another file instead."* And it responds by saying: *"Sure. But once again, I'll need input that I can redirect. So tell me what you want redirected to this other file."*

The terminal will then prompt us for text to use as ```STDIN```. And instead of just repeating the text through ```STDOUT```, it'll redirect it to another file. 

We can confirm this by looking inside this new file and noticing the text that got redirected through ```STDOUT```.

<img width="926" alt="7  cat redirected into new file" src="https://github.com/user-attachments/assets/0926ce74-da7c-4348-960e-2e1fc3c7eba9" loading="lazy"/>

Next let's look at the ```<``` redirector.

We'll use the ```wc -l``` command to illustrate it. ```wc``` is a command that counts lines, words, and characters from a file (or standard input). The ```-l``` flag specifies that we want to count the number of lines.

So if we ran ```wc -l``` against our ```hello.txt``` file, we'll see how many lines are in it.

<img width="911" alt="8  wc -l command" src="https://github.com/user-attachments/assets/46bc199c-43b6-4434-b2a9-9c1a85298b77" loading="lazy"/>

And we can use the ```<``` operator to achieve the same result:

```
wc -l < hello.txt
```

Here the ```hello.txt``` file serves as the ```STDIN```. And this input is being redirected to the ```wc -l``` command. This command then calculates the number of lines in ```hello.txt```, sends it to ```STDOUT```, and displays the result on the terminal screen.

<img width="933" alt="9  wc -l with redirector" src="https://github.com/user-attachments/assets/08189a9e-ae8f-40d4-a342-c052d64746fd" loading="lazy"/>

The next redirector is ```<<EOF```. 

This creates a "Here Document," which allows us to enter multiple lines of text that can be used as ```STDIN```. And it'll read every line of input until the ```EOF``` delimiter is used (marking the "end of file"). 

So for example, we can run the same ```wc -l``` command against this new operator.

<img width="512" alt="10  EOF redirector" src="https://github.com/user-attachments/assets/abe00720-feb1-4b45-bdf7-08fb618763bc" loading="lazy"/>

Here the block of text we entered serves as the ```STDIN```. And this input is being redirected to the ```wc -l``` command. This then calculates the number of lines in our "Here Document," sends it to ```STDOUT```, and displays the result on the terminal screen.

We can use the same operator with the ```cat``` command.

The block of text serves as ```STDIN``` and gets sent to the ```cat``` command.

Then we see the same text—everything before EOF—get sent to ```STDOUT``` and display it on the terminal screen.

<img width="519" alt="11  cat command with EOF redirector" src="https://github.com/user-attachments/assets/83a9b4fd-1b1a-40fe-8d10-23dc3551c582" loading="lazy"/>

Great.

Now let's say we want to redirect error messages to a new file. That way, we can troubleshoot or debug the issue at a future time.

We can ```cat``` a file that doesn't exist to illustrate this. Then we can try to redirect it into a new file, similar to how we've been doing it.

```
cat aNonexistentFile > error.log
```

<img width="508" alt="12  redirecting error message with another error" src="https://github.com/user-attachments/assets/e1469a00-c60d-47db-821a-76e8b97b1db4" loading="lazy"/>

Despite using the redirector, we still get an error message.

This happens because the ```>``` only redirects ```STDOUT```. And we're currently trying to redirect a ```STDERR```.

To properly redirect ```STDERR```, we need to know that each data stream has a number representing it:

- STDIN = 0
- STDOUT = 1
- STDERR = 2

So we can successfully redirect ```STDERR``` by throwing a ```2``` in front of our operator.

```
cat aNonexistentFile 2> error.log
```

If we ```cat``` the ```error.log```, we'll see that it worked.

<img width="571" alt="13  cat an error log" src="https://github.com/user-attachments/assets/474a922b-bc95-4a5f-b8ec-7ea472d2c8f5" loading="lazy"/>

The same principle applies for appending standard error messages.

```
cat aNonexistentFile 2>> error.log
```

<img width="586" alt="14  appending error message into error log" src="https://github.com/user-attachments/assets/fc775bda-61f7-43d9-9d92-df34f4d00bd7" loading="lazy"/>

Now notice how there are two lines of errors when we ```cat``` it.

Sometimes we may want to redirect output or errors into oblivion. This is useful if we want to remove clutter from our terminal or suppress unnecessary information. And we can do this by redirecting ```STDOUT``` or ```STDERR``` into a file named ```/dev/null```.

```/dev/null``` acts as a black hole for data.

So, if we were to redirect an error message to this file, it'd get immediately discarded.

```
cat aNonexistentFile > error2.log 2> /dev/null
```

Here's a quick command breakdown:

- ```cat aNonexistentFile```: This tries to display the contents of ```aNonexistentFile```, which doesn't exist.
- ```> error2.log```: This redirects ```STDOUT``` from the previous command to ```error2.log```. Even though the file doesn't exist, this part of the command still runs and creates a file named ```error2.log```. But nothing gets redirected to it because there was nothin in ```STDOUT``` from the ```cat``` command. For that reason, ```error2.log``` remains empty.
- ```2> /dev/null```: This redirects standard error messages (```STDERR```) to ```/dev/null```. This will discard all error messages. 

<img width="684" alt="15  redirecting stdout and stdin with dev null" src="https://github.com/user-attachments/assets/bd92073d-b0b8-4521-8e0f-8c248cdace21" loading="lazy"/>

Notice how ```error2.log``` exists, but there's no text in it.

Finally, we'll wrap up this lab with the ```|``` operator. We can use it to redirect ```STDOUT``` as ```STDIN``` for subsequent commands, much like a conveyer belt.

So, for example, we could get a screenshot of our current system processes and pipe that ```STDOUT``` to a command like ```less``` to read it.

```less``` is a terminal pager for viewing data one screen at a time. I also keeps the terminal uncluttered by not retaining the output once we exit.

```
ls /proc | less
```

<img width="555" alt="16  list proc files with less pager" src="https://github.com/user-attachments/assets/8457fd50-97ed-4633-a057-f5e06534eadb" loading="lazy"/>

That's a pretty simple use case for the ```|``` redirector.

But we can use multiple pipe operators to manipulate data in more sophisticated ways. For instance, let's say we wanted to see all the users on our system. 

Remember that this information exists in ```/etc/passwd```.

<img width="647" alt="17  cat etc passwd" src="https://github.com/user-attachments/assets/22ff1ab8-dc3b-46be-91af-b01b99e22a07" loading="lazy"/>

There's a lot of clutter. 

So we can use the ```cut```command to filter out any unnecessary information. All we need to do is specify a delimiter and the field we want to view.

```
cat /etc/passwd | cut -d : -f 1
```

Here the ```-d :``` flag specifies that we want to separate text by the ```:```. The ```:``` is the delimiter. And the ```-f 1``` flag specifies that we want to view the first field of text that comes before ```:```. 

The first field is the user column.

<img width="578" alt="18  cat etc passwd with cut command" src="https://github.com/user-attachments/assets/9783c475-320f-424c-93d1-76ae7b3cdf6c" loading="lazy"/>

Now we only see a list of users.

But let's say we also want to view these users in alphabetical order. We can pipe the ```sort``` command to it to accomplish this.

```
cat /etc/passwd | cut -d : -f 1 | sort
```

<img width="499" alt="19  read sorted list of users" src="https://github.com/user-attachments/assets/12304cee-7c70-4366-b324-e2e1f13c9524" loading="lazy"/>

Notice how all the users are sorted now.

We can also redirect this entire output into a new file called ```users.txt```.

```
cat /etc/passwd | cut -d : -f 1 | sort > users.txt
```

<img width="689" alt="20  redirect sorted list of users to new file" src="https://github.com/user-attachments/assets/4536fee1-82e9-422f-9e93-4b8eb903335e" loading="lazy"/>

Now we can investigate the user names at a later time.

But instead of having a list of names, let's just get a count of how many users are on the system. All we need to do is pipe ```wc -l``` to the entire command.

Then we can redirect that output into a new file named ```numberOfUsers.txt```.

```
cat /etc/passwd | cut -d : -f 1 | sort | wc -l > numberOfUsers.txt
```

<img width="762" alt="21  redirect number of users into new file" src="https://github.com/user-attachments/assets/46e48af0-487d-4a45-b9fe-591b6c3533bc" loading="lazy"/>

Now when we ```cat``` our new file, we'll see how there are 48 users on the system.

That concludes our lab on data streams!

# Lab #16: Create Scheduled Tasks with ```Crontab```

Scheduled tasks in Linux automates repetitive actions.

The key tool for doing this is ```Cron```, which is a daemon (background service) that runs tasks at specific times. ```Cron``` refers to the Greek word "chronos," indicating its role in time-based job scheduling. And we can use the ```crontab``` command to interact with the configuration file that stores these scheduled tasks. 

This saves us time by handling tasks like backups, updates, and routine jobs. 

Let's get started by opening up a terminal.

<img width="531" alt="1  whatis crontab" src="https://github.com/user-attachments/assets/02fb48b4-1bce-40dc-b736-345f14957e72" loading="lazy"/>

We're going to open a ```crontab``` file and add a scheduled task.

But before doing this, we'll want to specify the text editor to be used for editing the configuration file. We can use the ```select-editor``` command to do this.

A list of options pop up. For simplicity, choose the ```nano``` editor.

<img width="541" alt="2  select-editor command" src="https://github.com/user-attachments/assets/efbd6b2d-fff2-4858-a84f-6c66ca84d008" loading="lazy"/>

Great. Now we can open up and edit the configuration file by using the ```crontab``` command with the ```-e``` flag.

<img width="551" alt="3  crontab -e" src="https://github.com/user-attachments/assets/550e9b9b-763a-4c81-a694-a5c1afe1e099" loading="lazy"/>

We'll see some lines that start with a ```#```.

These are "comments" and won't be interpreted as scheduled tasks. 

<img width="800" alt="4  crontab file comments" src="https://github.com/user-attachments/assets/122e7a8b-2a2d-43da-b39e-179021965bfb" loading="lazy"/>

Now we can go to the bottom of the file to enter text.

Setting a scheduled task requires us to enter special symbols, followed by the command we want to automate on the system. These special symbols represent values for minute, hour, day of the month, the month, and the day of the week.

To illustrate this, we'll only use asterisks to represent the time. This means that text will get appended into the file every minute.  

Then we'll run a command to append text into a file.

```
* * * * * echo "hello there" >> /home/Colton/hellothere.txt
```

<img width="800" alt="5  crontab task for appending text" src="https://github.com/user-attachments/assets/089be993-01bb-4264-9bf7-f1eb223a855b" loading="lazy"/>

Let's exit and save the file. 

Quickly use the ```date``` command to get the current time stamp.

After a couple minutes, we'll come back to the terminal and check the file.

<img width="828" alt="6  scheduled task in action with echo hello there" src="https://github.com/user-attachments/assets/eb8c985b-4d6e-4a83-8994-a06f4a31b86a" loading="lazy"/>

We'll notice 3 lines of text appear. This tells us that our scheduled task has ran three times already.

So if we want to view all the scheduled tasks of the current user without editing them, we can use the ```-l``` flag. 

<img width="566" alt="7  crontab -l command" src="https://github.com/user-attachments/assets/d3085f75-02b0-4433-9dc8-095b815653c6" loading="lazy"/>

At the bottom we'll see our scheduled task. 

Now let's say we want to delete our scheduled task. All we need to do is use the ```-r``` flag with ```crontab```. 

<img width="526" alt="8  crontab -r command" src="https://github.com/user-attachments/assets/f944a554-713e-4271-a0f5-bb32ee99ed19" loading="lazy"/>

Notice how our cron table no longer exists. Another approach is to just use the ```-e``` flag again, delete the scheduled task entry, then save the configuration file.

Moving on.

Let's run a more sophisticated scheduled task. 

We'll use this task to dive deeper into "cron expressions." These are the first five special symbols in a crontab entry that define the schedule or time at which the task should run. 

First, let's look at the order of these cron expressions:

- The first entry represents the minute.
- The second entry represents the hour.
- The third entry represents the day of the month.
- The fourth entry represents the month.
- The fifth entry represents the day of the week. 

```
* * * * * command-to-be-executed
- - - - -
| | | | |
| | | | +---- Day of the week (0 - 6) (Sunday=0, Monday=1, ..., Saturday=6)
| | | +------ Month (1 - 12)
| | +-------- Day of the month (1 - 31)
| +---------- Hour (0 - 23)
+------------ Minute (0 - 59)
```

*Side note: Use the [crontab calculator](https://crontab.guru/) to quickly figure out the correct timings.*

Then we have special symbols:

- ```*```: The asterisk is a wildcard symbol that represents "every" possible value for that field. So for ```* * * * *```, this means the command runs every minute of every hour, every day, every month, and every day of the week. 
- ```/```: The slash is used to specify step values or intervals. So ```*/5 * * * *``` would mean "every 5 minutes." 
- ```,```: The comma allows us to specify multiple values in a single field. So ```0 8,12,16 * * *``` would mean the command runs at 8AM, 12PM, and 4PM every day.
- ```-```: The hyphen defines a range of values. So ```0 9-17 * * *``` would run a command every hour between 9AM to 5PM.
- ```?```: The question mark is used in the ```day of the month``` and ```day of the week``` field to mean "no specific value." So ```0 12 10 * ?``` runs a command at 12PM on the 10th of every month, regardless of what day of the week it is. 

That's a lot of information at once, so we'll run through our more sophisticated scheduled task.

Let's say we want to automatically perform a backup of our home directory:

- We want to perform this at 6AM every day. 
- We want to put that backup in the ```var``` backups folder.

How would we schedule this? 

First, we'll want to make a directory inside of the ```var``` folder to store the backups. This folder requires ```sudo``` privileges to access. 

So we'll want to first switch to the root user by using ```sudo su```. If we don't specify a user account after ```su```, then it'll default to the root user.

<img width="523" alt="9  sudo su command" src="https://github.com/user-attachments/assets/0e2f1e5b-41a7-41e8-9745-046868941f5e" loading="lazy"/>

Once we do that, we'll want to make a directory inside of ```/var/backups/```:

```
mkdir /var/backups/coltonHomeBackups
```

<img width="863" alt="10  mkdir for home backups" src="https://github.com/user-attachments/assets/44236d06-779d-4aa0-9752-0cf797081bed" loading="lazy"/>

Now the directory exists. 

Let's open up ```crontab``` and schedule the task.

We want to perform this at 6AM every day. So here's what each entry looks like:

- First Entry: The minute field determines the exact minute of the hour when the task should run. It'll range from 0 to 59. In our case, setting it to ```0``` means the task will run at the start of the hour.
- Second Entry: The hour field determines the exact hour of the day when the task should run. It'll range from 0 to 23. In our case, setting it to ```6``` means the task will run at 6AM.
- Third Entry: This field specifies which day of the month the task should run. Since we want it to run every day of the month, we'll use the asterisk ```*```.
- Fourth Entry: This field specifies which months the task should run. Since we want it to run every month, we'll use the asterisk ```*```.
- Fifth Entry: This field specifies which days of the week the task should run. Since we want it to run every day of the week, we'll use the asterisk ```*```.

<img width="631" alt="11  crontab cron expressions" src="https://github.com/user-attachments/assets/15f83e13-3712-4e61-9c4b-e710ddcb5f40" loading="lazy"/>

Now we need to add a command. 

We want to copy all files and directories from our home directory. Then we want to put it into a new file. So we can use the ```cp``` command for that.

Then we'd add the source and destination path.

We'll also add the ```-a``` flag. This ensures that we get a full backup, as it includes all file attributes (such as timestamps, permissions, and ownership). It also recursively copies directories and their contents. 

Here's what the full command will look like:

```
cp -a /home/Colton/* /var/backups/coltonHomeBackups
```

<img width="600" alt="12  command for scheduled backup" src="https://github.com/user-attachments/assets/ac0f7865-9bbd-4e8b-8e52-b319fbb03d34" loading="lazy"/>

The ```*``` after ```/home/Colton/``` ensures I'm capturing all files and directories at that source path.

Great. Let's add two more scheduled tasks to illustrate a few concepts. 

First, let's create a scheduled task that does a backup "every minute." We'll use the ```* * * * *``` cron expressions for this. That way, we can view what a backup actually looks like (instead of waiting till 6AM).

I'll create a new directory. Then I'll enter the following command in our ```crontab``` configuration file:

```
* * * * * cp -a /home/Colton/* /var/backups/coltonHomeBackupsEveryMinute
``` 

<img width="589" alt="13  scheduled task every minute for backup" src="https://github.com/user-attachments/assets/69f6f4a8-f0af-467f-ae9b-2de037a240cc" loading="lazy"/>

Then I'll create a third scheduled task without the ```-a``` flag, just so we know how important it is to use the "archive" option.

I'll create a new directory and enter the following command in our ```crontab``` configuration file:

```
* * * * * cp -a /home/Colton/* /var/backups/coltonHomeBackupsWithoutArchiveFlag
```

<img width="583" alt="14  scheduled task for backup without archive option" src="https://github.com/user-attachments/assets/aab10252-943d-4563-adfd-92040057ecd9" loading="lazy"/>

Great. Save the configuration file and let's wait a few minutes.

After a couple minutes have gone by, let's see if our backups worked. We'll list out the files and directories in our backups scheduled for "every minute."

<img width="888" alt="15  scheduled backups in crontab" src="https://github.com/user-attachments/assets/962e7367-3f1f-4162-9a44-4860477424bf" loading="lazy"/>

As you can see, both backups worked. And the backups without the ```-a``` flag don't back up any of the directories. This is why the ```-a``` flag is so important when doing backups in Linux.

So now we have a full running backup of our home directory so we don't lose our data. 

# Lab #17: Software Administration with Package Managers

Linux handles software management a bit differently than Windows. 

Instead of downloading executable files, Linux downloads "packages" managed by a "package manager." A package is a bundle of software files and code. It includes everything needed to run a piece of software. It's like buying a DIY furniture piece from IKEA. 

Inside the IKEA box, you'll find all the parts, instructions, and tools to assemble the piece of furniture.

Package managers are tools that automate the process of finding, downloading, installing, and removing software packages. 

There are multiple package managers out there. But regardless of which one you use, they exist to make sure everything in the package is installed correctly and works as expected. It's like asking a knowledgeable IKEA clerk which furniture set best fits your needs and where to find it. 

Similar to a helpful clerk, the package manager helps us find the right packages, checks that we've got all the required dependencies, and makes sure we don't install incompatible or unnecessary files. 

At this point, we have to wonder where the package manager is grabbing packages from.

And this is what repositories are. They're servers or databases maintained by the Linux community and developers. They keep the software packages safe, up-to-date, and compatible with our Linux machine. These repositories store the software packages and make them available for download.

Similarly, in order to get IKEA furniture to your local warehouse, they need to request it from a distribution center. This distribution center is where employees manage and oversee inventory.

In our lab, we'll use the ```apt``` package manager.

This stands for "advanced package tool." And it's a command line interface for managing software packages.

<img width="795" alt="1  apt man pages" src="https://github.com/user-attachments/assets/ef1e4eef-59b5-4749-8217-16e337f78517" loading="lazy"/>

Keep in mind that software management is an administrative task. 

And administrative tasks typically requires us to use ```sudo``` permissions. 

<img width="688" alt="2  apt update without sudo" src="https://github.com/user-attachments/assets/5fb10ba6-cfb2-4a0a-80c8-9f1dd21bbdf0" loading="lazy"/>

That being said, let's talk about ```apt update`` as a command. 

It's a good one to start with. When we run it with ```sudo```, we'll see a list of the latest software package versions. ```apt``` is fetching this information from the repositories. 

<img width="675" alt="3  sudo apt update" src="https://github.com/user-attachments/assets/ca6c213a-c3ae-4dab-adc3-d621ccd7de62" loading="lazy"/>

In the example above, here's a breakdown of the following line: ```Get:2 http://azure.archive.ubuntu.com/ubuntu focal-updates InRelease [128 kB]```:

- ```Get:2```: This indicates that this is the secon thing our system is fetching.
- ```http://azure.archive.ubuntu.com/ubuntu```: This is the website where the update is coming from. It's the repository or server that stores the package.
- ```focal-updates```: This is the name of the specific update. This refers to a section in the repository that contains updated software packages. 
- ```InRelease```: This tells us that the updates are being released now and are ready to be installed. Generally speaking, this column indicates the nature or status of the update being fetched.
- ```[128 kB]```: This shows the size of the update in kilobytes.

This is an important command because it keeps us informed about the latest software packages available for us to install or update. It's like asking the IKEA clerk for the latest catalogs of available items.

Once the command is completed, we can run ```apt list --upgradable``` to see a list of upgradable software packages. 

<img width="875" alt="4  apt list --upgradable" src="https://github.com/user-attachments/assets/bceea161-9497-48a5-a4b6-6103393f4c57" loading="lazy"/>

We'll see a list of all the specific installed packages on our system that have newer versions available.

This is like highlighting items inside the IKEA catalogs that you already own. Once you show the clerk, they'll give you a list of all the newest models available for those specific items you already have at home.

Since we're just searching for software packages, we don't need to use ```sudo```. 

Next let's say we want to search for a specific software package available, like ```zim```. ```zim``` is a graphical text editor based on wiki technologies.

We'd use the following command to search for it:

```
apt search zim
```

We'll see a list of software packages that match this search request, where we can find the specific package associated with ```zim```.

<img width="550" alt="5  apt search for zim" src="https://github.com/user-attachments/assets/cc60d8f1-4aa5-4b50-a92f-5c310eb4e535" loading="lazy"/>

This is like asking the IKEA clerk for more information about a specific type of furniture that you like. They'll flip through the catalog with you, pointing out all the relevant furniture pieces that match your inquiry. 

The ```apt search``` command is useful for quickly locating a specific software package we want.

Now let's say we want to do a full upgrade of the system.

This means we'd upgrade all of our existing software to the latest versions. This is everything we saw in the ```apt list --upgradable``` command.

We'd just run the following command:

```
sudo apt upgrade
```

We'll see a large amount of requests going out to the centralized repository links and retrieving all the latest packages. 

<img width="795" alt="6  sudo apt upgrade" src="https://github.com/user-attachments/assets/e8d78951-a688-4370-876c-9f345157c9f3" loading="lazy"/>

Once everything is fetched, we'll see everything get extracted (similar to uncompressing a zipped file).

At that point, ```apt``` uses a local database to check the versions and metadata of the installed packages.

Then the files will get unpacked from the packages and put into various folders on disk.

<img width="695" alt="7  sudo apt upgrade progress" src="https://github.com/user-attachments/assets/2acc3b3a-f5a6-4189-bc96-1e13780bcd77" loading="lazy"/>

Depending on the system you're using, a full upgrade could take a very long time.

This is like deciding to replace all your old IKEA furniture with the upgraded models that the store clerk told you about. If you have a lot of old furniture, this process may take awhile.

**An important side note:** When we're deploying our own custom Linux machine, it's a good idea to update and upgrade the software packages once it's initialized.

It's a good habit. A common command to do this all at once is:

```
sudo apt update && sudo apt upgrade -y
```

<img width="690" alt="8  apt update and upgrade at once" src="https://github.com/user-attachments/assets/adbd304c-d185-4909-b20e-5cff02fe1cbf" loading="lazy"/>

Moving on.

So how does our package manager know where to retrieve software packages from?

We can find this information in the ```/etc/apt/sources.list``` file. And we can use the following ```apt``` command to open the file in a text editor:

```
sudo apt edit-sources
```

<img width="795" alt="9  edit apt sources" src="https://github.com/user-attachments/assets/ff844682-80fa-42b1-9092-e95f11fade28" loading="lazy"/>

We'll see URLs listed throughout the file. 

These are the URLs that point to the repositories where the package manager retrieves software packages from. It's not generally recommended to modify these repository links, as this can cause broken dependencies, security vulnerabilities, and issues with package updates and installations. It'd be like using an unreliable distribution center to ship IKEA furniture to your local warehouse. There could be issues with quality or the wrong items being sent.

Let's exit the file.

Next we'll install some software using our package manager. 

We'll do this with the ```zim``` tool mentioned earlier. We know it exists because we used the ```apt search``` command on it earlier.

Since we confirmed it's available for installation, we can run ```apt install```:

```
sudo apt install zim
```

<img width="900" alt="10  sudo apt install zim" src="https://github.com/user-attachments/assets/cd95a3f7-23a1-4aea-9da1-807005f90964" loading="lazy"/>

The package manager will reach out to the proper repository and install it on our system.

This is like finding a piece of IKEA furniture you want to add to your home. So you ask the clerk to help you locate it, purchase it, then set it up at home.

We can confirm it works by opening up a new terminal and running ```zim```.

<img width="850" alt="11  open zim" src="https://github.com/user-attachments/assets/540d80ec-b0d3-4c9a-80b9-e4ecae3d8b04" loading="lazy"/>

The new text editor will pop up, which allows us to enter more feature-rich text.

But we don't actually need ```zim``` on our system. So let's uninstall and delete it.

There are two commands to do this:
- ```sudo apt remove zim```: This removes the ```zim``` software package data. But it leaves behind the user configuration files in case we want to reinstall the package later. This is like deciding to return a piece of IKEA furniture—but you keep the assembly instructions, in case you change your mind later and buy it again.
- ```sudo apt purge zim```: This completely removes the ```zim``` package from our system—the software package data, and the user configuration files. This is like deciding to get rid of a piece of IKEA furniture and all related items, leaving no trace behind. 

We want to purge our system of ```zim```.

So let's do that now.

<img width="900" alt="12  sudo apt purge zim" src="https://github.com/user-attachments/assets/1d12ca35-30c3-4dac-9ab9-0acd3e9b25b0" loading="lazy"/>

Now it's completely removed from our Linux machine.
