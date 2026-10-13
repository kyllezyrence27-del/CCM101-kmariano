# Linux Host Baseline Assessment

**Student:** Kylle Zyrene Mariano  
**Course:** CCM101 – Cloud Computing  
**Laboratory:** 07 – Cloud Operations Engineer

## 1. Purpose

This report describes the initial system resources available in the KillerCoda Linux environment. The inspection establishes a baseline before deploying the Nginx web server and monitoring its performance.

## 2. Host Inspection Commands

The following commands were used to gather information about the Linux host.

| Command | Purpose |
|---|---|
| `cat /etc/os-release` | Checks the installed operating system |
| `uname -r` | Identifies the Linux kernel version |
| `lscpu` | Displays processor and architecture details |
| `free -h` | Displays RAM and swap usage |
| `df -h /` | Shows root filesystem capacity and available space |
| `top` | Displays running processes and CPU activity |

## 3. Baseline Results

The following values were observed in the shared KillerCoda environment.

| Resource | Actual Result |
|---|---|
| Operating system | Ubuntu 24.04.4 LTS |
| Kernel version | 6.8.0-136-generic |
| CPU configuration | Intel Xeon E312xx, x86_64 architecture, 1 CPU and 1 core |
| Total RAM | 1.9 GiB |
| Used RAM | 402 MiB |
| Free RAM | 1.2 GiB |
| Available RAM | 1.5 GiB |
| Total swap | 1.0 GiB |
| Root filesystem capacity | 19 GB |
| Used disk space | 5.5 GB |
| Available disk space | 13 GB |
| Disk usage | 30% |

## 4. Resource Analysis

The system inspection shows that the environment has 1.9 GiB of RAM and approximately 1.5 GiB available at the time of measurement. The root filesystem has a capacity of 19 GB, with 13 GB available.

Checking disk capacity before a traffic surge is important because the server needs enough space for container images, application logs, and other data. Running out of disk space may cause errors or prevent services from operating correctly.

The CPU and memory readings also provide a reference for evaluating resource consumption after the Nginx container is deployed.

## 5. Conclusion

The host inspection established the initial condition of the Linux environment before the container monitoring tasks. The collected information will help explain the resources available to the server and provide context for the observations in the succeeding checkpoints.

Screenshots of the memory and disk checks will serve as evidence of the inspection process.
