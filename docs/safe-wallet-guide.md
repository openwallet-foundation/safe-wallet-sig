# Safe Wallet Guide

Digital wallets promise to revolutionise the digital interactions of businesses, governments, and people.

Unless they are implemented carefully, they can open new "back-doors" for undesirable surveillance, profiling, and activity correlation of users. This is especially the case when previously closed and tightly controlled usage moves into much wider and larger scale open ecosystems, where control over every possible use case cannot be exerted by a single body. Such larger open ecosystems include national and international scale wallet ecosystems that are rapidly developing right now that take advantage of recent developments in digital credentials and SSI.

Due to the technical complexities of the cryptography and protocols used, there are only a few people that understand what these back-doors are. There is a danger that well intentioned wallet initiatives deploy at scale only to find that they have created a ticking time bomb that will destroy trust in the ecosystem they are fostering once user profiling and correlation becomes commonplace.

The intention of this SIG is to ensure that everyone working on digital wallets, whether technical, legal, or commercial, knows what these dangers are and how to avoid them. It will also provide vital tools that will become the de-facto way to determine how "safe" the new breed of digital wallets is and be able to compare them effectively.

This guide is a non-technical, plain English (minimal jargon) document detailing the best practices for digital wallets for preventing correlation and profiling of users and ensuring they are "safe". This guide will include explanations of how correlation and profiling could occur with "real world" examples and how a bad actor might utilise vulnerabilities. The audience of this guide is legislators, politicians, journalists, members of the public, and advisors. Our hope is that this guide will educate the readers about what “good” looks like and how to recognise it.

We begin the document by first defining "safe" by looking at defining a number of categories that need to be considered. The second part of the document will provide granular best practices for "safe" digital wallets for each of these categories. Lastly, we will look at a scoring mechanism to help people understand how well a given wallet meets the best practices, and in turn, how "safe" the wallet is for a given use case.

## Categories

In this section, we will define ten categories that need to be considered to help us define what "safe" is in the context of digital wallets.

### Privacy
Topics to include:
- Correlation prevention – balance?
- Profiling prevention
- Ensuring the wallet provider does not know what is contained in the wallet

### Security
Topics to include:
- Data security
- Backup and recovery process security
- Key handling & management & custody

### Wallet locking and unlocking mechanisms

### Holder binding
Topics to include
- how to confirm the person who obtained a credential is the one presenting it
- 
#### Content

Wallets are like a toolbox looking to be filled with different tools. Different tools that the citizen will use depending on his needs. 

When we speak about digital identity those tools are the so-called Credentials, each one telling a different aspect of the user: driving license, library membership, etc. Among them one kind of credentials stands out: the personal information credentials. This personal information credentials can be seen as the digital twin of a passport, national ID or any other kind of official ID form and needs to be treated carefully as it will represent the user himself. 

There are two main ways for receiving these personal information credentials: either setup along with the wallet (this is called early binding) or added later when the user requests it to a government agency (this is called late binding). 

The main difference between early and late binding, apart from the moment when the credentials are issued is that late binding allows the user to enjoy the benefits of a wallet prior to having the first personal information credential issued. 

When using the personal information credentials, the user faces a security risk: being impersonated by someone taking control of the wallet. The unlocking mechanism of the wallet may (or not) be enough to warrantee The main difference between early and late binding, apart from the moment when the credentials are issued is that late binding allows the user to enjoy the benefits of a wallet prior to having the first personal information credential issued. 

When using the personal information credentials, the user faces a security risk: the unlocking mechanism of the wallet may not be enough to secure the use of the personal information credentials. Extra mechanism may be used to enhance security: additional PIN/Password, MFA or even using an external device. 

Non evaluation criteria: 

    - Early binding capable wallet 
    - Late binding capable wallet 
    - Both 

Secure wallet evaluation criteria: 

    - No extra security measures 0 pts 
    - Extra PIN/ Password 1 pts 
    - MFA 1 pts 
    - External device 2 pts 
    - In-person at government agency PIN/Password change only 2 pts
    - Other methods (confirmation call or text) 1 pts

These extra security steps should derive in an associated confirmation method that the verifier/relying party can double check.

### Legislation compliance
Topics to include:
- What legislation exists?
    - GDPR, CCPA
- Where does this legislation exist?
- How much to rely on legislation vs. technical solutions

### Certification
Topics to include:
- where is certification required?
- which certification(s) are required?
- who/what needs to be certified?

### User interface
Topics to include:
- how well informed can the user be 
- how does the user "feel" safe
- consent

### Counterparties
Topics to include:
- How do you know who you are dealing with (is the issuer/verifier (or other holder) who they say they are)
- How do you know that what they are asking for is OK

### Audit
Topics to include:
- how a holder knows what they’ve done
- could a court audit your wallet for criminal proceedings?

### Accountability
Topics to include:
- who do you sue if something goes wrong?

## Best Practices
This section will define the best practices for the each of the above categories.

## Scoring Mechanism
This section looks at a scoring mechanism that will allow people to understand how well a given wallet meets the best practices, and in turn, how "safe" the wallet is for a given use case.

Example:

| **Category**           | **Score** |
| ---------------------- | --------- |
| Privacy                | <img alt="4 stars" src="images/4-stars.png" width=100px> |
| Security               | <img alt="3 stars" src="images/3-stars.png" width=100px> |
| Legislation Compliance | <img alt="5 stars" src="images/5-stars.png" width=100px> |
| User Interface         | <img alt="4 stars" src="images/4-stars.png" width=100px> |
| Accountability         | <img alt="2 stars" src="images/2-stars.png" width=100px> |

**NOTE**: In order to be a "safe" wallet, the context of how that wallet will be used should be considered. Specifically, one wallet might heavily favor the "Legislation Compliance" category, while another may favor "Privacy". 
