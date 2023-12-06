# Safe Wallet Guide

> [!WARNING]  
> **Please do not edit this document in GitHub**!
> 
> The Safe Wallet Guide has been transitioned to a [Google Doc](https://docs.google.com/document/d/1jrxQ2ASDeSt3ZQqmRG4i1gGj5bLPIuNE/edit?usp=drive_link&ouid=111902059063316257481&rtpof=true&sd=true) and will be ready for general review and updates by **08-DEC**
> If you want to contribute, please use the online version of the document:
> * [Safe Wallet Guide in Google Docs](https://docs.google.com/document/d/1jrxQ2ASDeSt3ZQqmRG4i1gGj5bLPIuNE/edit?usp=drive_link&ouid=111902059063316257481&rtpof=true&sd=true)  
  

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

In the context of digital wallets, privacy primarily relates to the how a user’s activities are protected from unwanted observation, tracking and correlation. Digital wallets and credentials, and the protocols involved in their issuance and verification, introduce a new set of challenges that don’t exist in the world of physical (paper and plastic) credentials.

-	Unique Identifiers
    - Does the wallet avoid use of a holder-specific or wallet-specific unique identifier that gets shared, without holder choice, with every transaction in the transaction metadata?
        - Such an identifier will be akin to a tracking beacon that allows all holder activities to be correlated across all usage. It would allow any colluding entities to correlate all activities of a holder.
        - This is particularly dangerous when proxy verification services are used, that process verifications for many relying parties and will be able to see and track such an identifier and profile the behaviours of all holders.
        - An example of such an identifier is a wallet serial number.
    - Does the wallet prevent use of credentials that contain credential-specific unique identifiers in metadata that are shared, without user choice, in every transaction that uses that credential?
        - While not as privacy impacting as a holder/wallet specific identifier, a credential-specific identifier in metadata that the user cannot avoid sharing will allow all use of that credential to be correlated.
        - An example of a credential-specific identifier in metadata is a revocation index position or an issuer signature.
-	Decoupling issuers and verifiers
    - Does the wallet and its associated ecosystem prevent issuers from seeing where, when or why holders use their credentials?
        - It is essential that issuers of credentials like governments and banks cannot track the use of those credentials. 
        - If issuers can track the use of their credentials, it should be expected that they will.
        - If they do, they will quickly build up profiles of the lives of their users/customers.
        - An example of decoupling is preventing a verifier from contacting the issuer to check the revocation status of a credential. If this happened, the issuer would know the holder of the credential was using it at that issuer. This is also known as the “phone home” problem.
-	Wallet provider privacy
    - The developers and operators of digital wallets must not be able to observe or track transactions undertaken by holders.
        - This is particularly important in the case of hybrid and pure cloud wallets where transactions are performed on the wallet operator’s infrastructure.
        - Wallet operators must not be able to observe the content of backups that are held by those wallet providers.
-	Credential exchange platform providers and proxy services.
    - Organisations that provide the infrastructure that wallets connect to in order to issue or verify credentials (typically called credential exchange platforms) must not be able to examine the content, source or destination of wallet transactions.
        - In many situations, such credential exchange platforms will need to “translate” from an encrypted credential envelope to/from clear text for integration with other systems such as customer onboarding systems.
        - In this case, the credential exchange platform must manage the data in such a way that it is transient and not stored, observable or trackable to protect wallet holder privacy.
    - Proxy services may provide credential issuance/verification services for many issuers and verifiers. In doing so they could observe and correlate wallet transactions across large ecosystems. 
        - Proxy services must not observe, store and correlate wallet transactions.
        - Holders should be informed that they are dealing with a proxy service rather than the true end issuer/verifier.


### Security
Topics to include:
- Data security
- Backup and recovery process security
- Key handling and management and custody

According to the European Union(1) a digital wallet _will provide a secure and convenient way for European citizens and business to  __**share identity data **__ needed for accessing digital services such as checking in at the airport, renting a car, opening a bank account, or when logging in to their accounts on large online platforms._

(1)[https://digital-strategy.ec.europa.eu/en/policies/eudi-wallet-toolbox](https://digital-strategy.ec.europa.eu/en/policies/eudi-wallet-toolbox)

At its most basic, a digital wallet is a holder-controlled digital container sitting between Issuers of Verifiable Credentials and a Relying Party that authorizes access to services. It is a critical confluence point and must be able to establish, maintain and attest to the trusted processes which are required for a trustworthy Digital Wallet. DIACC's Digital Wallet Component Conformance Criteria (2) states: "The integrity of a Trusted Process is paramount because many Participants may rely on the output of the process, often across jurisdictional, organizational, and sectoral boundaries."

(2) [PCTF Digital Wallet Confoce Profile Candidate for Final Recommendation V1.0 (diacc.ca)](https://diacc.ca/wp-content/uploads/2023/04/PCTF-Digital-Wallet_Conformance-Profile-Final-Recommendation-V1.0.pdf)

To support the trusted processes, a wallet must support fundamental functions such as:

1. Wallet Selection
2. Key Management
3. Credential Signature / Format
4. Credential Management
5. Presentation Protocols
6. Mechanisms to convey Consent

Wallets also play a pivotal role in foundational identity outcomes such as privacy and architectures must be underpinned by strong security controls, and attestations to the context, method and strength of those controls. Security specifications for wallets should ensure performance in a manner tailored for identity-based applications and be specific to the level of assurance required by both the Issuer and Verifier.

![](./images/security.png)

#### Functional elements for security consideration

Security Considerations for wallets to support fundamental functions while mitigating risks for growing attack surfaces and vectors on consumer devices must be factored into the design of the wallet architecture. In a decentralized model, where multiple parties are part of the identity flow maintaining security control across domains and devices is necessary to achieve, and attest to the necessary levels of assurance that are foundational to the establishment of trust, assurance of privacy and the efficacy necessary to create a positive and adoptable wallet-holder experience. DIACC's Digital Wallet Component Includes a comprehensive detailing the Type of Risk, Threat Category, Impact and proposed Mitigation.

Ref(3): [PCTF Digital Wallet Conformance Profile Candidate for Final Recommendation V1.0 (diacc.ca)](https://diacc.ca/wp-content/uploads/2023/04/PCTF-Digital-Wallet_Conformance-Profile-Final-Recommendation-V1.0.pdf)

Expanding on the foundational work DIACC has done, this document provides examples of three functional security elements, with standards references where applicable:

#### Key Management

| **FUNCTION(s)** | **OUTCOME** | **STANDARDS REFERENCE (example)** |
| --- | --- | --- |
| Key Storage: Trusted Execution Environment(s) | 1. Hardware backed Trusted Execution Environment (e.g. TEE, TPM, (e)SE) | ISO/IEC 7816 / EMV BOOK E Security & Key Management v1.0 June 2023 |
|   | 2. Software backed Trusted Execution Environment | ISO/IEC 7816 / EMV BOOK E Security & Key Management v1.0 June 2023 |
| Key Management: | The set of functions required to be present in every wallet | ISO/IEC 7816 / EMV BOOK E Security & Key Management v1.0 June 2023 |
| Key | A sequence of symbols that controls the operation of a cryptographic transformation (EMV) | ISO/IEC 7816 / EMV BOOK E Security & Key Management v1.0 June 2024 |
| Key Expiry | The date after which a signature made with a particular key is no longer valid | ISO/IEC 7816 / EMV BOOK E Security & Key Management v1.0 June 2025 |
| Key Introduction | The process of generating, distributing and beginning the us of a key pair | ISO/IEC 7816 / EMV BOOK E Security & Key Management v1.0 June 2026 |
| Key Life Cycle | All phases of key management from generation, through revocation, destruction and archiving | ISO/IEC 7816 / EMV BOOK E Security & Key Management v1.0 June 2027 |
| Key Replacement | The simultaneous revocation of a key and introduction of a key to replace the revoked one | ISO/IEC 7816 / EMV BOOK E Security & Key Management v1.0 June 2028 |
| Key Revocation | The key management process of withdrawing a key from service and dealing with the legacy of its use. Key revocation can be as scheduled or accelerated. | ISO/IEC 7816 / EMV BOOK E Security & Key Management v1.0 June 2029 |
| Key Revocation Date | The date after which no legitimate cards still in use should contain certificates signed by this key, and therefore the date after which this key can be deleted from terminals. For a planned revocation the Key Revocation Date is the same as the key expiry date. | ISO/IEC 7816 / EMV BOOK E Security & Key Management v1.0 June 2030 |
| Key Withdrawal | The process of removing a key from service as part of its revocation. | ISO/IEC 7816 / EMV BOOK E Security & Key Management v1.0 June 2031 |

#### Wallet Application - Container

| **FUNCTION(s)** | **OUTCOME** | **STANDARDRS REFERENCE (example)** |
| --- | --- | --- |
| Mechanisms for Device Attestation: device hardware identifier proofs | 1. Device legitimization | EMV/SBMP |
| Software Protection: white box crypto, device binding, root detection, anti-instrumentation, tamper-detection, anti-emulation, obfuscation, | 1. Prevent data from compromise while captured, processed & stored on the mobile device | EMV/SBMP |
| Secure Data Exchange (NFC, Bluetooth, Cellular, Wi-Fi, Infrared): - Modify wireless vendor default encryption keys, passwords and SNMP community strings & transmission encryption | 1. Data protection and/or Interception prevention during exchange between wallet & external devices & verified relationships. | EMV/SBMP |
| Protect removable media (SIM card, SD card) | 1. SIM , SD attack prevention |   |
| Drive Biometric readers (camera (face, iris) touch (fingerprint), voice, hand geometry,…… | 1. Disabled 'master prints' |   |
| Hardware attestation | 1. Proof of mobile device hardware identifiers, such as serial number or IEMI |   |
| Relationship Identity Establishment | Process to uniquely identify & establish a relationship between the wallet and an external party for each program/service: can be both internal (ie an app) or external |   |
| Relationship Type(s), Verification & Validation | Process(es) to uniquely validate & verify each external party that will interact with the wallet |   |
| Relationship Resolution & Maintenance | Change control and maintenance process(es) for identified external parties |   |

#### Threat Minimum Compensation

| **ATTACK VECTOR** | **STANDARDS REFERENCE (Example)** |
| --- | --- |
| 1. Bypass of mobile payment platform security controls | EMV |
| 2. Reverse Engineering of Wallet source code | EMV |
| 3. Modification of Wallet source code | EMV |
| 4. Interface exploitation between Wallet product components | EMV |
| 5. Extraction of assets run time | EMV |
| 6. Static analysis: Disassembly, recompilation, de-obfuscation | EMV |
| 7. Code modification - bypass security mechanisms, inject malicious code | EMV |
| 8. Dynamic analysis: exploitation of debugging fetuses, unprotected lifecycle phases, hooking | EMV |
| 9. Perturbation attacks | EMV |
| 10. Differential fault analysis (single or multiple faults) | EMV |
| 11. Side channel analysis | EMV |
| 12. RNG attacks | EMV |
| 13. Software attacks: ie protocol, man-in-the-middle, replay, downgrade attacks, unknown key share / impersonation, certificate misuse | EMV |
| 14. Logical attacks: ie application, segregation, IPC exploitation, fuzzing | EMV |

### Wallet locking and unlocking mechanisms

As in all the systems the weakest link marks the security of the solution. In the case of the wallet it is usually the citizen the weakest link because he can tricked.
Usually a wallet has several functions: storing attributes, signing documents, presenting the attributes to a verifier, etc.
Those functions should be protected against malicious actors or user errors, that can be achieved with additional layers of protection and verifications.

Unlock the wallet when activating it may have a metric depending on:
- Complexity of the unlocking mechanism.
  - Simple PIN, 1 point
  - Complex password, 2 points
  - MFA, +1 point
  - External unlocking mechanism, like hardware key, 3 points
- Frequency of the unlocking requirement
  - Only while opening,1 point
  - Each time the wallet loses focus, 2 points (this has to be reviewed for the cases that copy and paste is required)
  - Each time the device (smartphone) is locked or suspended, 1 point
  - 
Multiple layers of unlocking. Whenever advanced or higher level of assurance operations require additional unlocking:
  - No additional unlocking, 0 points
  - PID and document signatures requires additional unlocking, 1 points
  - Additional unlocking uses different PIN/Password, +1 point
  - Wallet checks additional unlocking have not the same PIN/Password, +1 point
    
Biometrics
  - Biometrics enabled for wallet unlocking, 1 point

### Holder binding

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

#### Biometrics in Holder binding

Nowadays most of the ID documents have an electronic interface. From NFC to integrated chips these interfaces allow a form to access to the ID information in an electronic way.
This is very convenient for a verification, and some of that electronic information is biometric information, so we can think on using the biometric information in the ID document to load it into a wallet.
This biometric information in the wallet could lead to a safer holder binding so when an ID request comes the user could potentially use the biometrics in the device, match with the stored identity and send it to the verifier requesting it.
Unfortunately, this is only safe if the verification is done in a verifier server, not in the wallet device. Why? Because the devices could be tampered, and the applications hacked. An application running in a user device could be modified so it will send the verifier an “Biometrics match” even if not. The proper way to perform biometrics verification is that the device directly sends the audio/video stream to a server, then the server matches the information with the electronic ID information (that is signed and cannot be tampered) and then decide if there is a match.
Here comes the question: “I do use the biometrics in my device to access my bank account? Am I not safe?” Albeit if looks that the same procedure is happening indeed it is not. When you use the biometrics in your phone to access your bank account what happens is that your device is not sending the biometric information. Whenever you did configure the biometrics, your smartphone did store your bank account access details and only access them when your biometrics match with the ones stored in the device. Your bank (acting as a verifier) never has access to those biometrics. 
There’s an evolution on this, usually related to strong costumer verification, when in addition to access to a service there’s a biometric (usually voice) authentication from your bank (like saying “I do authorize this transaction”): that is the first example. The server from your bank received the stream of data and process the biometrics, matching against the information they have from you.

Biometrics linking evaluation criteria:
-	Server side verification: 1 point
-	Other: 0 point


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
> *Control text, we can remove it when we finish with the content of this section* 
> 
> Topics to include:
> - where is certification required?
> - which certification(s) are required?
> - who/what needs to be certified?
>

Certification in the context of digital identity wallets relates to the formal evaluation of products according to standards such as Common Criteria. It is closely associated with the Legislation Compliance topic, since digital wallet regulations in some cases include specific certification requirements.
- Compliance with regulations:
  - Are there any regulations that require certification of digital wallets for the countries or regions in scope? (Example: The eIDAS2 regulation, where EUDI Wallet certification is mandatory.)
  - If so, does the digital wallet comply with the national or regional certification requirements?
- Components to be certified:
  - Does the digital wallet mobile app have to be certified, and to which certification standard? If so, is the digital wallet certified? (Example: FITCEM certification.)
  - Does the secure element in the mobile device have to be certified, and to which certification standard? If so, is the secure element certified? (Example: Common Criteria or GlobalPlatform certification.)
  - Does the digital wallet backend have to be certified, and to which certification standard? If so, is the digital wallet backend certified? (Example: ISO 27001 audit.)
  - Are there any other components in the digital wallet eco-system to be certified, and to which certification standard? If so, are the other components certified?  (Example: HSMs that are Common Criteria or FIPS 140-2 certified.)
- Evidence of certification:
  - Does the digital wallet provide evidence to the user that its certification is up to date? (Example: There could be information on the digital wallet’s screen that can be tapped on to get more details.)
  - Is there a certification body (in the applicable country) that publishes lists of certified digital wallets?
  - Does the certification body publish certificates or reports about the digital wallet certifications?

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
- Governance and Operational Audit
    - If an ecosystem has one or more governance bodies, do they have tools that enable them to audit the correct operation of the ecosystem?
        - For example, if a relying party is asking for more data than it is allowed to, can the governance body see proof of this to stop it happening again?
- Legal Audit.
    - Can a user prove to a legal authority that they have undertaken some action with their wallet i.e. can the wallet provide legally binding transaction evidence?
    - Does a wallet satisfy local regulatory audit requirements for example can legal authorities examine the content and transaction history of a user’s wallet as part of a criminal investigation?
    - Can a legal authority look at the transaction history of an issuer/verifier and prove that a user interacted with them without looking at the user’s wallet?

### Accountability
Topics to include:
- who do you sue if something goes wrong?

Counterparty identification and verification, audit, and wallet certification can all be for naught if the responsible parties cannot ultimately be held accountable. Like most Safe Wallet categories, requirements for accountability can be divided into: a) technical mechanisms (those that can be implemented with hardware, software, and protocols) and, b) governance mechanisms (those that must be implemented by humans following prescribed laws, regulation, policies and/or rules, including via [reputation systems](https://en.wikipedia.org/wiki/Reputation_system)).

#### Checklist for Technical Accountability Mechanisms

These are functions of a digital wallet required to produce what a court of law will consider [admissible evidence](https://en.wikipedia.org/wiki/Admissible_evidence) of the actions of the relevant parties in the case of harm or damage resulting from reliance on the wallet or its contents. Without such evidence, it would be all but impossible to hold specific parties accountable.

1. **Does the wallet provide secure storage of cryptographic keys, credentials, and digital assets?** If a defense lawyer can create reasonable doubt that the keys, credentials, or assets in a digital wallet were secure, it becomes very difficult to hold the relevant parties accountable since all of them have plausible deniability that they took the harmful action.
1. **Does the wallet digitally sign credentials, messages and transactions?** Only by applying a digital signature to each action taken by the relevant parties can that action be tied directly to the use of a particular digital wallet in a particular interaction.
1. **Does the wallet produce a secure audit log of user and counterparty interactions and transactions?** As described in the Audit category (above), only by keeping a history of all the digitally signed transactions will the wallet holder be able to produce evidence of the alleged harmful actions.
1. **Does the wallet provide alerts for unsafe interactions?** In addition to compiling evidence, a Safe Wallet can also implement “accountability by design” by designing the wallet software to alert either: a) the user, b) a governing body (such as a consumer protection agency), or c) both if the wallet detects anomalous behavior or a clear policy violation. This “thousand eyes” approach can be a highly effective deterrent for many bad behaviors and dark patterns online. 
1. **Does the wallet provide AI-assisted monitoring for unsafe interactions?** Alert monitoring can be further enhanced by personal AI functionality provided it is privacy-respecting and operates exclusively on the wallet holder’s behalf.
1. **Does the wallet have integrated technical support for a [reputation system](https://en.wikipedia.org/wiki/Reputation_system)?** This is the necessary technical enablement for user-generated reputation (see #7 below).

#### Checklist for Governance Accountability Mechanisms

While technical mechanisms can produce evidence or notification of harmful actions, ultimate accountability resides in the ability to take enforcement action when necessary. This can be supported by any combination of the following governance mechanisms.

1. **Is the wallet certified, and if so, under what certification programs, for what assurance levels, with what trust marks?** Many governance frameworks will specify certification requirements for digital wallets as well as for issuers and verifiers of specific digital credentials.
1. **Is the wallet conformant with relevant governmental regulations?** Many types of digital harms are already covered by existing laws and regulations, including commercial codes, consumer protection laws, and data protection and privacy regulations.
1. **Is the wallet conformant with relevant governance frameworks (aka trust frameworks)?** Digital wallets, agents, and credentials can be issued, held, and verified under the policies of a [governance framework](https://docs.google.com/document/d/1fZByfuSOwszDRkE7ARQLeElSYmVznoOyJK4sxRvJpyM/edit#heading=h.2x05z0r097mn) published by the relevant [governing body](https://docs.google.com/document/d/1fZByfuSOwszDRkE7ARQLeElSYmVznoOyJK4sxRvJpyM/edit#heading=h.1wptecwzvuvz). Specifications, tools and models for digital governance frameworks are published by the [Trust Over IP (ToIP) Foundation](https://trustoverip.org/); best practices for digital trust frameworks are published by the [Open Identity Exchange](https://openidentityexchange.org/).
1. **Is the wallet audited for continued conformance? On what frequency?** Most certification programs will require either periodic or on-demand audits of the wallet hardware and/or software, as well as audits of issuers and/or verifiers.
1. **Does the wallet support a dispute resolution mechanism?** While legal enforcement is a court of last resort, many governance frameworks may specify more progressive, efficient, and less expensive [dispute resolution](https://en.wikipedia.org/wiki/Dispute_resolution) mechanisms.
1. **Is the use of the wallet covered by one or more liability frameworks?** Another important accountability topic addressed by governance frameworks is liability, i.e., how damages are assessed, allocated, and paid when a party is found to be in violation of a governance framework. Note: because of their ability to automate verifiable transactions, digital wallets may also enable their holders to engage in a unique new form of automated [class action](https://en.wikipedia.org/wiki/Class_action). Holders that have suffered a specific harm could give consent via their digital wallets to: a) join the class action lawsuit, and b) automatically send the necessary evidence to the class action litigator. This could be a particularly powerful deterrent to bad actors.
1. **Does the wallet support a [reputation system](https://en.wikipedia.org/wiki/Reputation_system)? Does that reputation system cover the safety features of the wallet itself?** Reputation systems are user-generated accountability mechanisms that do not require trusted third parties (other than to design, implement, and prevent gaming of the reputation system).


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
