# Reflection: Cloud Operations and Observability

**Student:** Kylle Mariano  
**Course:** CCM101 – Cloud Computing

## 1. Why is it important to check the host server's resources even if your containers are running perfectly?

Checking the host server is important because containers depend on the resources available on the machine where they run. Even if a container works properly, low memory, high CPU usage, or limited disk space can affect its performance. Monitoring these resources helps identify possible problems before they affect the application, especially when website traffic increases.

## 2. If a user complains that they cannot log into a web application, how would the Docker logs command help you solve the problem?

I would use `docker logs client-website` to inspect messages produced by the container. These messages may reveal failed requests, application errors, or other clues about the problem. I would check the timestamps and response codes, then investigate further based on the evidence. Logs can help narrow down the cause, although authentication problems may also require checking application settings and other services.

## 3. What is the difference between monitoring logs (Checkpoint 4) and monitoring metrics (Checkpoint 5)?

Logs record individual events, such as HTTP requests and application errors. Metrics provide numerical measurements, including CPU usage, memory consumption, and network traffic. Logs help me understand what happened during a particular event, while metrics help me evaluate performance and recognize changes in resource usage. Using both provides a clearer picture of the application's condition.

## 4. How do you think large enterprise companies monitor thousands of containers at the same time?

Large enterprises can use centralized monitoring tools such as Prometheus and Grafana. Prometheus collects metrics from monitored systems, while Grafana presents the information through dashboards and graphs. Alerts can notify engineers when resource usage or other measurements exceed configured limits. These tools make it easier to monitor many services and investigate possible problems efficiently.

## 5. How has your ability to troubleshoot Linux environments improved?

This activity helped me understand the importance of checking evidence instead of guessing the cause of a problem. Commands such as `free -h` and `df -h /` help inspect host resources, while `docker logs` and `docker stats` provide information about container behavior and performance. Testing successful requests and a missing webpage also helped me understand HTTP response codes. I can now approach troubleshooting in a more organized way.

## Conclusion

This laboratory demonstrated how host monitoring, application logs, and container metrics support reliable cloud operations. These skills can help me identify errors, investigate resource problems, and understand the performance of containerized applications.
