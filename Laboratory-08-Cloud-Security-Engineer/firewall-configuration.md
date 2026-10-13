# Laboratory 08 – Firewall Configuration and Security Testing

**Student:** Kylle Zyrence F. Mariano  
**Course:** CCM101 – Cloud Computing  
**Laboratory Role:** Cloud Security Engineer  
**Platform:** KillerCoda Ubuntu Linux  
**Tools:** Docker, Nginx, UFW, cURL

## 1. Introduction

This laboratory activity involved configuring network security controls in an Ubuntu cloud environment. The main objective was to understand how firewall policies can regulate incoming and outgoing connections while allowing necessary applications to remain operational.

The practical activity included deploying an Nginx web server through Docker, implementing UFW firewall rules, and testing the application after applying the security settings.

## 2. Checking the Docker Environment

Before deploying the application, the installed Docker version was verified.

**Command:**

```bash
docker --version
```

**Actual Output:**

```text
Docker version 29.1.3, build 29.1.3-0ubuntu3~24.04.2
```

This confirmed that Docker was available in the Ubuntu environment.

## 3. Deploying the Nginx Application

The following command was executed to create and start the Nginx container:

```bash
docker run -d --name secure-web-app -p 8080:80 nginx
```

Docker downloaded the Nginx image and successfully created the container.

**Container ID:**

```text
a53b6a9a2020b561395f1d9c027bad8b16e99e12a343fa25a1c436c5162218b5
```

The application was tested using:

```bash
curl -I http://localhost:8080
```

**Actual Response:**

```text
HTTP/1.1 200 OK
Server: nginx/1.31.6
```

This indicated that the Nginx server was responding successfully through localhost port 8080.

## 4. Inspecting the Initial Firewall Status

The firewall was examined before making configuration changes.

```bash
ufw status verbose
```

**Actual Output:**

```text
Status: inactive
```

The result indicated that UFW was initially disabled.

## 5. Establishing Firewall Rules

The following commands were used to establish the firewall configuration:

```bash
ufw allow 22/tcp
ufw default deny incoming
ufw default allow outgoing
ufw allow 8080/tcp
```

### Explanation of Each Rule

**Allow SSH (Port 22):** Permits incoming SSH connections for remote administration.

**Deny Incoming Traffic:** Establishes a restrictive default policy for incoming connections that do not match an allowed rule.

**Allow Outgoing Traffic:** Permits the server to initiate outbound connections.

**Allow Port 8080:** Adds a rule permitting incoming TCP connections to the application port.

## 6. Reviewing the Added Rules

Before activating the firewall, the following command was executed:

```bash
ufw show added
```

**Actual Output:**

```text
Added user rules (see 'ufw status' for running firewall):
ufw allow 22/tcp
ufw allow 8080/tcp
```

This verified that the SSH and application port rules had been added.

## 7. Activating UFW

The firewall was enabled using:

```bash
ufw enable
```

**Actual Output:**

```text
Firewall is active and enabled on system startup
```

This confirmed that UFW was successfully activated.

## 8. Verifying the Active Firewall

The final firewall configuration was inspected using:

```bash
ufw status verbose
```

**Actual Results:**

```text
Status: active
Logging: on (low)
Default: deny (incoming), allow (outgoing), deny (routed)

To                         Action      From
--                         ------      ----
22/tcp                     ALLOW IN    Anywhere
8080/tcp                   ALLOW IN    Anywhere
22/tcp (v6)                ALLOW IN    Anywhere (v6)
8080/tcp (v6)              ALLOW IN    Anywhere (v6)
```

The firewall was active with a default deny policy for incoming connections and explicit allow rules for ports 22 and 8080.

## 9. Testing Application Connectivity

After the firewall configuration was completed, the Nginx application was tested again.

```bash
curl -I http://localhost:8080
```

**Actual Output:**

```text
HTTP/1.1 200 OK
Server: nginx/1.31.6
```

The successful response showed that the application remained accessible locally after UFW activation.

However, Docker-published ports can bypass certain UFW rules. Additional testing from another host would be required to verify whether external traffic is filtered as intended.

## 10. Security Analysis

The activity demonstrated how firewall policies can be configured to control access to a Linux server.

The Default Deny policy provides a restrictive baseline, while explicit rules identify the network connections intended to remain available.

Allowing SSH before enabling UFW also demonstrated the importance of planning security changes to reduce the risk of losing remote administrative access.

## 11. Conclusion

The laboratory successfully demonstrated the configuration and verification of UFW in an Ubuntu environment.

The firewall was activated, the required rules were confirmed, and the Nginx application continued responding to local HTTP requests.

The activity provided practical experience in firewall administration, container deployment, and basic cloud security testing.

## 12. Screenshot Evidence

The following screenshots document the laboratory procedures:

- `screenshots/vulnerable-app-running.png`
- `screenshots/firewall-activated.png`
- `screenshots/firewall-allowed.png`
