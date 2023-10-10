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

| Regulation                              | Acronym | Year | Country |
| --------------------------------------- | ------- | ---- | ------- |
| General Data Protection Regulation      | GDPR    | 2018 | EU      |
| California Consumer Privacy Act         | CCPA    | 2020 | US/CA   |
| General Personal Data Protection Law    | LGPD    | 2020 | Brazil  |
| Digital Charter Implementation Act 2022 | DCIA    | 2022 | Canada  |
| Digital Personal Data Protection Act    | DPDPA   | 2024 | India   |

- What regulations issues need to be addressed? 
- Where does this legislation exist?
- How much to rely on legislation vs. technical solutions?
- Some of the identified legislative issues related to wallet based data exchanges are summarised below: 
  - Legislations that organisations need to adhere to while processing data. E.g. Article 30 of the GDPR places an obligation on controllers and processors (organisatons, issuers/verifiers) to have in place within their organisations a detailed record ofactivities the organisation carries out which use personal data.
  - Legislations that ensures the digital rights of the individuals are taken care of. E.g. The GDPR has a chapter on the rights of data subjects (individuals) which includes the right of access, the right to rectification, the right to erasure, the right to restrict processing, the right to data portability, the right to object and the right not to be subject to a decision based solely on automated processing.
  - Article 7 (1) of GDPR states that in situations where processin of data is based on consent, the controller shall be able to demonstrate that the data subject has consented to processing of his or her personal data.

### Certification
Topics to include:
- where is certification required?
- which certification(s) are required?
- who/what needs to be certified?

### User interface

#### UX rules

- Intuitive navigation: The wallet should be easy to navigate, with clear and concise labels for all functions. Users should be able to quickly and easily find the information and features they need.
- Visual cues: The wallet should use visual cues, such as icons and colors, to help users understand what they are doing. For example, a green check mark could be used to indicate that a transaction was successful.
- Security features: The wallet should use the latest security features to protect users' data and funds. This could include features such as two-factor authentication, biometric login, and data encryption.
- Transparency: The wallet should be transparent about its security features and how it protects users' data. This information should be easy to find and understand.
- User feedback: The wallet should provide users with feedback on their actions. For example, the wallet should notify users when a transaction is successful or when there is a problem.

#### Best practices

- Use a strong and unique password. Your password should be at least 12 characters long and include a mix of upper and lowercase letters, numbers, and symbols. Do not use the same password for your digital wallet as for any other online accounts.
- Enable multi-factor authentication (MFA). MFA adds an extra layer of security to your account by requiring you to enter a code from your phone in addition to your password when logging in.
- Keep your device up to date. Software updates often include security patches, so it is important to keep your device up to date with the latest version of the operating system and security software.
- Be careful about what links you click on and what apps you download. Phishing scams and malicious apps are common ways for attackers to steal your personal information and financial data. Only click on links from trusted sources and download apps from official app stores.
- Monitor your account activity regularly. Review your account statements regularly to look for any unauthorized transactions. If you see something suspicious, contact your digital wallet provider immediately.

In addition to these best practices, it is also important to be aware of the latest security threats and scams. For example, attackers are increasingly using social engineering techniques to trick users into revealing their personal information or clicking on malicious links. Be suspicious of any unsolicited contact from your digital wallet provider or other financial institutions.

By following these tips, you can help keep your digital wallet safe and secure.

#### Resources and References

- UI/UX Design for Digital Wallets: Marrying Security with Intuitive Navigation | by Ethercess | Sep, 2023 | Medium
https://medium.com/@ethercess/ui-ux-design-for-digital-wallets-marrying-security-with-intuitive-navigation-61acaa66a2c8 
medium.com
- The Role of UX/UI Design in Cryptocurrency Wallet Development | by Naeem Hasan | Oct, 2023 | Medium
https://medium.com/@naeemhasan588/the-role-of-ux-ui-design-in-cryptocurrency-wallet-development-3f1fbe97b747 
medium.com
- 7 Best Practices For Enhancing Your Digital Wallet Security
https://www.appknox.com/blog/best-practices-for-digital-wallet-security 
www.appknox.com
- Digital Wallet Design: Enhancing Your User Experience
https://qubstudio.com/blog/digital-wallet-design/ 
qubstudio.com
- How to Improve Mobile UX with Digital Wallets
https://cxl.com/blog/digital-wallets/ 
cxl.com

### Counterparties

A counterparty in this context is a person, organisation or thing to whom a digital wallet is connecting to in order to execute a transaction of some sort. The counterparty could be an issuer of credentials, an online shop requesting age verification, a police officer, or a passport e-gate.

- Counterparty Identity Verification
    - Does the wallet inform the user that the counterparty that they are interacting with is who they say they are? For example:
        - If the user is being offered a new digital credential by an organisation, is the user able to quickly and easily determine that the organisation is legitimate?
        - If the user is being asked to digitally sign a contract, can the user quickly ascertain that the requestor is who they say they are?
        - Can the user proactively send a verification request to an organisation (or another user) to ask them to prove who they are?
    - Is the user able to see several levels of detail about the counterparty? For example:
        - Level 1: a visual confirmation (green tick style) that the counterparty has been vouched for by some authority.
        - Level 2: detail about the counterparty’s identity, for example company name, registered address, company number, and who has vouched for them.
        - Level 3: detail about the vouching that has taken place e.g. digital signature matches, vouching organisation process, Legal Entity Identifier details etc.
-	Counterparty Action Verification
    - Can the user quickly and easily determine that the counterparty is allowed to ask what they are asking, and if it is a reasonable request?
        - Some data sharing transactions may be limited by regulation, restricting who is allowed to ask for what. Is this communicated to the user? 
        - Does the wallet automatically reject illegal requests? If so, how does it know a specific request from a specific issuer is illegal in one specific jurisdiction and legal in another?
        - Is a user able to determine that “Gerald’s Corner Shop” is not a legitimate issuer of driving licenses? How can a user know that a credential they are being offered is coming from a legitimate source?
        - When not limited by regulation, are there common-sense limits to what should be shared? Is the wallet able to alert the user when it detects oversharing?
    - How much hand-holding is provided to the user by the wallet to guide them through this new world of digital credentials?

### Audit

Audit in this context is the ability of participants in a digital credential ecosystem to know what is happening in that ecosystem. It is tightly linked with the Privacy and Legislation Compliance topics. 

Audit requirements and Privacy requirements can clash. Care will need to be taken to design a digital wallet that handles both in the best way. The balance user privacy and regulation is also an important topic, even more so when multiple competing regulations may be involved.

- User Audit.
    - Is a wallet user able to see all the transactions that they have carried out with their digital wallet?
    - Can these transactions be used as proof of activity e.g. proof of purchase?
    - Can they delete their own transaction list in an unrecoverable way?
- Governance & Operational Audit
    - If an ecosystem has one or more governance bodies, do they have tools that enable them to audit the correct operation of the ecosystem?
        - For example, if a relying party is asking for more data than it is allowed to, can the governance body see proof of this to stop it happening again?
- Legal Audit.
    - Can a user prove to a legal authority that they have undertaken some action with their wallet i.e. can the wallet provide legally binding transaction evidence?
    - Does a wallet satisfy local regulatory audit requirements for example can legal authorities examine the content and transaction history of a user’s wallet as part of a criminal investigation?
    - Can a legal authority look at the transaction history of an issuer/verifier and prove that a user interacted with them without looking at the user’s wallet?

### Accountability
Topics to include:
- who do you sue if something goes wrong?

## Best Practices
This section will define the best practices for the each of the above categories.

## Scoring Mechanism
This section looks at a scoring mechanism that will allow people to understand how well a given wallet meets the best practices, and in turn, how "safe" the wallet is for a given use case.

Example:

| **Category**           | **Score**                                                |
| ---------------------- | -------------------------------------------------------- |
| Privacy                | <img alt="4 stars" src="images/4-stars.png" width=100px> |
| Security               | <img alt="3 stars" src="images/3-stars.png" width=100px> |
| Legislation Compliance | <img alt="5 stars" src="images/5-stars.png" width=100px> |
| User Interface         | <img alt="4 stars" src="images/4-stars.png" width=100px> |
| Accountability         | <img alt="2 stars" src="images/2-stars.png" width=100px> |

**NOTE**: In order to be a "safe" wallet, the context of how that wallet will be used should be considered. Specifically, one wallet might heavily favor the "Legislation Compliance" category, while another may favor "Privacy". 
