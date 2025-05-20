# bOrn_TobeRooT
# basic

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

![Screenshot from 2024-12-22 18-45-21.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/86fd731c-6f91-46ba-94e4-8608b03510b4/bd9ea913-5b7f-4ac0-865b-ec6f16aa6218/Screenshot_from_2024-12-22_18-45-21.png)

 

![Screenshot from 2024-12-22 18-53-52.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/86fd731c-6f91-46ba-94e4-8608b03510b4/609bb851-b59e-4ea4-a7e5-1bef18f961c6/Screenshot_from_2024-12-22_18-53-52.png)

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

![Screenshot from 2024-12-25 12-18-33.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/86fd731c-6f91-46ba-94e4-8608b03510b4/1dfa3c16-94b4-400f-81e4-234138f98e29/Screenshot_from_2024-12-25_12-18-33.png)

**Type 2 Hypervisor: Advantages and Disadvantages :**

Type-2 hypervisor runs on top of supported operating systems and uses the OS’s drivers to communicate with the hardware. Oracle Virtual Box, QEMU and VMware Workstation are examples of Type-2 hypervisors. Actually, the hypervisor of Type-2 runs inside OS as other applications and shares resources with them.

### Advantages:

- **Hardware-agnostic**, modern Type-2 hypervisors can run on any hardware, which is supported by the host OS.
- E**asy to install and manage**. It is installed as a normal application.

### Disadvantages:

- Lower performance than with Type-1, because of resource sharing with other applications and using hardware resources via the host OS.
- **Less secure and stable**. Crash of any other application may crash host OS.

![Screenshot from 2024-12-26 09-36-24.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/86fd731c-6f91-46ba-94e4-8608b03510b4/bcb0e826-a935-489a-ab45-d8376829188b/Screenshot_from_2024-12-26_09-36-24.png)

**BARE-METAL HYPERVISOR :**

bare-metal (Type 1) hypervisor runs directly on the hardware and acts as a lightweight operating system (how : Directly controlling hardware resources (CPU, memory, I/O) / Scheduling and allocating these resources to guest operating systems ). allows multiple guest operating systems to run independently on the same physical machine.

**kernel : is a computer program (**set of instructions written by assembly and c language for computer to execute**) at the core of a the computer’s operating system has control over everything in the system (software and hardware).**

![Screenshot from 2024-12-23 10-42-05.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/86fd731c-6f91-46ba-94e4-8608b03510b4/2051db82-2538-4143-8f44-fda92f8d873d/Screenshot_from_2024-12-23_10-42-05.png)

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

![Screenshot from 2024-12-25 15-47-52.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/86fd731c-6f91-46ba-94e4-8608b03510b4/e01cdc55-d972-4610-bd40-ef50897321bd/Screenshot_from_2024-12-25_15-47-52.png)

![Screenshot from 2024-12-25 15-44-55.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/86fd731c-6f91-46ba-94e4-8608b03510b4/eb599de3-bb59-4f5b-a715-5575225afc60/Screenshot_from_2024-12-25_15-44-55.png)

---

[added infos about LVM:](https://www.notion.so/added-infos-about-LVM-16733f09557980b4bb59c39de86c3072?pvs=21)

[catch up infos:](https://www.notion.so/catch-up-infos-16833f095579808c9515e24fec726735?pvs=21)

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

[**Linux Boot Process:**](https://www.notion.so/Linux-Boot-Process-16a33f095579803e8b5ceb48b57b5e7a?pvs=21)

[root / user / sudo:](https://www.notion.so/root-user-sudo-16a33f095579804b8403f14ec576f63a?pvs=21)
