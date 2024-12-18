# Linux OS Administration
# Table of Contents
- [Introduction](https://github.com/itscoltonhicks/Linux-OS-Administration/blob/main/README.md#introduction)

- [Setting Up Our Linux OS Lab Environment](https://github.com/itscoltonhicks/Linux-OS-Administration/blob/main/README.md#Setting-Up-Our-Linux-OS-Lab-Environment)
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
