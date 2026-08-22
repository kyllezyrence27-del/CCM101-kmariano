# Cloud Infrastructure Components

## Overview

A cloud environment depends on several infrastructure components that work together to provide computing services. Based on the investigation of the KillerCoda Linux server, the main components identified are compute, storage, networking, and the operating system.

## 1. Compute Resources

### Purpose

Compute resources provide the processing capability required to execute programs, applications, and system processes.

### Importance in Cloud Computing

Computing power is necessary for running workloads and applications in the cloud. Cloud platforms make it possible to provide virtual computing resources according to the needs of an organization.

### KillerCoda Environment

The investigated server uses an **Intel Xeon E312xx (Sandy Bridge, IBRS update)** processor with **1 CPU core**. The environment is virtualized using **KVM**, which provides the virtual machine with its allocated computing resources.

## 2. Storage Resources

### Purpose

Storage resources provide space for the operating system, applications, system files, and user data.

### Importance in Cloud Computing

Cloud storage allows data to be stored and accessed when needed. It is important because applications and services require reliable storage for their files and information.

### KillerCoda Environment

The main filesystem, `/dev/vda1`, has a capacity of **19G**, with approximately **13G available**. The server also has mounted filesystems for `/boot` and `/boot/efi`.

## 3. Networking Resources

### Purpose

Networking resources provide communication between computers, applications, servers, and users.

### Importance in Cloud Computing

Networking makes it possible for cloud resources to communicate and for users to access cloud-based applications and services. A properly configured network is therefore an important part of cloud infrastructure.

### KillerCoda Environment

The Linux server has the IP addresses **172.30.1.2** and **172.17.0.1**. These addresses indicate the network interfaces available in the virtualized environment.

## 4. Operating System

### Purpose

The operating system manages hardware resources and provides a platform where applications and services can operate.

### Importance in Cloud Computing

An operating system is needed to manage resources such as CPU, memory, storage, and networking. It also provides the environment required for applications and cloud workloads to run.

### KillerCoda Environment

The server uses **Ubuntu 24.04.4 LTS (Noble Numbat)** with the **6.8.0-138-generic** Linux kernel. It manages the virtual hardware and system resources assigned to the KillerCoda server.

## Conclusion

The investigation shows that cloud infrastructure is composed of several interconnected resources. The KillerCoda environment provides a practical example of how compute, storage, networking, and an operating system work together to support a virtual cloud server. Understanding these components is important when planning and managing cloud-based systems.
