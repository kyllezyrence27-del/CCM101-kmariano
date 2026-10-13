# Reflection: Cloud Operations and Observability

**Student:** Kylle Mariano  
**Course:** CCM101 – Cloud Computing

## 1. Why is it important to check the host server's resources even if your containers are running perfectly?

A container may appear healthy while the host is already running low on resources. If memory is nearly exhausted or disk space is insufficient, the application could slow down or fail when the workload increases. Checking the host helps me understand the environment's limitations before they become serious problems.

## 2. If a user complains that they cannot log into a web application, how would the Docker logs command help you solve the problem?

I would inspect the container output with `docker logs client-website` and look for messages related to the user's request. If the application records authentication errors, failed requests, or other relevant events, these may help identify the problem. I would then check the relevant application settings and services rather than relying on the logs alone.

## 3. What is the difference between monitoring logs (Checkpoint 4) and monitoring metrics (Checkpoint 5)?

Logs record events and provide details about application activity, including requests and errors. Metrics summarize system performance using values such as CPU percentage, memory usage, and network traffic. Logs help me investigate specific events, whereas metrics help me recognize performance changes and resource trends.

## 4. How do you think large enterprise companies monitor thousands of containers at the same time?

Managing thousands of containers manually would be difficult, so enterprises can use centralized monitoring systems. Prometheus can collect metrics from containerized services, and Grafana can present those measurements in dashboards. Alerts can also notify engineers when resource usage or other monitored values exceed configured limits.

## 5. How has your ability to troubleshoot Linux environments improved?

I have learned to approach troubleshooting more systematically by checking system information and examining application evidence. Commands such as `free -h`, `df -h /`, and Docker's logging and monitoring tools provide different details that can help narrow down a problem. This approach makes it easier to investigate issues and decide what to check next.

## Conclusion

The activity shows that effective cloud operations require both application-level investigation and system-level monitoring. Understanding logs, resource measurements, and monitoring tools can help engineers maintain services and respond to problems more effectively.
