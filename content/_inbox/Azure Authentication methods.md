2023-12-19
Tags: #cloud #azure #security 

 Azure supports multiple authentication methods, including standard passwords, single sign-on (SSO), multifactor authentication (MFA), and passwordless.
## Single-sign on (SSO)
SSO enables a user to sign-in one time with an initial authentication and use that credential to access multiple resources and applications from different providers. The benefit of this is that you only need to remember one login, the downside is that SSO is only as secure as that initial authenticator, as the subsequent connections are all based on trusting the credentials you received. 
## Multifactor authentication (MFA)
MFA is the process of prompting a user for extra forms of identification during the sign-in process, very oftenly, this is a secure code from an authenticator app on your phone, or a confirmation message on your phone. This provides an extra level of security, but requires users to set-up a connection or authentication app on their mobile device, and is a real pain in the ass.

Microsoft offers a **Microsoft Entra multifactor authentication** service that provides MFA capabilities and management.
## Passwordless authentication
Very similar to MFA, basically it authenticates the device you're on, and if we trust that device, we can trust you to access services. This can be done with a couple of services:
#### Windows Hello
Seems to be a windows product which authenticates users to their Windows PC using biometric and PIN credentials
#### Microsoft Authenticator app
The standard Microsoft Authenticator app that you set-up on your phone and get a PIN to validate yourself, usually during an MFA log-in but can be used as a passwordless option
#### FIDO2 security keys
Fast IDentity Online (FIDO) Alliance promotes open auth standards, FIDO2 is the latest standard that incorporated the WebAuthn standard.

Usually some kind of key that exists on a USB device, but can also be Bluetooth, or NFC, and this is used for authentication. 

---
# References

https://learn.microsoft.com/en-gb/training/modules/describe-azure-identity-access-security/3-authentication-methods