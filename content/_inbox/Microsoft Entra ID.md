2023-12-19
Tags: #cloud #azure 

Microsoft's cloud-based identity and access management service; a directory service that enables you to sign in and access cloud applications and applications that you develop, it can help you maintain your on-premise AD deployment as well. You can connect Entra ID with your AD so that Entra ID will help protect you by detecting suspicious sign-in attempts.

Microsoft Entra ID provides:
- **Authentication**
- **SSO**
- **Application Management**
- **Device management**
## Microsoft Entra Domain Service
Provides managed domain services such as domain join, group policy, lightweight directory access protocol (LDAP), and Kerberos/NTLM authentication. This provides the benefit of domain services without the need to deploy, manage, and patch domain controllers (DCs) in the cloud.

> A Microsoft Entra Domain Services managed domain lets you run legacy applications in the cloud that can't use modern authentication methods

So it works kind of like a [[Anti-corruption Layer pattern]]

---
# References

https://learn.microsoft.com/en-gb/training/modules/describe-azure-identity-access-security/2-directory-services