# Laboratory Activity 08 – Personal Reflection

**Student:** Kylle Zyrence F. Mariano  
**Course:** CCM101 – Cloud Computing  
**Laboratory:** The Cloud Security Engineer

## Reflection

Through this laboratory activity, I gained a better understanding of how security measures are implemented in a cloud computing environment. Before performing the activity, I mainly focused on making applications work properly. However, this exercise helped me recognize that managing a server also involves protecting its services and controlling which network connections are permitted.

One important part of the activity was configuring the Uncomplicated Firewall (UFW) in Ubuntu. I started by checking its initial status and discovered that it was inactive. I then applied a Default Deny policy for incoming connections while allowing outgoing traffic and the necessary ports for SSH and the Nginx web application. This process helped me understand how firewall rules can be used to establish basic network access restrictions.

Another valuable experience was deploying the Nginx web server using Docker and testing its availability through the terminal. After enabling UFW, I used the curl command to check whether the application was still responding. Receiving an HTTP 200 OK response showed that the application remained accessible locally. I also learned that Docker networking may require additional security checks because published container ports do not always follow UFW filtering rules as expected.

The activity also strengthened my awareness of the Principle of Least Privilege and the importance of reducing a system's attack surface. I realized that effective cloud security requires careful planning, proper configuration, and verification rather than simply enabling security tools.

Overall, this laboratory helped me develop practical knowledge of Linux firewall administration and container-based application testing. The experience will be useful as I continue studying cloud computing and preparing for future responsibilities in the information technology field.

## Lessons Learned

1. Firewall policies help control network access to server resources.
2. Essential ports should be identified before activating security restrictions.
3. A Default Deny policy provides a more restrictive starting point for incoming connections.
4. Testing applications after configuration changes helps identify possible connectivity issues.
5. Docker networking introduces additional considerations when implementing firewall security.

## Conclusion

Laboratory Activity 08 allowed me to practice basic cloud security procedures using Ubuntu, Docker, and UFW. It improved my understanding of how network access policies and application testing contribute to maintaining a secure and functional cloud environment.
