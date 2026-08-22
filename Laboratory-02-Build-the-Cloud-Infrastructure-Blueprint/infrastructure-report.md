# Infrastructure Report

## Cloud Server Assessment

This report presents the results of the investigation conducted on the Linux server provided through the KillerCoda Playground. The purpose of the investigation is to identify the available operating system, computing resources, memory, storage, network information, and mounted file systems.

## Operating System

The cloud server is running **Ubuntu 24.04.4 LTS (Noble Numbat)**. Ubuntu is a Linux-based operating system commonly used for servers and cloud computing environments.

## Kernel Version

- **Kernel Version:** 6.8.0-138-generic

The Linux kernel serves as the core component of the operating system and manages hardware resources and system operations.

## CPU and Compute Resources

- **CPU Model:** Intel Xeon E312xx (Sandy Bridge, IBRS update)
- **Number of CPU Cores:** 1
- **Architecture:** x86_64
- **Hypervisor:** KVM

The server is running as a virtual machine using KVM virtualization.

## Memory

- **Total RAM:** 1.9 GiB
- **Used RAM:** 425 MiB
- **Available RAM:** 1.4 GiB
- **Swap:** 1.0 GiB

The available memory allows the virtual server to run its operating system and applications.

## Storage Capacity

The main storage device is `/dev/vda1`, which has a total capacity of **19G**.

| Filesystem | Size | Used | Available | Mounted On |
|---|---:|---:|---:|---|
| /dev/vda1 | 19G | 5.4G | 13G | / |
| /dev/vda16 | 881M | 117M | 703M | /boot |
| /dev/vda15 | 105M | 6.2M | 99M | /boot/efi |
| tmpfs | 191M | 1000K | 190M | /run |
| tmpfs | 952M | 84K | 952M | /dev/shm |
| tmpfs | 5.0M | 0 | 5.0M | /run/lock |

## Mounted File Systems

The Linux server contains several mounted file systems. The main root file system is mounted at `/`, while additional file systems are mounted at `/boot` and `/boot/efi`. Temporary file systems are also mounted for system processes and shared memory.

## Hostname

- **Hostname:** ubuntu

The hostname identifies the Linux server within its environment.

## IP Address

The server reports the following IP addresses:

- **172.30.1.2**
- **172.17.0.1**

These addresses represent network interfaces available within the virtualized environment.

## Commands Used

The following Linux commands were used during the investigation:

```bash
cat /etc/os-release
uname -r
lscpu
free -h
df -h
hostname
hostname -I
