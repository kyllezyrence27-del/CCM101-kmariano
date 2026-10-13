# Linux Host Baseline Assessment

**Student:** Kylle Mariano  
**Course:** CCM101 – Cloud Computing  
**Laboratory:** 07 – Cloud Operations Engineer

## 1. Assessment Overview

Before deploying the Nginx web server, the Linux host must be inspected to understand its available computing resources. This assessment will record the operating system, kernel, processor configuration, memory, and disk capacity.

## 2. Inspection Commands

| Command | Information Provided |
|---|---|
| `cat /etc/os-release` | Linux distribution and version |
| `uname -r` | Current kernel release |
| `lscpu` | CPU architecture and configuration |
| `free -h` | Memory and swap information |
| `df -h /` | Root filesystem usage and free space |

## 3. Host Measurements

The results below will be filled in after the commands have been run.

| Item | Recorded Result |
|---|---|
| Operating system | Pending inspection |
| Kernel release | Pending inspection |
| CPU details | Pending inspection |
| RAM and swap | Pending inspection |
| Root filesystem storage | Pending inspection |

## 4. Resource Evaluation

The baseline measurements help establish what resources the environment provides before container deployment. Available memory and disk space are particularly useful when assessing whether the host can accommodate the web server and its related files.

The measurements will also serve as a reference when reviewing resource consumption during the later Docker monitoring checkpoint.

## 5. Summary

Inspecting the host before deployment helps establish a clearer understanding of the environment. Actual command outputs and screenshots will be included after the system checks are completed.
