
# MinIO Object Storage Deployment

**Name:** Kylle Zyrence F. Mariano  
**Laboratory:** 05 – The Cloud Data Engineer

## 1. Deployment Overview

For this laboratory activity, I deployed MinIO, an S3-compatible object storage server, using Docker in the KillerCoda Ubuntu environment.

The purpose of the deployment was to create an object storage service, access its web console, create a storage bucket, and upload a sample image.

## 2. Tools and Technologies

- Ubuntu 24.04
- Docker
- MinIO
- KillerCoda Ubuntu Playground
- Web Browser

## 3. Docker Image

The initial Docker image command provided in the instructions was not accessible. I used the MinIO image from Quay.io instead.

Command used:

```bash
docker pull quay.io/minio/minio
```

The image was downloaded successfully.

## 4. Deploying the MinIO Container

The following command was used to create and start the MinIO container:

```bash
docker run -d \
  --name minio-server \
  -p 9000:9000 \
  -p 9001:9001 \
  -e "MINIO_ROOT_USER=admin" \
  -e "MINIO_ROOT_PASSWORD=MinioAdmin123!" \
  quay.io/minio/minio server /data --console-address ":9001"
```

### Explanation of the Docker Command

| Option | Description |
|---|---|
| `-d` | Runs the container in detached mode. |
| `--name minio-server` | Assigns a name to the container. |
| `-p 9000:9000` | Maps port 9000 for the MinIO API. |
| `-p 9001:9001` | Maps port 9001 for the MinIO Web Console. |
| `MINIO_ROOT_USER` | Sets the MinIO administrator username. |
| `MINIO_ROOT_PASSWORD` | Sets the administrator password. |
| `server /data` | Starts the MinIO server and specifies its data directory. |
| `--console-address ":9001"` | Sets the web console to port 9001. |

## 5. Verifying the Container

I used the following command to check whether the container was running:

```bash
docker ps
```

The output showed the container named `minio-server` with an Up status and ports 9000 and 9001 mapped.

This confirmed that the MinIO container was running in the KillerCoda environment.

## 6. Accessing the MinIO Web Console

I accessed the MinIO Web Console through the KillerCoda port forwarding feature using port 9001.

I logged in using the administrator credentials configured in the Docker command.

The web console allowed me to manage buckets and upload objects through the browser.

## 7. Creating a Bucket and Uploading an Object

I created a bucket named:

`client-photos`

After creating the bucket, I uploaded a sample image through the MinIO Web Console.

The uploaded image appeared inside the bucket, confirming that the object storage operation was successful.

## 8. Screenshots and Evidence

The following screenshots provide evidence of the deployment:

| Screenshot | Description |
|---|---|
| `screenshots/minio-deployed.png` | Shows the running MinIO container and port mappings. |
| `screenshots/minio-bucket-upload.png` | Shows the created bucket and uploaded sample file. |

## 9. Conclusion

This deployment helped me understand how Docker can be used to run an object storage server. I also learned how to configure container ports, access a web-based cloud storage console, create buckets, and upload objects.

MinIO provided a practical environment for learning the basic operations of S3-compatible object storage.
