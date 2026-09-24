# Windows Active Directory Security Home Lab

## Project Overview

This project demonstrates the deployment and security configuration of a Windows Active Directory environment using Oracle VirtualBox.

I built a Windows Server 2025 Domain Controller, created the `jsec.local` domain, joined a Windows client workstation to the domain, configured Active Directory users and groups, implemented Group Policy security controls, configured NTFS permissions, and investigated Windows Security events.

## Lab Environment

- Oracle VirtualBox
- Windows Server 2025
- Windows Client Workstation
- Domain Controller: DC01
- Domain: jsec.local
- Client Computer: CLIENT01

## Active Directory Configuration

I created an organizational structure for managing users and computers.

Organizational Units (OUs):

- JSEC-Users
  - Finance
  - HR
  - IT
  - Security
- JSEC-Computers
- JSEC-Groups
- JSEC-Servers

I also created domain users and security groups to practice centralized identity and access management.

## Group Policy Security

I created a Group Policy Object named:

`JSEC-Workstation-Security`

The account lockout policy was configured with:

- Account lockout threshold: 5 invalid logon attempts
- Account lockout duration: 10 minutes
- Reset account lockout counter after: 10 minutes

The policy was applied to the CLIENT01 workstation.

## NTFS Permissions and Least Privilege

I configured an IT department folder and used Active Directory security groups to control access.

The `JSEC\IT-Security` group was granted Modify permissions.

An authorized IT user was able to access the resource, while an HR user without the required permissions was denied access.

This demonstrates:

- NTFS permissions
- Access Control Lists (ACLs)
- Group-based authorization
- Least privilege

## Security Testing

I performed a controlled account-lockout test against a domain user account.

After the configured failed-login threshold was reached, Active Directory locked the account.

The account was then unlocked by an administrator and normal authentication was restored.

## Windows Event Log Investigation

I investigated authentication activity using Windows Event Viewer.

Important Security Event IDs observed:

- 4625 — Failed logon
- 4740 — User account locked out
- 4624 — Successful logon

The investigation demonstrated the following sequence:

`Failed Logon → Account Lockout → Administrator Recovery → Successful Logon`

## Skills Demonstrated

- Windows Server Administration
- Active Directory Domain Services (AD DS)
- DNS
- Domain Join
- Organizational Units
- Active Directory Users and Groups
- Group Policy
- Account Lockout Policies
- NTFS Permissions
- Access Control Lists
- Least Privilege
- Windows Event Viewer
- Authentication Monitoring
- Basic Security Incident Investigation

## Project Evidence

The project screenshots document:

1. Windows Server / Domain Controller configuration
2. Active Directory OU structure
3. CLIENT01 domain computer
4. Group Policy account lockout configuration
5. IT department NTFS permissions
6. Account lockout Event ID 4740
7. Successful authentication Event ID 4624

## Conclusion

This home lab provided hands-on experience deploying, administering, securing, and monitoring a Microsoft Active Directory environment.

The project demonstrates practical skills related to identity and access management, endpoint security, authentication controls, least privilege, security monitoring, and incident investigation.