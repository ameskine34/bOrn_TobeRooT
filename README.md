# bOrn_TobeRooT
# basics

VIRTUALIZATION ::

allows the creation of virtual versions of physical resources; AND it is the process of using software to simulate hardware resources, enabling a single physical machine to run multiple virtual environments.

### **Benefits of Virtualization**

1. **Resource Optimization**:
    - Utilizes physical hardware more efficiently by running multiple VMs on a single machine.
2. **Isolation**:
    - VMs operate independently, providing fault and security isolation between environments.
3. **Flexibility**:
    - Easier to scale and manage workloads by dynamically allocating resources.
4. **Cost Savings**:
    - Reduces the need for physical servers and hardware.
5. **Portability**:
    - Virtual machines can be easily migrated between different host systems.

### **Real-World Applications**

1. **Development and Testing**:
    - Isolated environments for coding and testing applications.
2. **Disaster Recovery**:
    - Quick restoration of systems using snapshots and backups of virtual machines.
3. **Server Consolidation**:
    - Reducing the physical server count while maintaining capacity.

VIRTUAL ENVIRONMENTS : 

is a container , Each environment is independent, preventing conflicts between different software versions or dependencies. changes in one virtual environment do not effect others or the host system.

CHARACTERISTICS of virtual environment :

 **Isolation [avoid conflict between V.E] / Self-Containment [All required dependencies, libraries, and configurations are packaged within the environment which ensures consistency ] / Portability [can be moved between machine] / Scalability [we can allocate dynamically cpu memo …];**

VIRTUAL BOX :

open source virtualization software It enables users to run multiple operating systems (known as "guest OS") on a single physical machine (known as "host OS").

UTM :

is a virtualization tool designed specifically for macOS and iOS. UTM is native HYPervisor framework apple;

VirtualBox Limitations on macOS::::: VirtualBox  is not always optimized for macOS , particularly with recent macOS versions that enforce stricter security measures. 

VirtualBox does not natively support iOS, meaning you can't use it to run virtual machines directly on iOS devices.

1. **Container:**

Container virtualization is a lightweight form of virtualization that allows applications to run in isolated user spaces called containers while sharing the same operating system (OS) kernel.

1. **Virtual machine :**

Unlike traditional virtual machines (VMs), which emulate entire operating systems.
 

![Screenshot](image/Screenshot%20from%202024-12-22%2018-45-21.png)

docker is a container (instead of taking the hole operating system) so you take only the package that will contain docker image and when we run the image the container is on. and work with **docker engine**

 **Type 1 Hypervisor: Advantages and Disadvantages**

**** Type-1 hypervisor runs directly on hardware and doesn’t require any operating system. mostly used in business environments to virtualize company services. A Type-1 hypervisor is an operating system. Microsoft Hyper-V is often listed as a Type-1 hypervisor, which is true, but other applications besides VMs can run on it. That’s why some people call Hyper-V Type 1.5 or hybrid.

**Advantages:**

**Best performance : cuz it run the hardware directly;**

**High security,** as no other applications are running on the hypervisor directly.

**High stability,** as no other services or applications interfere with hardware;

### Disadvantages:

- Type 1 hypervisors are more complicated to deploy and manage than Type 2.
- Some hypervisors require hardware components from an approved hardware compatibility list.

![Screenshot](image/Screenshot%20from%202024-12-25%2012-18-33.png)

**Type 2 Hypervisor: Advantages and Disadvantages :**

Type-2 hypervisor runs on top of supported operating systems and uses the OS’s drivers to communicate with the hardware. Oracle Virtual Box, QEMU and VMware Workstation are examples of Type-2 hypervisors. Actually, the hypervisor of Type-2 runs inside OS as other applications and shares resources with them.

### Advantages:

- **Hardware-agnostic**, modern Type-2 hypervisors can run on any hardware, which is supported by the host OS.
- **Easy to install and manage**. It is installed as a normal application.

### Disadvantages:

- Lower performance than with Type-1, because of resource sharing with other applications and using hardware resources via the host OS.
- **Less secure and stable**. Crash of any other application may crash host OS.

![Screenshot](image/Screenshot%20from%202024-12-26%2009-36-24.png)

**BARE-METAL HYPERVISOR :**

bare-metal (Type 1) hypervisor runs directly on the hardware and acts as a lightweight operating system (how : Directly controlling hardware resources (CPU, memory, I/O) / Scheduling and allocating these resources to guest operating systems ). allows multiple guest operating systems to run independently on the same physical machine.

**kernel : is a computer program (**set of instructions written by assembly and c language for computer to execute**) at the core of a the computer’s operating system has control over everything in the system (software and hardware).**

**DEBIAN** :

is a lunix distribution that : is a complete operating system package built on top of the Linux kernel. 

Here are the key components that make up a Linux distribution:::

1/ The Linux Kernel 2/ Package Management System(Tools for installing, updating, and removing software <> Examples include APT (used by Debian/Ubuntu)) 3/ Desktop Environment 4/ Pre-installed Software.

DEBIAN VS ROCKY :

DEBIAN  afford simple installation process and comprehensive documentation. ensuring a beginner-friendly graphical interface. its package manager (`apt`);

ROCKEY aimed more at enterprise environments (focused on enterprise applications) and users familiar with the Red Hat (destro of operating system) ecosystem.

SELinux (Security-Enhanced Linux):

 is a Linux kernel security module that provides a mechanism for enforcing mandatory access control (MAC) policies. closely associated with **Red Hat-based distributions**, such as **Rocky Linux**, **Red Hat Enterprise Linux (RHEL)**, **Fedora.**

**AppArmor** : (Application Armor)  It focuses on confining programs to a set of predefined capabilities, helping to limit potential damage from 
vulnerabilities or exploits.

AppArmor enforces security policies that restrict(limit) programs' access to system resources like files, networks, and other capabilities

Apparmor  type1: enforce mode (block from the beginning the starting of the app that will cause an issue);

type2 : complain mode : the app runs if a potential issue appear it give message ;

LVM (logical volume management ) allow us more flexibility on disk management compared to traditional partitioning methods. It abstracts physical storage. + resize and managed without fixed partition.

- **Physical Volumes (PVs):** These are the actual storage devices or partitions (e.g., `/dev/sda1`). They **are physical disks and partitions** (block device) of the hard drive with **LVM** file system.
- **Volume Groups (VGs):** A pool of storage created by combining one or more PVs.
- **Logical Volumes (LVs):** The "virtual partitions" carved out from the VG.

benefits ::::

- **Dynamic resizing:** You can increase or shrink LVs as needed without rebooting.
- **Snapshots:** Useful for backups or testing system changes.
- **Efficient storage utilization:** Combine multiple storage devices into a single logical group.

![Screenshot](image/Screenshot%20from%202024-12-25%2015-47-52.png)

# added infos about LVM:

To display information about volume groups such as `rootvg` and `datavg`

commands to displays infos 

 lsvg rootvg  /   lsvg datavg

To display information about physical volumes:

 lsvg -p rootvg  /   lsvg -p datavg

To display information about logical volumes:

 lsvg -l rootvg  /   lsvg -l datavg

what is apt(advanced package tool) package : 

APT (command line) is like a Play Store for Linux - it connects to repositories that contain pre-packaged applications. lower-level package manager (like write you to tell details) that other tools (including aptitude) are built upon

When you use APT, it:

1. Finds the package in these repositories
2. Downloads it and any required dependencies (a message appear and tell you that you don t have this dependencies ).
3. Handles the installation process automatically

what is aptitude ():

APTITUDE is Unix package management system It offers more advanced dependency resolution and package management features compared to APT.

REQUIRED Dependencies are other software packages that a program needs to function properly. For example:

When you install a web browser like Firefox, it might need:

- Graphics libraries to display content
- Audio libraries to play sound

Dependency resolution: Process of figuring out and managing all the additional software packages needed for a program to work.

# mount point for the partition :

**mount point** refers to the location within the directory hierarchy where the contents of a partition are made accessible.

1///The `/boot` directory in a Linux system contains the essential files required to boot the operating system.

**Bootloader Files / Linux Kernel ….**

2/// A /swap file is a special file on a storage device that serves as an extension of a system’s physical RAM (Random Access Memory).

3/// The **`/var` directory** in a Linux system is a part of the standard directory structure defined by the **Filesystem Hierarchy Standard (FHS)**. It is short for **"variable"** and is used to store files that are expected to change frequently during the normal operation of the system. These include logs, spool files, caches, and other dynamic content.

4/// . The name **`/srv`** stands for **"service"** and is designed to hold files served by the system, such as web content, FTP data, or other service-specific resources. Stores web content, such as HTML, CSS, images, Hosts repositories for services like Git.

5/// . temporary directory is typically named **`/tmp`**, which is part of the **Filesystem Hierarchy Standard (FHS)**. Files in `/tmp` are typically **deleted at system reboot** to free up space and prevent clutter(desordre).

6/// . In summary, **`/var/log`** is a directory dedicated to storing logs for system and application activity, helping administrators monitor and troubleshoot their Linux systems effectively. Proper management of `/var/log` ensures system stability and security. 

The /home directory in Unix-like operating systems (including Linux) is a crucial directory that contains user-specific data and settings.

:::: Personal Files/Default Permissions/Configuration Files.

7/// The mount point for the /home partition is simply "/home" in Linux/Unix systems. This is where user home directories are stored by default. Each user typically gets their own subdirectory within /home, like /home/username.

### **Purpose of `/var/log`**

1. **Centralized Logging**: Acts as a centralized location for storing logs from the kernel, applications, and various services.
2. **System Monitoring**: Helps system administrators track and analyze system activity.
3. **Troubleshooting**: Useful for diagnosing issues by examining error messages or unusual events.
4. **Audit Trail**: Logs can serve as an audit trail to track security incidents or user actions.

# set up process :

enter to root and install the sudo (#superuser do ) that gives some privilege  as the root have i did install sudo using (#apt install sudo ) to remove it (#apt remove sudo) to check for any program if it is installed (#sudo - -version)

first you have to go to root and add the user to the group sudo using (usermod -aG sudo ameskine) and after i check it if successfully was added with ** getent group sudo .

to add a user to a sudo group (#usermod -aG sudo ameskine)

to remove a user from a sudo group (#sudo deluser username sudo)

to check is the user is added successfully to the sudo group tow ways :

#cat  /etc/group  &&  #grep sudo /etc/group

and we can also use :::::::::: grep username /etc/passwd

Change the username (`-l` or `--login`):

#sudo usermod -l newname oldname

now i m going to go forward the ssh :

first to check about any service : in my example i ll do it for ssh :
# sudo systemctl status ssh

after it you need to modify from the file /etc/ssh/sshd_config to give access to the port 4242 and to not give the permission to the root ;

but lets install it : syu
the ssh get installed this way : # sudo apt install ssh

after i check it up with : sudo systemctl status ssh

### **`enabled`**

- **Meaning**:
    
    The service is set to start automatically during the system boot process.
    

### **2. `disabled`**

- **Meaning**:
    
    The service will not start automatically during system boot, he service will not start unless manually activated.
    

### **1. `active`**

- **Meaning**:The service is currently running and operationa

### **2.`inactive` (or "deactivated")**

- **Meaning**:The service is not running. It is either stopped manually or has not been started yet.

when using useradd : without password .

using adduser : with a password .

for now i m gonna add the FIREWALL:

WHAT IS THE FIREWALL :::

A firewall is software that controls incoming and outgoing network traffic based on predetermined security rules. It essentially acts as a barrier between a trusted network .

Here are the key things firewalls do:

Traffic filtering / Access control / Logging and monitoring

so first i install the firewall (apt install firewall ) and then i check if the ufw (uncomplicated firewall) is active or inactive by ## : ufw status or much better command : sudo service ufw status ;

if you get inactive which is what i get i should 

activate it with :: ##sudo ufw enable then i check it with # sudo ufw status 

!!!! ONE IMPORTANT THING TO ACTIVATE AND CHANGE THE PORT :: 4242 BY THIS PATH : sudo nano /etc/ssh/sshd_config

TO ADD NEW UFW to a specific port  ::::

sudo ufw allow 4242/tcp (This allows incoming TCP connections on port 4242.)

to remove a port :: sudo ufw delete allow 8080;

ip hostname : hostname -I (it gives you the ip address of your machine);

to modify hostname you have to do two things :::: 

#sudo hostnamectl set-hostname <new_hostname> and go to the file :: vi /etc/hosts .

TCP :: protocol that provides reliable, ordered, and error-checked delivery of data between applications running on computers connected via an IP network.
When you send data, TCP breaks it into smaller pieces called "segments”. 

Each segment gets a sequence number so they can be put back together in the right order.

The TCP segments are then packaged into IP packets, These packets may take different routes through the network to reach the destination to be faster .

If any segment is missing, TCP requests a retransmission.

- **IPv4 (Internet Protocol version 4)**:
    - Format: `xxx.xxx.xxx.xxx` (e.g., `192.168.1.1`)
    - Uses 32-bit addresses, allowing approximately 4.3 billion unique addresses.
    - Commonly used, but its address space is almost exhausted.
- **IPv6 (Internet Protocol version 6)**:
    - Format: `xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx` (e.g., `2001:0db8:85a3:0000:0000:8a2e:0370:7334`)
    - Uses 128-bit addresses, allowing a vast number of unique addresses.
    - Developed to address IPv4 exhaustion and offers enhanced features like better routing and built-in security

for the password policy i work on these :
firstly i use the following path to modify it nano /etc/login.defs

Your password has to expire every 30 days. MAXDAYS 30.
• The minimum number of days allowed before the modification of a password will be set to 2. MINDAYS 2.
• The user has to receive a warning message 7 days before their password expires PASS_WARN_AGE 7.

** Password Expiration Policies
After configuring the system-wide password policies, I applied them individually to the root user and the regular user using the chage command:

chage -l root
chage -l ameskine

# Apply password policies
sudo chage -M 30 -m 2 -W 7 root
sudo chage -M 30 -m 2 -W 7 ameskine
-M 30: Set maximum password age to 30 days.

-m 2: Set minimum password age to 2 days.

-W 7: Warn the user 7 days before password expiration.

** Password Quality Enforcement
I installed the password quality checking library to enforce strong password rules:

sudo apt -y install libpam-pwquality
The -y flag automatically answers "yes" to all prompts.

This library integrates with PAM (Pluggable Authentication Modules) to validate passwords based on defined quality rules.

Configuration file:

vi /etc/security/pwquality.conf
Here, I modified rules like minlen, dcredit, ucredit, etc., to enforce strong passwords.

** Sudoers Configuration
The sudoers file defines permissions and behaviors for the sudo command. I edited it safely using:

visudo
I added the following options to enhance security and auditing:

Defaults        requiretty
Defaults        passwd_tries=3
Defaults        badpass_message="Wrong password. Please try again."
Defaults        logfile="/var/log/sudo/sudo.log"
Defaults        log_input, log_output

requiretty: Requires users to run sudo from a terminal.

passwd_tries=3: Limits password entry attempts.

logfile: Specifies where to store sudo logs.

log_input, log_output: Captures all user inputs and outputs during sudo sessions.

Important: Ensure the logging path exists:

sudo mkdir -p /var/log/sudo
sudo touch /var/log/sudo/sudo.log
** Cron Job Setup
Cron is a time-based job scheduler used to automate repetitive tasks.

I created a cron job that launches a monitoring script every 10 minutes after each system reboot:

sudo crontab -e
Inside the crontab file, I added:

@reboot while true; do sleep 600 && /home/ameskine/monitoring.sh; done
This ensures the script is executed every 10 minutes continuously after each reboot.
