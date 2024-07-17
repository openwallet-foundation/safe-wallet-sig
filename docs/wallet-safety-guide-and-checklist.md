# Wallet Safety Guide and Checklist
OpenWallet Foundation Safe Wallet Special Interest Group (OWF-SW-SIG)<br/>
v1.1<br/>
16th July 2024<br/>
Copyright (c) 2024 OpenWallet Foundation.<br/>
<br/>
These materials are made available under and are subject to the Creative Commons Attribution 4.0 International license (http://creativecommons.org/licenses/by/4.0/legalcode).<br/>
<br/>
THESE MATERIALS ARE PROVIDED “AS IS.” The OpenWallet Foundation ("OWF") and its members and contributors (each of OWF, its members and contributors, a "OWF Party") expressly disclaim any warranties (express, implied, or otherwise), including implied warranties of merchantability, non-infringement, fitness for a particular purpose, or title, related to the materials. The entire risk as to implementing or otherwise using the materials is assumed by the implementer and user.<br/>
<br/>
IN NO EVENT WILL ANY OWF PARTY BE LIABLE TO ANY OTHER PARTY FOR LOST PROFITS OR ANY FORM OF INDIRECT, SPECIAL, INCIDENTAL, OR CONSEQUENTIAL DAMAGES OF ANY CHARACTER FROM ANY CAUSES OF ACTION OF ANY KIND WITH RESPECT TO THESE MATERIALS, ANY DELIVERABLE OR THE OWF GOVERNING AGREEMENT, WHETHER BASED ON BREACH OF CONTRACT, TORT (INCLUDING NEGLIGENCE), OR OTHERWISE, AND WHETHER OR NOT THE OTHER PARTY HAS BEEN ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

## Revision History

| Version | Date | Changes | Authors |
| ------- | -------------- | -------------------------- | --------------------- |
| v1.1   | 16th July 2024 | Add front-matter; reformat for Markdown | Sean Bohan <br/> Tracy Kuhrt |
| v1.0.2 | 10th July 2024 | Final editorial pass, add comments from Safe Wallet SIG | Juliana Cafik |
| v1.0.1 | 27th June 2024 | Full Edit for _tone_ consistency, reduce duplications, add additional detail and/or context, to align under 4 Pillars and add Executive Summary | Juliana Cafik |
| v1.0   | 18th June 2024 | Finalised.                 | Andy Tobin            |
| v0.961 | 28th May 2024  | Update checklist for Accountability section <br/> Updated footnotes <br/> Updated text in first sections | Drummond Reed <br/> Andy Tobin <br/> Daniel Bachenheimer |
| v0.96  | 7th May 2024   | Updated audience, scope, based on feedback and  <br/> test run exercises by Consult Hyperion, Innopay <br/> and Canadian participants | Juliana Cafik <br/> Andy Tobin <br/> Tim Bloomfield <br/> Dan Bachenheimer |
| v0.951 | 26th Mar 2024 | Added EU Digital identity Wallet example to the Holder <br/> Binding section | Dan Bachenheimer |
| v0.95 | 25th Mar 2024 | Updates following further reviews. | Andy Tobin <br/> Juliana Cafik <br/> Jorge Flores <br/> Keith Kowal |
| v0.91 | 25th Feb 2024 | Incorporated external feedback from Jamie Smith++. <br/> Multiple refinements and clarity edits. | Dan Bachenheimer <br/> Juliana Cafik <br/> Jamie Smith ++ <br/> Andy Tobin |
| v0.9 | 15th Feb 2024 | Incorporating feedback from OWF Government Advisory Council <br/> and external reviewers | Andy Tobin <br/> Sankarshan Mukhopadhyay |
| v0.8 | 6th Feb 2024 | Updates to Wallet/Device Lock/Unlock <br/> Updates to Security <br/> Updates to Accountability | Tim Bloomfield <br/> Juliana Cafik <br/> Drummond Reed       |
| v0.7 | 30th Jan 2024 | Updates to Holder Binding and Certification sections to change <br/> questions into requirements. | Andy Tobin |
| v.06 | 23rd Jan 2024| Updates to Security section <br/> Updates to Holder Binding section | Juliana Cafik <br/> Andy Tobin and Tim Bloomfield |
| v0.5 | 16 Jan 2024 | Multiple updates  | Daniel Bachenheimer <br/> Tracy Kuhrt <br/> Tim Bloomfield      |
| v0.4 | 9 Jan 2024  | Updates for consistency and flow. Acceptance of multiple <br/> prior changes. | Andy Tobin |
| v0.3 | 5 Dec 2023  | Updates for consistency and flow. Additions for clarity <br/> and new content. | Daniel Bachenheimer |
| v0.2 | Various     | Multiple updates and additions into each section. | Andy Tobin <br/> Juliana Cafik <br/> Sebastian Elfors <br/> Stavros Kounis <br/> Tracy Kuhrt <br/> Juan Francisco Tavira <br/> Lal Chandran <br/> Daniel Bachenheimer |
| v0.1 | 22 Sep 2023 | Initial framework        | Andy Tobin          |

##  Contents

- [Executive Summary](#executive-summary) 
- [Pillar 1: Privacy](#pillar-1-privacy)
- [Pillar 2: Security](#pillar-2-security)
- [Pillar 3: Supporting Functions](#pillar-3-supporting-functions)
- [Pillar 4: Governance](#pillar-4-governance)

## Executive Summary

Digital wallets are increasingly becoming integral to our digital lives, offering the promise of streamlined
transactions for individuals, businesses, and governments. However, their rapid evolution, reliance on
intricate cryptographic technologies, and the need to comply with dynamic regulations present
considerable challenges. As the adoption of digital wallets grows, so do concerns about their security and
the ability to maintain user privacy. It is crucial for users and Relying Parties to understand the safety
measures in place, for journalists to have access to accurate information on wallet features, and for
policymakers to grasp the technical subtleties to safeguard citizens.

Digital wallets, while empowering users to manage various digital assets and verify credentials, could
inadvertently introduce vulnerabilities if not implemented meticulously. These include potential security
gaps, surveillance risks, and the possibility of fraud or user profiling. The shift from secure, controlled
digital interactions to open, large-scale ecosystems—often without a single governing entity—further
complicates the oversight of these technologies.

The expertise required to master this complex landscape is limited, raising the risk that large-scale
deployments of digital wallets may unintentionally compromise trust within the ecosystem. This scenario
is reminiscent of the evolution of internet cookies, which morphed from simple session management
tools into sophisticated tracking and surveillance mechanisms. Therefore, it is imperative to approach the
development and deployment of digital wallets with a perspective that prioritizes security, privacy, and
user trust above all.

Addressing the highlighted concerns, the Open Wallet Foundation (OWF) Safe Wallet Special Interest
Group (SIG) has compiled the following high-level safety guidelines to aid wallet developers and product
managers. The document emphasizes four fundamental Pillars for Safe Wallets:

1. Privacy Pillar: Privacy by Design (PbD) is crucial for digital wallets, focusing on protecting user data
   from unwanted observation and tracking. The document outlines principles and mechanisms to
   ensure privacy, such as avoiding unique identifiers and decoupling issuers and verifiers

2. Security Pillar: Security by Design and Zero Trust principles are essential for digital wallets. The
   document details various security measures, including key management, credential management,
   and secure presentation protocols to prevent unauthorized access and ensure data integrity

3. Supporting Functions: Supporting functions for digital wallets include mechanisms for wallet and
   device locking/unlocking, user interface/user experience considerations, and holder binding. The
   document emphasizes the importance of these functions for ensuring security and usability

4. Governance Pillar: Governance involves regulatory compliance, certification, counterparty
   verification, and audit requirements. The document discusses the need for digital wallets to adhere to
   legal standards and provide mechanisms for accountability and transparency

## Pillar 1: Privacy

From a high level, the concept of Privacy and Privacy by Design (PbD) takes on a unique significance when
applied to digital wallets. Privacy in this context primarily pertains to the protection of a holder’s activities
from unwanted observation, tracking, and correlation.

Digital wallets and the digital credentials they manage, along with the complex cryptography and
protocols involved in their issuance, presentation (or exchange), and verification, introduce a new set of
challenges that don’t exist in the world of physical credentials. These challenges are integral to a wallet’s
functionality and need to be implemented with privacy considerations in mind.

The PbD approach in this context would involve:

1. Being proactive and preventive in protecting holder data, rather than reacting after a breach has
   occurred

2. Making privacy the default setting in the digital wallet, ensuring that holder data is protected by
   default

3. Embedding privacy into the design of the digital wallet, ensuring that all features and functionalities
   are built with privacy in mind

4. Ensuring full functionality of the digital wallet while maintaining privacy, aiming for a win-win
   outcome

5. Providing end-to-end security, protecting user data throughout its entire lifecycle

6. Maintaining visibility and transparency, keeping processes open, clear and understandable to holders

7. Respecting user privacy and keeping the holder at the center of the design, ensuring that their needs
   and concerns are addressed

By adhering to these principles, digital wallet providers can ensure they are meeting their legal and
regulatory responsibilities, reduce (minimize) data breaches, and foster trust with all stakeholders. This
approach ensures that privacy is not an afterthought, but a fundamental aspect of the design and
operation of digital wallets. Elements for consideration include:

1. Unique Identifiers:

    1. Unique identifiers specific to the holder or wallet, which may be shared without the holder’s
       consent during each transaction, should be avoided. These can be considered as follows:

        1. Akin to a tracking beacon that allows colluding entities to correlate all activities of a
           holder using that wallet

        1. Dangerous when proxy verification services that process verifications for many relying
           parties can see and track identifiers and profile the behaviors of all holders

        1. A wallet serial number in the “metadata” of the credential exchange transaction

        1. The exposure of IP addresses used in digital interchanges should be factored into the
           overall operational risk profile

    1. Credential-specific unique identifiers that are shared, without user choice, are another class of
       unique identifiers that should be avoided and include:

        1. Identifiers specific to a credential, which a holder inevitably shares, can lead to
           transaction correlation each time that credential is used. Although this doesn’t impact
           privacy as much as a holder or wallet-specific identifier, it’s still a concern because it isn’t
           necessarily shared with every transaction. Examples of credential-specific identifiers are:

            - Revocation index position or an issuer signature in the “metadata” of the
              credential exchange transaction

            - Payment credentials which may contain unique identifiers for compliance
              within the financial services industry

1. Decoupling issuers and verifiers are a fundamental aspect of implementing privacy and aligning with
   the principles of Privacy by Design. It aids in safeguarding user data, preventing unwanted tracking,
   and enhancing user autonomy and trust. The importance of separating the roles of issuers and
   verifiers in the context of digital wallets is multi-fold:

    1. Reduced Data Exposure: If issuers and verifiers are distinct, the personal data revealed during
       transactions can be kept to a minimum. The party verifying the credential doesn’t need to know
       its issuer, and vice versa

    1. Avoiding Correlation: Keeping issuers and verifiers separate helps avoid the correlation of
       transactions. If a single entity were to issue and verify a credential, it could potentially track its
       usage, compromising the user’s privacy

    1. Increased User Autonomy: Users have more control over their data when issuers and verifiers are
       not the same. They can choose to share their credentials without the issuers knowing where and
       when those credentials are being used

    1. Trust Building: Trust among users is fostered when issuers and verifiers are decoupled, as users
       can be confident that no single entity has access to all their transaction data. This can lead to a
       broader acceptance of digital wallets

    1. Issuers and verifiers of digital credentials should not be able to track their use which would
       enable them to, for example, build user profiles. However, transactions where usage tracking is a
       fundamental part of the use case that holders are fully aware of (payments being an example)
       would be accepted in that context

    1. Issuers should not be able to aggregate holder information
    
    1. Preventing verifiers from contacting issuers (a process known as decoupling) for any reason,
       including to verify the revocation status of digital credentials, is crucial. Without this decoupling,
       issuers could potentially monitor the usage of digital credentials. This could happen through
       hidden interactions between issuers and verifiers that occur without the knowledge or consent of
       the credential holders. This issue, often referred to as the “phone home” problem, should be
       avoided

    1. Issuers and Verifiers should not be able to access a digital wallet without explicit holder Notice and
       Consent

1. Support for Privacy-Enhancing Credential Sharing Mechanisms in Wallets. The wallet should
   incorporate mechanisms that preserve privacy, and ensure that only a specific subset of data
   attributes within a credential are disclosed. An example could be sharing only the first name and
   photo from a driver’s license, rather than all the information on the license. Additionally, these
   mechanisms should allow for the verification of data possession without exposing the actual data
   values. An example of this could be verifying if a user is over 18 without revealing their exact date of
   birth. This can be achieved using techniques such as selective disclosure, calculated or predetermined
   predicate proofs and zero-knowledge proofs.

1. Privacy of Wallet Transactions should be preserved and the entities that provide the code and/or
   operate the cloud services for digital wallets should not have the ability to monitor or track the
   transactions carried out by the wallet holders. This is especially crucial for:

    1. Code providers and contributors and/or cloud operators of digital wallets must not be able to
       observe or track transactions undertaken by holders

    1. This is particularly important in the case of hybrid and cloud wallets, where transactions are
       performed on the wallet operator’s infrastructure

    1. Wallet code providers and cloud operators must not be able to access the contents of digital
       wallet transactions log files or backups

    1. Wallet code providers and cloud operators must not have a “master key” or “back-door” that
       enables them to access the contents of wallets

1. Digital Wallet ecosystem providers or organizations that provide the infrastructure to which digital
   wallets connect to issue or verify credentials (typically called credential exchange platforms) must not
   be able to examine the contents, source or destination of wallet transactions. Specific considerations
   are:

    1. In situations, such credential exchange platforms will need to “translate” from an encrypted
credential envelope to/from clear text for integration with other systems, such as customer
onboarding systems. In this case, the credential exchange platform must manage the data in such
a way that it is encrypted, transient and not stored, observable, or trackable to protect wallet
holder privacy.

    1. Proxy services may provide credential issuance/verification services for many issuers and
verifiers. In doing so, they could observe and correlate wallet transactions across large
ecosystems and should:

        1. Not observe, store and correlate wallet transactions

        1. Provide clear Notice and Consent that they are dealing with a proxy service rather than
           the true end issuer/verifier

1. Wallet Consent management is a key component of privacy by design, ensuring that privacy is not an
   afterthought, but a fundamental aspect of the design and operation of digital wallets. It helps to
   protect user data, prevent unwanted tracking, and enhance user control and trust and is critical to
   privacy for several reasons:

    1. User Control: Consent management gives users control over their own data. Users decide what
       information they want to share, with whom, and for what purpose. This empowers users and
       respects their privacy

    1. Minimizing Data Exposure: With consent management, users can choose to share only the
       necessary information, minimizing the exposure of their personal data. This is particularly
       important in the context of digital wallets where sensitive information is involved.

    1. Trust and Transparency: Consent management promotes trust as users know their data is being
       used responsibly. It also ensures transparency as users are aware of how their data is being used

    1. Regulatory Compliance: Many regions have data protection regulations that require user consent
       before personal data can be processed. Consent management helps digital wallets comply with
       these regulations, avoiding legal issues and potential fines

    1. Preventing Misuse of Data: By giving users the ability to manage consent, it reduces the risk of
       data misuse. Holders can withdraw consent if they believe their data is not being used
       appropriately

    1. Provide clear, understandable, and easy-to-use mechanisms for the user to provide consent to
       add data or read data from their wallet. This is a major privacy consideration and ensures the
       user is in control of their data.

    1. Record of Notice and Consent: Holders must be able to track the Notices provided and consents
       given and should be able to withdraw that consent at any time

    1. Enable Wallet privacy preserving supporting functions: The act of providing consent by the holder
       should not compromise privacy

## Pillar 2: Security

At its most basic, a digital wallet is a holder-controlled digital container sitting between Issuers of
verifiable credentials and a Verifier and/or Relying Party that authorizes access to, and the provisioning
of, services. It is also a critical confluence point in credential-based interactions and must be able to
establish, maintain and attest to the trusted processes required for a private, trustworthy, secure, and
safe digital transaction to safeguard against harm.

According to the European Union[^1], a compliant EU digital wallet _will provide a secure and convenient way
for European citizens and business to **share identity data** needed for accessing digital services such
as checking in at the airport, renting a car, opening a bank account, or logging in to their accounts on
large online platforms._

Digital wallets are instrumental to the acquisition, storage and presentation of credential-based
assertions, and the security of wallets is essential to safeguarding the integrity and privacy of those
assertions. Wallet architects and developers should consider Security by Design, Security by Default and
Zero Trust security best practices with a focus of least privilege for wallet applications and supporting
functions. Wallet components should correspondingly be based on robust security controls capable of
providing evidence to the context, methodology, and strength of the controls as well as confirm their
authenticity and state while in use. Wallet security controls should also mitigate risks from evolving attack
surfaces and vectors on consumer devices, to detect potential vulnerabilities such as (but not limited to)
unauthorized access, phishing attacks, man-in-the-middle, replay and relay attacks, malware and elevated
privilege, data breaches, social engineering attacks and credential theft. These unauthorized activities
can lead to monetary loss or identity theft for the holder and risk to Relying Parties. Given that digital
wallets may store sensitive identity and financial information, they are appealing targets for
cybercriminals. Therefore, it is crucial for digital wallet developers and providers to take necessary
precautions to secure digital assets and their exchange for wallet holders.

The Digital Identity and Authentication Council of Canada’s (DIACC's) Digital Wallet Component
Conformance Criteria states: "The integrity of a Trusted Process is paramount because many Participants
may rely on the output of the process, often across jurisdictional, organizational, and sectoral
boundaries". DIACC's Digital Wallet Conformance Profile[^2] also includes a comprehensive breakout
detailing the Type of Risk, Threat Category, Impact and Proposed Mitigation, which is a good example of
how to assess digital wallet conformance to these critical design elements.

Expanding on the foundational work that DIACC has done, this document describes Trusted Processes and
Security Design Controls and Considerations that may be necessary to provide safety for wallet holders as
well as meet the required levels of assurance for regulatory compliance, issuers, verifiers and relying
parties as well as ultimately providing the building blocks for establishing an awareness of state via
attestation that can be relied upon.

### Trusted Processes

1. Wallet Selection: Wallet selection refers to the process of the holder or device operating system
   choosing a digital wallet for a specific purpose while ensuring optimal security and safety. In a
   situation where multiple wallets are available, a wallet selector is an additional step in the wallet user
   flow when sending or receiving transactions, to prompt a provider to choose the specific digital wallet
   they wish to use. The goal is to select a wallet that not only provides the appropriate functionality but
   also ensures safety and security for all interactions on an ongoing basis. This is fundamental to the
   establishment of trust, the assurance of privacy and the efficacy necessary to create a positive and
   adoptable wallet-holder experience. Wallet selection can pose several security risks and
   considerations for prevention include (but are not limited to):

    1. Malware:

        1. Regular Software Updates: Continually update wallet software, operating systems,
           internet browsers, phone firmware, and antivirus software to fix known vulnerabilities as
           they are discovered

        1. Secure connections and end-point management for all network interactions, including
           NFC and Bluetooth low-energy enabled hardware

        1. Phishing resistant authentication

        1. Obtain wallet software from official sources

        1. Root detection for mobile devices

    1. Social Engineering prevention involves a combination of technical measures, policy enforcement
       and wallet holder education. Strategies for mitigation include:

        1. User Education: Users should be educated about the common tactics used in social
           engineering attacks and how to identify potential scams

        1. Phishing resistant authentication

        1. End-point security

        1. Regular audits of accounts and access levels

        1. Software updates to prevent evolving known vulnerabilities

        1. Policy enforcement for policies and procedures that consider potential social engineering
           vectors and provide specific guidance on steps to take to avoid successful attacks

        1. Brute Force Attack Mitigation options:

            1. Phishing resistant authentication

            1. Account lockouts and rate limiting

            1. Strong data encryption and storage

        1. End-point authentication to prevent Man-in-the-Middle Attacks such as:

            1. Relay Attacks: Relaying information between parties

            1. Replay Attacks: Capturing and reusing information

1. Key Management and Generation: the security of a cryptographic system heavily relies on the secure
   generation, storage, and management of its keys and is an essential function involving the handling
   and safeguarding of cryptographic keys to ensure the security and integrity of the holder's digital
   assets and it is essential that the design be reviewed by multiple cryptographers. Primary security
   considerations and controls for key management and key generation are a vital part of a wallet’s
   cryptographic systems and require considerable care to ensure security such as:

    1. Random Number Generator Quality: It is important to use a high-quality random number
       generator for key generation. This helps to avoid predictability and strengthens the security of
       the cryptographic system

    1. Encryption Algorithms and Key Size Selection: The choice of encryption algorithms and key size
       should be based on the security requirements of the application and the most secure
       combination should be selected

    1. Safe Key Storage: Keys should be stored securely using hardware security modules, smart cards,
       and/or trusted platform modules. This secure storage helps to prevent unauthorized access to
       the keys

    1. Key Rotation and Decommissioning: Keys should be renewed periodically, and old keys should be
       decommissioned. Regular renewal of keys reduces the risk of key compromise over time

    1. Preventing Key Compromise: The secure management of cryptographic keys is of utmost
       importance, as the security and reliability of cryptographic processes depend on the strength of
       the keys, the effectiveness of the protocols associated with the keys, and the protection given to
       the keys

    1. Adherence to Standards: Established standards and recommendations for key management
       should be followed, such as those provided by recognized standards organizations or as
       mandated by regulations or necessary to meet risk management requirements

    1. Backup and Recovery: A robust key recovery system, or process, is critical to ensure users can
       regain access to their wallet(s)if the private keys are lost or compromised

    1. Usage: Keys should be protected while in use, and at rest, in a secure manner and within a secure
       environment

    1. Key Revocation: Processes for revoking and replacing compromised keys

    1. Audit: Processes for logging, detecting and providing notice of security risks to keys

    1. Private Key Management to prevent exposure during the rendering of transaction processes

1. Credential Signature / Format: A credential signature in the context of a digital wallet is a digital proof
   that verifies the authenticity of the credential. For a secure credential signature, it is important for
   the wallet to support:

    1. Credential Signature Verification: mechanisms to verify the authenticity of the credential
       signatures to ensure they have not been tampered with and are issued by a legitimate trusted
       authority

    1. Secure Storage of Credentials: Secure storage to prevent unauthorized access and tampering
       with verified signatures

    1. Privacy Preservation: Mechanisms to support the verification of credentials without revealing
       unnecessary personal information, such as selective disclosure and zero-knowledge proofs

1. Credential Management: Credential management in the context of a digital wallet refers to the
   process of handling and safeguarding digital credentials to ensure their integrity. Security
   considerations are:

    1. Storage: Credentials must be stored securely to prevent unauthorized access.

    1. Backup and Recovery: A robust recovery system, or process, to ensure holders are able to regain
       access to their wallet(s)

    1. Usage: Digital wallet architecture must support credential use in a secure manner and within a
       secure environment

    1. Revocation: The process of revoking and replacing compromised credentials is a crucial aspect of
       maintaining the integrity and security of the wallet and the credentials it holds. Processes will
       vary by issuer, wallet, and framework and will need to ensure:

        1. Adherence to privacy regulations and principles

        1. Revocation checks cannot be linked by issuers and third parties

        1. Prevent holder traceability

    1. Audit: Auditing processes are crucial for maintaining the security of a digital wallet. They involve
       logging and detecting potential security risks to the credentials stored in the wallet. These
       processes aim to safeguard the integrity, privacy, and availability of the wallet, its trusted
       processes, supporting functions, and credentials. Regular audits can help identify vulnerabilities
       or breaches and take appropriate action to mitigate risks. It is an essential part of maintaining a
       secure digital wallet environment

1. Presentation Protocols: Presentation protocols in the context of a digital wallet refer to the
   standardized methods for presenting, sharing and verifying digital credentials. The protocols ensure
   interoperability and secure communication between different entities in the digital ecosystem,
   include standards-based credential presentation and verification and are crucial to the security and
   privacy of a holder's digital identity. To preserve the integrity of presentation protocols several wallet
   security measures should be implemented:

    1. Phishing-resistant user authentication to ensure the holder presenting the credentials is the
       legitimate holder of both the wallet and the credential

    1. Secure, Phishing and ‘spoof’ resistant user interface

    1. Strong data encryption and storage to secure credentials and prevent unauthorized access

    1. Digital wallet rendering and user interface to ensure that holders are interacting with intended
       functions to support credential presentation and usage in a secure manner

    1. Privacy-preserving mechanisms to support the presentation of credentials without revealing
       unnecessary personal information, such as selective disclosure and/or zero-knowledge proofs

    1. Audit processes for logging and detecting security risks, such as malware, phishing attacks, man-
       in-the-middle attacks, etc., that may impact credential presentation.

1. Mechanisms to convey consent: User Consent is a critical aspect of privacy and security in digital
   wallets. It provides credential holders with control over wallet interactions and the sharing of specific
   information, such as credentials with a service provider. To support secure holder-consent, the
   following mechanisms should be implemented:

    1. Phishing-resistant user authentication to ensure the holder providing consent is the legitimate
       holder of both the wallet and the credential

    1. Phishing and ‘spoof’ resistant user interface

    1. Strong data encryption and storage to secure sensitive data and consent records and prevent
       unauthorized access

    1. Revocation mechanisms to provide holders with the option to revoke consent such as a protocol
       for sending the revocation to the relying party, and a regulatory framework for requiring the
       relying party to act upon such revocation.

### Security Design Controls and Considerations

Security by design is the process of implementing Secure by Design strategies throughout the software
development lifecycle to enhance security outcomes. Considerations should be given to every component
of the wallet, including design, and end-to-end scenarios, and are essential to conducting detailed and
diverse threat modelling. These approaches aim to improve security by incorporating security
considerations throughout the software development life cycle. In the context of open-source digital
wallets, these strategies are essential for advancing collective security. Implementing the following secure
by design principles during the design phase of product development can reduce the number of
vulnerabilities that can be exploited by adversaries:

1. Zero Trust: A security model that operates on the principle of “never trust, always verify.” In the
   context of a digital wallet, this means that every transaction or access request is treated as potentially
   hostile, regardless of whether it originates from inside or outside the network. Zero Trust means the
   security posture for all users and devices defaults to untrusted, then layers of access are added based
   on the identity and context of the user or device, following the principle of least privilege. This makes
   it a highly effective strategy for securing digital wallets and other sensitive digital assets

1. Open Design: A concept that involves the development of products, machines, and systems using
   publicly shared design information including Open-Source Software. Specific security considerations
   for Open Design include:

    1. Security should be integrated from the start of the design process. This approach, known as
       Security by Design, aims to incorporate security considerations into the very foundations of a
       system

    1. The principle of open design states that security systems should not rely on secret designs or
       security by obscurity. Instead, they should invite and encourage open review and analysis.
       There should be sufficient security controls in place to keep applications safe without hiding
       core functionality or source code

    1. Security should be viewed holistically and, wherever possible, multiple levels of security
       controls should be used. This involves implementing a set of overlapping protections to
       reduce the risk using end-to-end controls

    1. Limiting the amount of code and functionality exposed to potential attackers. The less code,
       the fewer vulnerabilities there are likely to be

1. Attack Surface Minimization: A security strategy that aims to reduce the number of potential
   vulnerabilities in a wallet by limiting the ways in which it can be attacked. This can be achieved by
   reducing the number of entry, end points and APIs and by limiting the functionality and access of the
   wallet to only what is necessary for its intended purpose. By minimizing the attack surface, the wallet
   becomes more difficult to compromise, as there are fewer ways for an attacker to gain access or
   exploit vulnerabilities

1. Defense in depth: A security strategy that employs multiple layers of protection to slow down or
   prevent an attack from gaining unauthorized access to information. Each layer provides protection so
   that if one layer is breached, a subsequent layer is already in place to prevent further exposure.

1. Least privilege: A security concept that requires each user, system, or process related to the wallet to
   have a minimum level of access necessary to perform its function. This means that users, systems, or
   processes should only have access to the resources and information related to the wallet that they
   need to do their job, and nothing more. This approach helps to reduce the risk of unauthorized access
   or malicious actions, as it limits the potential damage that can be caused if a user, system, or process
   is compromised

1. Need to know: A security concept that states that access to information should be restricted to
   individuals who require that information to perform a specific task or function. This means restricting
   access to the information that is necessary for them to complete a task, and no more. This principle is
   closely related to the principle of least privilege. By following the need-to-know principle, wallet
   developers can reduce the risk of unauthorized access or disclosure of sensitive information

1. Role Based Access Controls (RBAC): A method of regulating access to resources based on the roles of
   individual users. In RBAC, permissions are assigned to roles, and users are assigned to roles. This
   allows for access to be restricted based on function, such as wallet Holder, Software Developer,
   Quality Assurance (QA), Project Managers, Security Analysts, and System Administrators, with roles
   being broad for general access or fine-grained to restrict specific capabilities

1. Separation of Duties: A security principle that shifts the burden of security as much as possible away
   from the end-user, or holder in the context of a wallet, to the wallet developer(s). This principle is
   based on the idea that no single individual should have complete control over a critical process or
   system, and that by distributing responsibilities and privileges, the potential for abuse or misuse is
   reduced. Separation of duties is often implemented through role-based access controls (RBAC)

1. Secure by Default: A principle aimed at shifting the burden of security as much as possible away from
   the holder back to the wallet developer(s). It is about designing wallets that require minimal
   hardening and are secure when deployed. In the context of digital wallets this is much harder to do
   than secure by design, as each wallet holder’s environment is different. What works well for one
   wallet architecture might not work for another. It is also important to consider that secure by default
   features go through rigorous testing and periods of customer feedback to ensure benefit to the
   largest number of end users possible.

1. Security Controls: such as [NIST 800-53](https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final)
   and [PCI DSS](https://www.pcisecuritystandards.org/standards/pci-dss/) are safeguards, or countermeasures, prescribed to
   meet a set of defined security requirements Controls are designed to address specific needs as
   specified by a set of security requirements and aid in protecting organizational operations and assets,
   the integrity of systems that support the wallet, the storage of sensitive data and authentication data,
   involve flaw remediation, malicious code protection, system monitoring and software integrity. They
   include security controls that focus on protection from a diverse set of threats, human error, the
   management of risk and information system security and are integral to the overall security posture
   of a digital wallet and supporting systems and organizations

1. Software Bill of Materials (SBOM): An SBOM is a key building block in software security and software
   supply chain risk management. It provides transparency into all constituent parts of the software,
   which is crucial for understanding exactly what has gone into the software that is being distributed
   and used for the wallet. The specifics of what is included in an SBOM can vary depending on the
   software in question and can provide a multitude of security advantages such as:

    1. Handling Vulnerabilities: SBOMs allow organizations to keep track of third-party components
       accurately. This enables developers to evaluate associated risks, such as open-source libraries,
       both before and after their incorporation. They can systematically cross-check the inventory
       against databases of known vulnerabilities

    1. Enhanced Visibility and Transparency: SBOMs improve visibility in the software supply chain. They
       generate and verify information about code provenance and relationships between components,
       which assists software engineering teams in detecting malicious attacks during development and
       deployment

    1. Incident Response and Forensics: In case of a security incident, an SBOM can assist cybersecurity
       teams in identifying and addressing vulnerabilities. Organizations with SBOMs have been able to
       reduce response times due to their ability to map applications to vulnerable dependencies

    1. Regulatory Compliance: Many governments and regulatory organizations now require the use of
       SBOMs as a standard. By understanding the source and licensing of each component, an
       organization can ensure that the use of these components complies with legal requirements and
       licensing terms

    1. Efficiency: The common infrastructure and data exchange format of SBOMs could save
       companies time by fostering greater collaboration between organizations

1. Software Development Best Practices, Software Assurance Models and Standards: should be
   considered to improve software security postures for the design, development and deployment of
   secure software for digital wallets and include [NIST 800-218](https://csrc.nist.gov/pubs/sp/800/218/final),
   [OWASP SAMM](https://owaspsamm.org/about/),
   [PCI Secure Software Standard](https://www.pcisecuritystandards.org/standards/secure-software/)
   and [PCI Secure Software Lifecycle (Secure SLC)](https://www.pcisecuritystandards.org/standards/secure-software-lifecycle-secure-slc/).
   Adopting software development best
   practices and assurance models along with standards can offer numerous advantages for digital
   wallets such as:

    1. Quality Assurance: Compliance with best practices and standards ensures the software’s
       quality, leading to a more reliable and robust digital wallet

    1. Security: Best practices often encompass security measures such as encryption, secure APIs,
       and regular updates, which help safeguard user data and transactions

    1. Scalability: Adhering to best practices allows for scalability, ensuring that the digital wallet
       can accommodate growth in the user base and transaction volume

    1. Interoperability: Standards ensure interoperability, enabling the digital wallet to interact
       seamlessly with various systems and technologies

    1. Regulatory Compliance: Compliance with standards can assist in meeting regulatory
       requirements, reducing legal risks

    1. Trust: Following recognized standards, and best practices can enhance trust among users and
       partners

    1. Risk Management: Assurance models aid in identifying and managing risks, contributing to
       the overall security and reliability of the digital wallet

    1. Validation: They offer a framework for validating that the digital wallet meets specified
       requirements and standards

    1. Continuous Improvement: Assurance models support continuous improvement by providing
       benchmarks and metrics for evaluating performance

    1. Stakeholder Confidence: Demonstrating that the digital wallet has been thoroughly evaluated
       and meets recognized standards, assurance models can increase confidence among
       stakeholders

## Pillar 3: Supporting Functions

Supporting functions for digital wallets are mechanisms specific to a digital wallet that enable, or support, 
external party processes and the functions, features and capabilities required to support specific use-cases, applicable standards requirements, trust frameworks and regulatory requirements.

1. Wallet and Device Locking and Unlocking Mechanisms: A safe digital wallet will provide a secure and
   user-friendly means through which an authorized holder may unlock and lock it to minimize
   fraudulent use. While these lock/unlock mechanisms, typically driven by the wallet provider, are
   detailed here separately and apart from holder authentication, although they may utilize similar
   processes, functions, and technologies. In situations where the wallet is used in proximity, it should
   be capable of displaying information without the need for the device to be unlocked as this could
   potentially expose sensitive data outside the context of the verifiers request. Coincidentally holder-
   notice should be provided prior to device unlocking and holder-consent based sharing of information.
   It is crucial in this scenario to authenticate the reader to prevent unauthorized data extraction by
   potential malicious actors nearby. This feature safeguards privacy and upholds the principle of data
   minimization.

   The requirements for unlocking mechanisms should incorporate considerations for accessibility and
   usability, both functionally and non-functionally, while also considering the associated risks. If a
   control mechanism is not user-friendly or accessible, it could lead to the use of less secure methods
   and/or exclude certain segments of the population from using the wallet, impacting its adoption.
   The lock/unlock mechanisms of a wallet protect it from unauthorized access, which include viewing,
   adding, updating, sharing, and deleting wallet contents, and are based on the design requirements of
   the wallet. Meanwhile, relying parties determine the Identity, Authentication, and Assurance Levels
   they require for access to their services, based on their distinct regulatory, framework and risk
   management policies and requirements.

   Once unlocked the digital wallet must include additional controls to protect the privacy of holder data
   and maintain the appropriate level of security of the wallet. The following is a minimal list of controls
   specific to wallet lock and unlock:

    1. The wallet locks if focus is lost

    1. The wallet locks after a pre-defined period of inactivity

    1. On mobile devices, application thumbnails (displayed during app switching or selection) are blank
       or otherwise rendered unreadable to protect sensitive information

    1. If implemented, the wallet must properly secure the PIN/Password and must not persist the
       PIN/Password in memory after an authentication event

1. Authentication: Authentication and device locking/unlocking in the context of digital wallets are
   closely related as the same methods used to authenticate to access the wallet may be used to lock
   and unlock it. As we transition into the topic of authentication, it's important to understand that
   these two concepts—locking/unlocking and authentication—are closely intertwined in the context of
   digital wallet security and the mechanisms and methods described below may apply to both.
   Authentication refers to the process of verifying the identity of a user before granting access to the
   wallet. This process is crucial for ensuring its security and protecting it from unauthorized access. For
   specific requirements and guidance for authentication we reference [NIST SP 800-63-4 B (draft)](https://pages.nist.gov/800-63-4/sp800-63b.html)
   but highlight the following for context:

    1. The mechanisms and controls to lock and unlock and authenticate to a wallet are defined by
       wallet developers. Wallet authentication mechanisms may vary in level of assurance and
       implementation and include, but are not limited to:

        1. PIN or password requirements: A PIN or password should implement complex rules to
           minimize the chance of it being guessed. These rules could include minimum length
           requirements, restrictions against patterns or dictionary words and rate limiting and are
           specifically detailed

        1. Multi-Factor Authentication (MFA), as defined by NIST SP 800-63-4 B (draft), is an
           authentication system that requires more than one distinct authentication factor. It can be
           performed using a multi-factor authenticator or by a combination of authenticators that
           provide distinct factors. Authentication factors include:

            - Something you know (e.g., a password)

            - Something you have (e.g., a hardware token or phone)

            - Something you are (e.g., biometric data like a fingerprint or face scan)
              
           An example of a multi-factor authenticator could be a cryptographic authentication device
           with an integrated biometric sensor that is required to activate the device
        1. Phishing-resistant authentication is a method to prevent attackers from gaining access to
           sensitive information through deceptive practices. Phishing-resistant authenticators are
           defined by their ability to detect and prevent the disclosure of authentication secrets and
           valid authenticator outputs to an impostor relying party without relying on the vigilance of
           the wallet holder and often implement asymmetric cryptography as a core security control.
           Examples include:
            - FIDO2 WebAuthn standard
            - PIV smart cards
            - PKI-encrypted smart cards
            - Biometric authentication
            - FIDO Passkeys
        1. Step-up authentication is a security measure that is distinct from multi-factor authentication
           as it requires wallet holders to provide additional proof of their identity when they attempt to
           access sensitive resources or when performing high-risk actions

1. Holder Binding: Digital wallets are applications used to receive, store, and share attributes in a secure,
   privacy enhancing fashion. To prove that the legitimate, natural person is receiving, in possession of,
   or sharing these attributes requires a means to bind the wallet and the credentials it manages to the
   natural person.

   In 1995, for example, the International Civil Aviation Organization (ICAO) clearly recognized the
   desirability of pursuing the use of biometrics in travel documents as the single best way to link the
   document and its rightful “owner.”[^3] In this example, the issuing authority binds the identity
   attributes to the authorized holder during the issuance process by including biometric data in the
   cryptographically signed logical data structure. When the holder makes an identity claim, the Relying
   Party (verifier) can determine the authenticity and integrity of the identity attributes and, through
   biometric recognition, determine if the authorized holder is presenting the information during the
   verification process. This works well for the intended use case: in-person identity verification by
   government authorities for cross-border travel.

   From a safe wallet perspective, holder binding can be split into sub-categories relating to the points in
   the chain of custody of the wallet and the credentials it contains. It should be noted that the chain of
   custody differs depending on whether the wallet will perform holder authentication during a
   transaction with a relying party, or whether the relying party will perform holder authentication (e.g.
   by comparing the portrait image from the authenticated credential to the presenter of the
   credential).

    1. Holder binding to the device and wallet:

        1. The wallet should have a mechanism to associate, and differentiate, one or more natural
           persons to the device as part of the wallet provisioning and setup process

        1. Where biometric binding is used, the wallet should have a mechanism to store, and share,
           associated metadata such as: signature of authority providing the biometric data, live capture
           by authority indicator, quality assessment method and result, presentation attack detection
           (PAD) method and result, morph attack detection (MAD) method and result

        1. The wallet should have a mechanism to store, and share, the associated assurance level of
           the issuance process (e.g., reflective of in-person, remote supervised, remote; uniqueness
           determination)

        1. The wallet should take any action if a previously set up device security (e.g. a fingerprint) is
           changed (e.g. the addition of a new fingerprint which could come from another person)

        1. The wallet may have its own person binding method in addition to the one implemented by
           the device’s operating system

    1. Holder binding to their credentials at issuance:

        1. The wallet should provide a mechanism whereby the issuer is able to confirm that the person
they are issuing the credential to is the correct person.

        1. The issuer may be able to insert into the credential (as an attribute or metadata)
confirmation that such a check has been performed, and how it was performed, such that a
relying party can confirm what checks the issuer carried out

    1. Holder binding to their keys (see Key Management in the Security section):

        1. The wallet must have a mechanism to bind the private keys within the wallet that are used
           for proving possession, for signing, etc., to each holder. For example:

             - Device keys are bound to the device

             - A holder is bound to the device keys via the device OS

             - A holder is bound to an identity credential via the biometric contained in the identity
credential

             - The identity credential is bound to the device via the device keys included in the
               identity credential (and signed by the issuer)

             - A relying party will need a mechanism to determine the level of confidence it can
               place in each of these bindings

        1. This mechanism should operate within a secure enclave or trusted execution environment.

    1. Holder binding at the point of presentation:

        1. The wallet should have a mechanism to check that the person releasing a presentation
           (“proof”) to a relying party is the same person to whom the credential was issued

        1. The wallet may be able to inform the relying party what mechanism it used to perform such a
           check and provide evidence of the success of the check

        1. The wallet should support multiple methods for executing holder binding at the point of
           presentation e.g. PIN entry, biometrics

        1. The wallet should have the ability to configure the holder binding checking it does in
           response to a trigger in the relying party’s proof request, i.e. the relying party can request a
           high assurance binding check for a high value transaction, or a low assurance check (with less
           friction) for a low assurance transaction

1. Additional information regarding biometrics in holder binding: In each of the Holder binding sub-
   categories where biometrics are used as part of the binding process, the additional factors described
   in this section should be considered.

   All biometric systems are probabilistic and will produce Type I (false non-match) and Type II (false
   match) errors which must be factored into the target use case. These error rates are influenced by
   factors such as quality, which is impacted by factors such as the equipment used to capture the
   biometric data, the resolution, lighting conditions, pose angles, environment, and demographic
   differentials.

   Relying on a third-party biometric recognition algorithm operating on a personal device to compare a
   selfie captured in real-time against the selfie captured during registration may be sufficient for some
   use cases - but not for others. Edge authentication, where the native or a 3rd party biometric sensor
   and/or matcher is used, is inherently lower assurance than in-person authentication where the
   relying party’s biometric sensor and matcher are used and where the relying party can determine
   quality and match thresholds.

   The EU Digital Identity Wallet legislation, for example, calls for Level of Assurance HIGH for User
   Authentication which necessitates the use of two of three factors where one factor can be inherence.
   This is where, “the applicant is identified as the claimed identity through comparison of one or more
   physical characteristic of the person with an authoritative source;” and “‘authoritative source’ means
   any source irrespective of its form that can be relied upon to provide accurate data, information
   and/or evidence that can be used to prove identity;”

   An ‘authoritative source’ for high-risk use cases requires biometric data to be captured live by a
   trusted entity, evaluated to be of sufficient quality for automated recognition, and determined to be
   unique within the target population to an acceptable False Positive Identification Rate (FPIR) at a
   specified False Negative Identification Rate (FNIR). This is typically performed by a government
   agency where, per NIST SP 800-63A and others, the “Expected Outcomes of Identity Proofing” is to
   “Resolve a claimed identity to a single, unique identity within the context of the population of users
   the CSP serves.”4 Comparing a physical attribute of a natural person to one encoded on, or in, a
   government issued credential is NOT identity proofing, it is identity verification.

   For identity resolution (aka, deduplication) we are more concerned with the false negatives (the
   misses) versus the false positives (the erroneous matches) which may be adjudicated manually. This is
   especially relevant in the Holder Binding to the wallet. For the highest assurance levels, for example,
   we expect that the authoritative source for biometric data is captured live by a trusted entity and
   determined to be of sufficient quality for automated recognition.
   
## Pillar 4: Governance

Digital wallets are technical and standards-based implementations to solve regulatory, compliance and
risk-based challenges. Wallets sit at the confluence between Counterparties who engage in transactions
and Relying Parties who depend on digital identity information from trusted sources to provide services
and may be subject to multiple requirements from both for:

1. Regulatory Compliance: For widespread adoption of digital wallets, there must be guardrails in place
   where both public- and private-sector implementers can turn to understand conformance - and for
   the public to derive trust.

   There is a balance to be struck between the enforcement of legislative rules through technological
   means versus through a court of law. For example, it may be decided that it is too technically complex
   to implement some legislation rules into a digital wallet, so the designers may elect to rely on the rule
   of law as implemented by a court instead. This would mean that technology does not restrict
   something from happening in the wallet, and instead, the rules are enforced through heavy fines or
   prison time for the transgressors. An example of this in the automobile industry is that enforcement
   of speed limits in cars is done by the police and the courts, not by the technology in the car (at least
   not yet). Some of the identified legislative issues related to wallet-based data exchanges are
   summarized below:

    1. Legislation that organizations need to adhere to while processing data. E.g., Article 30 of the
       GDPR places an obligation on controllers and processors (organizations, issuers/verifiers) to have
       in place within their organizations a detailed record of activities the organization conducts which
       use personal data

    1. Legislation that ensures the digital rights of the individuals are considered. The GDPR has a
       chapter on the rights of data subjects (individuals) which includes the right of access, the right to
       rectification, the right to erasure, the right to restrict processing, the right to data portability,
       the right to object and the right not to be subject to a decision based solely on automated
       processing. For example, Article 7 (1) of GDPR states that in situations where the processing of
       data is based on consent, the controller shall be able to demonstrate that the data subject has
       consented to the processing of his or her personal data

1. Certification: Certification in the context of digital wallets relates to the formal evaluation of products
   according to standards such as Common Criteria. It is closely associated with the Legislation
   Compliance topic since digital wallet regulations in some cases include specific certification
   requirements. This guide does not intend to list all applicable certification criteria for all use cases in
   all jurisdictions. Instead, it provides a list of questions that a wallet designer should be able to answer
   relating to the certification compliance of their wallet for its intended usage scenarios including:

    1. Compliance with regulations: The wallet complies with national or regional certification
       requirements. For example the eIDAS Revision regulation, where EUDI Wallet certification is
       mandatory.

    1. Components to be certified and/or attested to:

        1. Does the digital wallet mobile app have to be certified, and to which certification standard? If
           so, is the digital wallet certified?

        1. Does the secure element in the mobile device have to be certified, and to which certification
           standard? If so, is the secure element certified? For example: Common Criteria or
           GlobalPlatform certification

        1. Does the digital wallet backend have to be certified, and to which certification standard? For
           example: ISO 27001 audit

        1. Are there any other components in the digital wallet eco-system to be certified, and to which
           certification standard? If so, are the other components certified? For example: HSMs that are
           Common Criteria or FIPS 140-3 certified

    1. Evidence of certification:

        1. The digital wallet provider must supply evidence to the holder that its certification is up to
           date

        1. Is there a certification body (in the applicable country/region) that publishes lists of certified
           digital wallets?

        1. Does the certification body publish certificates or reports about the digital wallet
           certifications?

1. Counterparties: In the context of a digital wallet, a counterparty is a person, organisation or thing to
   whom a digital wallet is connecting to execute a transaction. The counterparty could be an issuer of
   credentials, an online shop requesting age verification, a police officer, or a passport e-gate etc.

    1. Counterparty Identity Verification

        1. The wallet should inform a holder that the counterparty that they are interacting with is who
           they say they are (see UI/UX section). For example:

            - If the holder is being offered a new digital credential by an organization, the holder
              should be able to quickly and easily identify the organization and see that it is
              legitimate

            - When the holder is being asked to digitally sign a contract, the holder should be able
              to quickly identify the who the requester is and determine that they are legitimate

            - The holder should be able to proactively send a verification request to an
              organization (or another user) to determine that they are legitimate

        1. The holder should be able to see several levels of detail about the counterparty. For example:

            - Visual confirmation (green tick style) that the counterparty has been verified by an
              authority

            - Detail about the counterparty’s identity, for example legal identifier, company name,
              registered address, incorporation number

            - Detail about a verification that has taken place e.g. digital signature matches,
              vouching organization process, Legal Entity Identifier details, legal and regulatory
              obligations the counterparty may have regarding revealing the shared information

        1. The holder should be able to quickly and easily determine that the counterparty is allowed to
           ask what they are asking, and if it is a reasonable request such as:

            - Certain regulations may impose limitations on data sharing transactions, dictating
              who can request specific information. This information should be conveyed to the
              user

            - The digital wallet should have the capability to automatically dismiss requests that
              are not permitted. The digital wallet should incorporate a rules engine, or something
              similar, to ascertain whether a particular request from a specific issuer is not allowed
              in one jurisdiction but is permissible in another

            - The digital wallet should confirm the legitimacy of an issuer and their authorization to
              issue the proposed type of credential and provide appropriate evidence to the holder

1. Audit: Digital wallets have a strong connection with Privacy and Legislative Compliance issues. There
   can be conflicts between audit and privacy requirements. It’s crucial to carefully design a digital
   wallet that can effectively strike a balance between user privacy and regulatory Considerations
   include:

    1. User Audit: Holders of a digital wallet should be able to view all their transactions, use them as
       evidence of activities such as proof of purchase, and can erase their transaction history

    1. Legal Audit:

        1. The digital wallet may need to provide an activity log for one or more actions under legal
       authority

        1. Digital wallets, like any other technology, are subject to local laws and regulations. In certain
           specific circumstances, such as a criminal investigation, legal authorities may have the right to
           examine the content and transaction history of a holder’s digital wallet. This would be similar
           to how they can execute a search warrant to inspect the contents of a person’s physical
           property, like a filing cabinet. However, the specifics can vary based on the jurisdiction and
           the privacy policies of the digital wallet provider. It’s important for holders to understand the
           terms of service and privacy policies associated with their digital wallet

1. Accountability: Accountability: Digital wallets facilitate access to services from various entities, and
   there should be mechanisms to hold the responsible parties accountable. Like most categories of Safe
   Digital Wallets, the prerequisites for accountability can be bifurcated into:

    1. Technical strategies, which involve the use of hardware, software, and protocols

    1. Governance strategies, which necessitate human intervention in adherence to established laws,
       regulations, policies, rules, or even through reputation systems


[^1]: <https://digital-strategy.ec.europa.eu/en/policies/eudi-wallet-toolbox>

[^2]: <https://diacc.ca/wp-content/uploads/2023/04/PCTF-Digital-Wallet_Conformance-Profile-Final-Recommendation-V1.0.pdf>

[^3]: <https://www.icao.int/security/mrtd/downloads/technical%20reports/icao_mrtd_history_of_interoperability.pdf>
