# Laboratory Activity 08: The Cloud Security Engineer

**Student:** Kylle Zyrence F. Mariano  
**Course:** CCM101 – Cloud Computing  
**Laboratory Environment:** KillerCoda Ubuntu Linux  
**Tools Used:** Docker, Nginx, UFW, cURL, and GitHub

## Mission Overview

This laboratory activity explores the importance of securing cloud infrastructure through firewall configuration and controlled network access. It provides hands-on experience in deploying a web application, implementing security policies, and verifying that essential services remain operational.

As part of the Cloud Security Engineer mission, the activity demonstrates how Ubuntu firewall rules can be used to restrict incoming connections while permitting authorized network services.

## Learning Objectives

- Explain essential principles of cloud security.
- Understand the Principle of Least Privilege and attack surface reduction.
- Implement a Default Deny firewall policy.
- Deploy an Nginx web application using Docker.
- Configure firewall rules for SSH and application traffic.
- Verify firewall settings and application connectivity.
- Document security testing results and observations.

## Checkpoint 1: Cloud Security Research

The first part of the laboratory focused on understanding three fundamental cybersecurity concepts.

**Principle of Least Privilege (PoLP):** Provides users and services with only the access permissions required for their responsibilities.

**Attack Surface:** Includes the different points through which a system may be accessed or potentially attacked.

**Default Deny Policy:** Rejects incoming connections unless they are explicitly permitted by security rules.

These principles help establish a foundation for protecting cloud resources.

**Documentation:** [Security Audit Report](security-audit-report.md)

## Checkpoint 2: Deploying the Nginx Application

The Docker environment was checked before deploying the application.

```bash
docker --version
```

**Observed Docker Version:** 29.1.3

The Nginx container was deployed using:

```bash
docker run -d --name secure-web-app -p 8080:80 nginx
```

The application was then tested through port 8080.

```bash
curl -I http://localhost:8080
```

**Actual Response:**

```text
HTTP/1.1 200 OK
Server: nginx/1.31.6
```

The successful response confirmed that the web server was running and responding to local HTTP requests.

### Screenshot 1 – Nginx Application Running

![Nginx Application Running](screenshots/vulnerable-app-running.png)

## Checkpoint 3: Configuring the Ubuntu Firewall

The initial UFW status was checked.

```bash
ufw status verbose
```

**Initial Result:** Status: inactive

The following commands were executed to establish the firewall rules:

```bash
ufw allow 22/tcp
ufw default deny incoming
ufw default allow outgoing
ufw allow 8080/tcp
ufw show added
ufw enable
```

These commands established the default firewall policies, permitted SSH and application traffic, and activated UFW.

### Verified Firewall Settings

| Security Setting | Actual Result |
|---|---|
| UFW Status | Active |
| Logging | On (low) |
| Default Incoming | Deny |
| Default Outgoing | Allow |
| Default Routed | Deny |
| SSH Port 22/TCP | ALLOW IN |
| Application Port 8080/TCP | ALLOW IN |
| IPv6 Rules | Enabled for ports 22 and 8080 |

### Screenshot 2 – Firewall Activated

![UFW Firewall Configuration](screenshots/firewall-activated.png)

**Documentation:** [Firewall Configuration Report](firewall-configuration.md)

## Checkpoint 4: Application Connectivity Verification

After enabling the firewall, the Nginx web application was tested again.

```bash
curl -I http://localhost:8080
```

**Actual Response:**

```text
HTTP/1.1 200 OK
Server: nginx/1.31.6
```

This result demonstrated that the application remained accessible locally after UFW activation.

**Security Consideration:** Docker-published ports can bypass certain UFW rules. Therefore, the successful local HTTP response does not independently confirm that external connections are being filtered as intended.

### Screenshot 3 – Application Connectivity

![Application Connectivity Test](screenshots/firewall-allowed.png)

## Laboratory Documentation

| File | Description |
|---|---|
| `README.md` | Main laboratory documentation |
| `security-audit-report.md` | Research on cloud security principles |
| `firewall-configuration.md` | Firewall setup and actual testing results |
| `reflection.md` | Personal reflection and lessons learned |
| `screenshots/` | Screenshots of practical laboratory activities |

## Personal Reflection

This laboratory provided practical experience in managing security settings within an Ubuntu environment. It highlighted the importance of applying restrictive firewall policies, allowing only necessary connections, and verifying application functionality after implementing security changes.

The activity also demonstrated that effective cloud security involves understanding the interaction between different technologies, including Docker networking and Linux firewall rules.

**Full Reflection:** [Laboratory Reflection](reflection.md)

## Conclusion

Laboratory Activity 08 strengthened my understanding of basic cloud security procedures through hands-on application deployment and firewall configuration.

The activity successfully demonstrated the activation of UFW, the implementation of a Default Deny incoming policy, and the continued local accessibility of an Nginx application.

The knowledge gained from this laboratory provides a useful foundation for further learning about cloud infrastructure protection, network access management, and secure system administration.
