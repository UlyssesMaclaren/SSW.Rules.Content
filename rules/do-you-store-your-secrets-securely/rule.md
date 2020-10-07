---
type: rule
title: Do you store your secrets securely?
uri: do-you-store-your-secrets-securely
created: 2016-04-28T19:19:40.0000000Z
authors:
- id: 1
  title: Adam Cogan
- id: 32
  title: Mehmet Ozdemir
- id: 34
  title: Brendan Richards
- id: 63
  title: Andrew Lean

---

Most systems will have variables that need to be stored securely; OpenId shared secret keys, connection strings, and API tokens to name a few.

These secrets  **must not**  be stored in source control in plain text – it is insecure by nature, and basically means that it is sitting.
 
There are many options for managing secrets in a secure way:

### Bad Practices


[greyBox] 
### Store production passwords in source control protected with the <br>      [ASP.NET IIS Registration Tool](https&#58;//msdn.microsoft.com/en-us/library/zhhddkxy.aspx)

Pros:

- Minimal change to existing process – no need for <br>         [DPAPI](https&#58;//msdn.microsoft.com/en-us/library/ms995355.aspx)or a dedicated Release Management (RM) tool.
- Simple and easy to understand


Cons:

- Need to manually give the app pool identity ability to read the default RSA key container.
- Difficult to manage production and non-production config settings
- Developers can easily decrypt and access the production password.
- Manual transmission of the password from the key store to the encrypted config file.

 [/greyBox]
Figure: Bad practice - Overall rating: 2/10
    
[greyBox] 
### Use Windows Identity instead of username/ password.

Pros:

- Minimal change to existing process – no need for DPAPI or a dedicated RM tool.
- Simple and easy to understand


Cons:

- Difficult to manage production and non-production config settings
- Not generally applicable to all secured resources.
- Can hit firewall snags with Kerberos and AD ports
- Vulnerable to DOS attacks related to password lockout policies
- Has key-person reliance on network admin

 [/greyBox]
Figure: Bad practice - Overall rating: 4/10   
[greyBox] 
### [Use External Configuration Files](https&#58;//docs.microsoft.com/en-us/aspnet/identity/overview/features-api/best-practices-for-deploying-passwords-and-other-sensitive-data-to-aspnet-and-azure)


Pros:

- Simple to understand and implement


Cons:

- Makes setting up projects the first time very hard.
- Easy to accidentally check the external config file into source control.
- Still need DPAPI to protect the external config file.
- No clear way to manage the DevOps process for external config files.

 [/greyBox]
Figure: Bad practice -  Overall rating: 1/10


### Good Practices

[greyBox] 
### Use Octopus/ VSTS RM secret management, with passwords sourced from KeePass


Pros:

- Scalable and secure.
- General industry best practice - great for organizations of most sizes below large corporate.


Cons:

- Password reset process is still manual
- DPAPI still needed.

 [/greyBox]
Figure: Good practice - Overall rating: 8/10



[greyBox] 
### Use Enterprise Secret Management Tool – LastPass/ Hashicorp Vault/ etc..

Pros:

- Enterprise grade – supports cryptographically strong passwords, auditing of secret access and dynamic secrets
- Supports hierarchy of secrets
- API interface for interfacing with other tools.
- Password transmission can be done without a human in the chain.


Cons:

- More complex to install and administer
- DPAPI still needed for config files at rest

 [/greyBox]
Figure: Good practice -  Overall rating: 8/10


[greyBox] 
### Use Azure KeyVault

See the SSW Rewards mobile app repository for how SSW is using this in a production application:           [https://github.com/SSWConsulting/SSW.Rewards](https&#58;//github.com/SSWConsulting/SSW.Rewards)

Pros:

- Best solution for cloud (Azure) solutions
- Enterprise grade
- Uses industry standard best encryption
- Dynamically cycles secrets
- Access granted based on Azure AD permissions - no need to 'securely' share passwords with colleagues
- Can be used to inject secrets in your CI/CD pipelines for non-cloud solutions




Cons:

- Price is per transaction - can become costly if used in high volume and not managed thoroughly (see SSW's William Liebenberg on Azure SpendOps: <br>            [https://azuregems.io/spendops-with-azure-cosmos-db/](https&#58;//azuregems.io/spendops-with-azure-cosmos-db/)



 [/greyBox]
Figure: Good Practice - Overall rating 9/10
