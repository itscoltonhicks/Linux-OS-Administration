# Linux OS Administration
# Table of Contents
- [Introduction]
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

But this only gives us the CLI. We still need to add the XFCE graphical desktop to it, so we'll want to remotely access our Linux VM and add the XFCE packages to it. 

We can access our terminal by using the ```ssh``` protocol.

```
ssh <username>@<IP Address>
```

Provide the password once prompted.

<img width="600" alt="7  ssh into linux" src="https://github.com/user-attachments/assets/62b85504-792d-4729-85b1-6c46c1a3f320" loading="lazy"/>
