# Security Audit Report

**Student Name:** Kylle Zyrence F. Mariano  
**Course:** CCM101 – Cloud Computing  
**Laboratory:** 08 – Cloud Security Engineer

## 1. Principle of Least Privilege (PoLP)

The Principle of Least Privilege is a cybersecurity approach that restricts users and applications to the minimum level of access necessary to accomplish their responsibilities.

In a cloud environment, this principle helps prevent unauthorized activities by limiting access to important system resources. For instance, an employee assigned to monitor a server should not automatically have permission to modify its security settings.

Applying this principle reduces the potential damage caused by compromised accounts, human errors, and unnecessary administrative privileges.

## 2. Attack Surface

An attack surface includes the different points where a computer system, application, or network could potentially be accessed or attacked.

Examples include exposed network ports, outdated applications, unnecessary background services, and improperly configured user accounts.

In cloud computing, minimizing the attack surface is important because cloud services may be accessible through public networks.

Organizations can reduce security risks by disabling unused services, updating software regularly, restricting unnecessary ports, and reviewing access permissions.

## 3. Default Deny Policy

A Default Deny policy is a security configuration that rejects network connections unless a specific rule explicitly permits them.

Instead of allowing every connection by default, the system accepts only authorized traffic.

For example, a Linux server may block incoming traffic while permitting SSH connections on port 22 and web application traffic on port 8080.

This approach supports stronger access control because unnecessary connections are restricted by default.

## 4. Importance of Cloud Security

Cloud security is essential for protecting applications, infrastructure, and information from unauthorized access.

The Principle of Least Privilege limits unnecessary permissions, attack surface reduction decreases possible entry points, and a Default Deny policy helps control network communications.

When combined with monitoring and regular security updates, these practices provide a stronger foundation for managing cloud infrastructure.

## 5. Conclusion

Understanding fundamental cybersecurity principles is an important part of becoming a cloud security engineer. Proper permission management, reducing exposed services, and implementing restrictive firewall policies can improve the security of Linux-based cloud systems.

These concepts also emphasize that protecting cloud resources requires continuous monitoring, testing, and maintenance.

## References

- National Institute of Standards and Technology. (n.d.). *Least privilege*. https://csrc.nist.gov/glossary/term/least_privilege
- OWASP Foundation. (n.d.). *Attack surface analysis cheat sheet*. https://cheatsheetseries.owasp.org/cheatsheets/Attack_Surface_Analysis_Cheat_Sheet.html
- Ubuntu. (n.d.). *Firewall*. https://documentation.ubuntu.com/server/how-to/security/firewalls/
