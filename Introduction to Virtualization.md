---
date created: Monday, March 27th 2023, 2:34:08 pm
date modified: Monday, March 27th 2023, 2:54:44 pm
---

# Introduction to Virtualization

## What is Virtualization ?

Virtualization is the process of creating a virtual representation of something through abstractions, such as virtual computer hardware platforms, storage devices, or computer network resources.

## Types of Virtualization

- Common (none-exhaustive) types of virtualization:
	- Platform (hardware) virtualization
	- Operating system (OS) virtualization
	- Storage virtualization
	- Network virtualization
	- Language-based virtualization

## Platform (hardware) Virtualization

This type involves running multiple virtual machines with different operating systems on a single physical host. The hypervisor creates a virtual hardware environment for each VM, allowing them to run independently.
It allows different users to access a computer as if they had each total control of the physical hardware.
A virtualization layer created, for each OS running on top of it, all the facilities of the underlying hardware in virtual form.

## What is a Virtual Machine ?

An efficient, isolated duplicate of a real computer machine.
A Virtual Machine (VM) is a software-based representation of a physical computer that runs on a host system. It emulates the hardware resources of a physical machine, such as the CPU, memory, storage, and network devices, enabling you to install and run an operating system and applications on the virtual machine as if it were a separate, independent computer.

A virtual machine consists of two main components:

1. **Virtual hardware**
2. **Guest operating system**

## Storage Virtualization

Storage virtualization abstracts storage-management software from underlying hardware infrastructure.
Storage virtualization involves abstracting and pooling physical storage resources, such as hard disks or storage area networks (SANs), into a single logical storage unit. This allows for simplified management and improved utilization of storage resources.

### Benefits

- flexibility
- scalability

### Examples

- LVM (Logical Volume Manager)
- BTRFS filesystem
- Hardware RAID (Redundant Array of Independent Disks)
- Software RAID (mdraid in Linux and dmraid over LVM)
- Hardware SAN (Storage Area Network)

## Network Virtualization

This type of virtualization abstracts the physical network infrastructure, allowing for the creation of multiple virtual networks that can run concurrently on the same physical network. It abstracts the networking resources into a logical model so that the same set of physical resources can be shared by multiple tenants in a secure and isolated manner. 

### Examples

- software-defined network (SDN)

## Language-based Virtualization

Language-based virtualization refers to the process of creating isolated execution environments for programs or applications written in a specific programming language. This type of virtualization is typically achieved through the use of language runtime environments, interpreters, or virtual machines designed for a particular programming language.

### Benefit

- architecture independence which provides application (binary) portability between platforms

### Examples

- JVM
- Dalvik
- Python VM
- V8 js VM
- .NET CLR

## System Simulation

System simulation involves using software to emulate hardware components of a target machine, where an interpreter executes each instruction and updates the software representation of the hardware state; this approach is highly accurate but slow and is often utilized for developing software for specific embedded hardware types.

### Examples

- Logisim
- Wind River Simics
- Ngspice

## System Emulation

System emulation focuses on emulating a sufficient amount of system hardware components to provide an accurate user experience, usually including the CPU and memory subsystems, while omitting buses. This approach takes numerous shortcuts to improve performance at the expense of overall system accuracy. As a result, code intended to run correctly on real hardware performs reasonably well, while code not designed for real hardware may exhibit significantly different behavior.

### Examples

- QEMU
- Bochs
- DOSBox
- MAME (Arcade)
- PCSX2 (PS2)
- UAE (Amiga)
- ZSNes (Super Nintendo)
- DGen (Sega Genesis)
- Vice (C64)

## Application Emulation

This type of virtualization involves running an application in an isolated environment, separate from the underlying operating system. This can be achieved by encapsulating the application and its dependencies into a virtualized package, which can then be executed on any compatible system without the need for installation.

### Difference between application and system emulation

Application emulation only emulates the programming interfaces used by an application compiled for a given OS, so it can run on another OS with different programming interfaces

System emulation emulates the whole system, including hardware

### Examples

- Wine (https://www.winehq.org/)
	- compatibility layer capable of running Windows applications on several POSIX-compliant OSes (Linux, OSX, etc.)
	- translates Windows API calls into POSIX calls on-the-fly
- WSL1 (Windows Subsystem for Linux, version 1)
	- translates Linux system calls to Windows kernel compatible calls/behavior

## Operating system (OS) virtualization

Also known as conteneurisation, this type of virtualization allows multiple isolated user-space instances, called conteneurs, to run on the same operating system kernel. Containers share the host OS kernel but have their own file systems, libraries, and application environments.

## Virtualization Vs Emulation Vs Simulation

### Virtual Machine

- Model a machine exactly and efficiently
- Minimal slowdown
- Must run on the physical machine it virtualizes (more or less)

### System Emulator

- Provides a behavioral model of hardware (and possibly software)
- Not fully accurate
- Reasonably fast

### System Simulator

- Provides a functionally accurate software model of a machine
- May run on any hardware
- Typically slow

## Why virtualize ?

### Coupling

Unfortunate coupling between hardware resources and the OS: 
- Hard to run multiple OSes on the same machine
- Difficult to transfer software setups to another machine, unless identical or nearly identical hardware
- Messy to adjust hardware resources to system needs → requires sticking your hands in the box
- Requires static, up-front provisioning of machine resources

### Isolation

Lack of true isolation between multiple applications: 
- Operating systems “leak” information between processes through file system and other channels
- Multiple applications may require specific and conflicting software packages to run
- Certain applications may have very specific OS configuration and tuning requirements
- Software vendors may not provide support if their application runs alongside anything else

## Benefits of virtualization

- Security: bugs and faults isolation
- Availability & reliability
	- OS + apps decoupled from physical hardware → live migration of VMs from one physical machine to another 
	- increase services availability, greater reliability
- Consolidation: ability to run multiple VMs on a single platform → decrease cost, improve manageability
- Functionality: ability to run a native app for a different OS
- Flexibility: 
	- can easily replicate an entire machine image in order to duplicate it or move it
	- software packaging and distribution
- Development: kernel, debugging, systems research, new architectures
- Support: legacy operating systems & applications

# References
