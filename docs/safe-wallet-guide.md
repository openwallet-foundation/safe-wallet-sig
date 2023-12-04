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

### Holder binding
Topics to include
- how to confirm the person who obtained a credential is the one presenting it

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
Topics to include:
- how well informed can the user be 
- how does the user "feel" safe
- consent - Refer to the legislative issue raised regarding consent.

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
