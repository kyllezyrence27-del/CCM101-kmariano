
# Research: Types of Cloud Storage

**Name:** Kylle Zyrence F. Mariano  
**Laboratory:** 05 – The Cloud Data Engineer

## Introduction

Cloud storage allows users and organizations to store, access, and manage digital information through cloud infrastructure. The three primary types of cloud storage are Block Storage, File Storage, and Object Storage. Each type has its own structure, advantages, and common applications.

## 1. Block Storage

### Description
Block Storage divides data into fixed-sized blocks and stores them separately. Each block has its own address, allowing applications and operating systems to access data efficiently.

### Primary Use Case
Block Storage is commonly used for virtual machine disks, operating system volumes, and databases that require fast and consistent read and write operations.

### Cloud Provider Examples
- Amazon Web Services (AWS): Amazon Elastic Block Store (EBS)
- Microsoft Azure: Azure Managed Disks
- Google Cloud: Persistent Disk

## 2. File Storage

### Description
File Storage organizes data into files and folders in a hierarchical directory structure. Users can access and share files through standard file protocols such as NFS and SMB.

### Primary Use Case
File Storage is useful for shared folders, team documents, content management systems, and applications that need a common file system.

### Cloud Provider Examples
- AWS: Amazon Elastic File System (EFS)
- Microsoft Azure: Azure Files
- Google Cloud: Google Cloud NetApp Volumes

## 3. Object Storage

### Description
Object Storage stores data as objects. Each object contains the actual data, metadata, and a unique identifier. Objects are stored in containers called buckets rather than traditional folders and disk blocks.

### Primary Use Case
Object Storage is suitable for photos, videos, backups, documents, and other unstructured data. It is designed to handle large amounts of data and allows applications to access objects through APIs.

### Cloud Provider Examples
- AWS: Amazon Simple Storage Service (S3)
- Microsoft Azure: Azure Blob Storage
- Google Cloud: Cloud Storage

## Why Object Storage Is Best for the Photo-Sharing Application

Object Storage is appropriate for the client's photo-sharing application because it can store large quantities of user-uploaded images as individual objects. Each image can have its own identifier and metadata, making it easier for the application to organize and retrieve files.

Unlike traditional block storage, object storage does not require the application to manage individual disk blocks. It also supports API-based access, which allows web applications to interact with stored images.

Using an S3-compatible service such as MinIO provides a practical way to test object storage operations, including creating buckets and uploading files. This makes Object Storage a suitable solution for the client's image storage requirements.

## Conclusion

Block Storage is commonly used for disks and databases, File Storage is useful for shared files and directories, and Object Storage is designed for large amounts of unstructured data. Understanding these differences helps cloud engineers select storage solutions based on application requirements.
