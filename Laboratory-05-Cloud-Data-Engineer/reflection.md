
# Mission Reflection: The Cloud Data Engineer

**Name:** Kylle Zyrence F. Mariano  
**Laboratory:** 05 – The Cloud Data Engineer

## Reflection

In this laboratory activity, I learned about the importance of Object Storage in cloud computing, especially for applications that need to store millions of photos. Object Storage is suitable for this kind of application because it stores data as individual objects with unique identifiers and metadata. Unlike traditional block storage, it makes managing large collections of images more convenient through buckets and APIs.

I also learned how Docker makes deploying a MinIO storage server easier. Instead of manually installing and configuring everything, I used a Docker image and a single command to run MinIO as a container. Although I encountered an error when downloading the original image, I was able to use an alternative image registry and continue the deployment. This experience helped me understand the importance of troubleshooting.

A bucket is a logical container in object storage where files or objects are stored and organized. In this activity, I created a bucket named `client-photos` and uploaded a sample image to verify that the storage service was working correctly.

For large enterprises, data protection is important because physical servers can experience failures. Companies can prevent data loss by using replication, redundant storage systems, regular backups, and copies of data in different locations. These methods help ensure that information can still be recovered when hardware problems occur.

Lastly, my confidence in using the Linux command line has improved. I practiced downloading Docker images, running containers, and checking their status using terminal commands. This activity helped me become more comfortable with Linux and gave me practical experience in deploying cloud services.

Overall, this laboratory strengthened my understanding of cloud storage, containerization, and the importance of protecting data in modern cloud environments.
