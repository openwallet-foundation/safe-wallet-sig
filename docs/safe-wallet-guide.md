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

| **Category**           | **Score** |
| ---------------------- | --------- |
| Privacy                | <img alt="4 stars" src="images/4-stars.png" width=100px> |
| Security               | <img alt="3 stars" src="images/3-stars.png" width=100px> |
| Legislation Compliance | <img alt="5 stars" src="images/5-stars.png" width=100px> |
| User Interface         | <img alt="4 stars" src="images/4-stars.png" width=100px> |
| Accountability         | <img alt="2 stars" src="images/2-stars.png" width=100px> |

**NOTE**: In order to be a "safe" wallet, the context of how that wallet will be used should be considered. Specifically, one wallet might heavily favor the "Legislation Compliance" category, while another may favor "Privacy". 
