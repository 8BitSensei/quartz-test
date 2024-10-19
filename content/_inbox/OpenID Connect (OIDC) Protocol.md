2024-03-13
Tags: #security 

OIDC is a thin layer that sits on top of OAuth 2.0, OAuth 2.0 is designed for *authorisation*, the OIDC layer adds login and profile information about the person who is logged in.   

It allows for *authentication*, and can be used SSO across multiple applications, the flow is almost identical to OAuth 2.0, except a **open-id scope** is passed in the initial request from the **client** to the **authorisation server**, and when it returns the access token, it will also return an **id token** in the form of a **JSON Web Token (JWT)**, which contains obfuscated information about your identity, such as email, address, name, etc.





---

[[OAuth 2.0]] security standard where a user gives an application limited permission to access to your data on another application. 
- **Resource Owner**: the owner of your identity, data, and permissions
- **Client**: the application (A) that wants to access your data or perform an action on behalf of the resource owner
- **Authorisation Server**: application (B) that knows the **resource owner** and has an account of theirs
- **Resource Server**: application's (B) API or service that the **client** wants to access on the **resource owners** behalf

- **Redirect URI**: the URL the **authorisation server** will redirect **resource owner** back to after granting permission to the **client**
- **Response Type**: the type of information the **client** expects to receive, usually an **authorisation code**
- **Scope** the granular permissions
- **Consent**: **Authorisation server** takes the scope the **client** is requesting and verifies it with the **resource owner** e.g. "are you sure you want to give A these permissions?"
- **Client ID**: ID used to identify the **client** with the **authorisation server
- **Secret**: a secret that only the **client** and **authorisation server** know
- **Authorisation code** a short-lived temporary code the **client** gives the **authorisation server** in exchange for an **access token**.
- **Access Token**: key the **client** will use to communicate with the **resource server**

1. You, the **Resource Owner**, want to allow “Terrible Pun of the Day,” the **Client**, to access your contacts so they can send invitations to all your friends.
2. The **Client** redirects your browser to the **Authorization Server** and includes with the request the **Client ID**, **Redirect URI**, **Response Type**, and one or more **Scopes** it needs.
3. The **Authorization Server** verifies who you are, and if necessary prompts for a login.
4. The **Authorization Server** presents you with a **Consent** form based on the **Scopes** requested by the **Client**. You grant (or deny) permission.
5. The **Authorization Server** redirects back to **Client** using the **Redirect URI** along with an **Authorization Code**.
6. The **Client** contacts the **Authorization Server** directly (does not use the **Resource Owner**’s browser) and securely sends its **Client ID**, **Client Secret**, and the **Authorization Code**.
7. The **Authorization Server** verifies the data and responds with an **Access Token**.
8. The **Client** can now use the **Access Token** to send requests to the **Resource Server** for your contacts.




---
# References
https://developer.okta.com/blog/2019/10/21/illustrated-guide-to-oauth-and-oidc