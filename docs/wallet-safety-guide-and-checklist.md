# Wallet Safety Guide and Checklist
OpenWallet Foundation Safe Wallet Special Interest Group (OWF-SW-SIG)<br/>
v1.0<br/>
18th June 2024

## Revision History

| Version | Date | Changes | Authors |
| ------ | -------------- | -------------------------- | --------------------- |
| v1.0   | 18th June 2024 | Finalised.                 | Andy Tobin            |
| v0.961 | 28th May 2024  | Update checklist for Accountability section <br/> Updated footnotes <br/>   Updated text in first sections| Drummond Reed <br/> Andy Tobin <br/> Daniel Bachenheimer |
| v0.96  | 7th May 2024   | Updated audience, scope, based on feedback and  <br/> test run exercises by Consult Hyperion, Innopay <br/> and Canadian participants | Juliana Cafik <br/> Andy Tobin <br/> Tim Bloomfield </br> Dan Bachenheimer |
| v0.951 | 26th Mar 2024 | Added EU Digital identity Wallet example to the Holder </br> Binding section | Dan Bachenheimer |
| v0.95 | 25th Mar 2024 | Updates following further reviews. | Andy Tobin <br/> Juliana Cafik <br/> Jorge Flores <br/> Keith Kowal |
| v0.91 | 25th Feb 2024 | Incorporated external feedback from Jamie Smith++. <br/> Multiple refinements annd clarity edits. | Dan Bachenheimer <br/> Juliana Cafik <br/> Jamie Smith ++ <br/> Andy Tobin |
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

- [Introduction](#introduction)
- [Audience](#audience)
- [Scope](#scope)
- [Privacy](#privacy)
    - [Tracking](#tracking)
    - [Correlation](#correlation)
    - [Observation](#observation)
    - [Privacy Checklist](#privacy-checklist)
- [Security](#security)
    - [Trusted Processes](#trusted-processes)
    - [Security Design Controls and Considerations](#security-design-controls-considerations)
    - [Security Checklist](#security-checklist)
- [Wallet Locking and Unlocking Mechanisms](#wallet-locking-and-unlocking-mechanisms)
    - [Locking and Unlocking Checklist](#locking-and-unlocking-checklist)
- [Holder Binding](#holder-binding)
    - [Additional information regarding biometrics in holder binding](#additional-information-regarding-biometrics-in-holder-binding)
    - [Holder Binding Checklist](#holder-binding-checklist)
- [Regulatory Compliance](#regulatory-compliance)
    - [Regulatory Compliance Checklist](#regulatory-compliance-checklist)
- [Certification](#certification)
    - [Certification Checklist](#certification-checklist)
- [User Interface / User Experience](#user-interface-user-experience)
    - [UI/UX Rules](#ui-ux-rules)
    - [Resources and References](#resources-and-references)
    - [User Interface Checklist](#user-interface-checklist)
- [Counterparties](#counterparties)
    - [Counterparties Checklist](#counterparties-checklist)
- [Audit ](#audit)
    - [Audit Checklist](#audit-checklist)
- [Accountability](#accountability)
    - [Checklist for Technical Accountability Mechanisms](#checklist-for-technical-accountability-mechanisms)
    - [Checklist for Governance Accountability Mechanisms](#checklist-for-governance-accountability-mechanisms)
    - [Accountability Checklist](#accountability-checklist)

## Introduction

Digital wallets are at the forefront of transforming digital
interactions for businesses, governments, and individuals. Despite their
innovative potential, digital wallets are still in their nascent stages,
rapidly evolving, and rely on complex cryptographic technologies and
conformance to emerging regulations, standards and frameworks.

As demand surges and new digital wallets enter the market, the
intricacies of their functionality, design, and implementation pose
significant challenges for both those with and without technical
expertise.

The OpenWallet Foundation's Safe Wallet Special Interest Group
(OWF-SW-SIG) is responding to these challenges by providing this
document to serve as a guide and checklist for wallet developers and
product managers. The intention is to provide them with help and
guidance to create wallets that have safety and security of the
individual user at the forefront of design and development choices.

The OWF-SW-SIG has developed this document with the input of wallet
experts drawn from across a broad spectrum of geographies and
organizations. Wallet safety is characterized by a number of
capabilities and functions that should ideally be present in wallets
that preserve user privacy and data security. By taking these factors
into account, the OWF-SW-SIG seeks to enable wallet developers to avoid
introducing loopholes that could, over time, be exploited to the
detriment of end users.

## Audience

The intended audience of this document is the digital wallet product
managers and developers building current or future code at the
OpenWallet Foundation, and the companies building products and services
upon them. The document may also be of interest to implementers of other
wallet platforms, policy-makers and others in the growing wallet
industry who want to know what considerations should be taken into
account when developing or assessing digital wallets.

## Scope

The scope of this document includes digital wallets and their inner
workings, as well as some of the systems and components with which they
interact. Digital wallets could be cloud based, native app based or a
hybrid of the two, the principles in this document remain valid for
these different configurations.

The interactions across digital wallets and other connected systems is
an important factor in the safety considerations for wallet users which
is why they have been included.

For this first version of the document, each category, described below,
has a checklist which can be used to ensure that due consideration is
given to the key safety aspects of wallet design and development.

## Overview

Digital Wallets empower users to manage their digital assets, such as
identity information, financial instruments, tokenized assets, and
enable the issuance and verification of digital credentials to name a
few.

Without attention to detail, wallet providers may introduce new
vulnerabilities, including security weaknesses or potential avenues for
unwanted surveillance, profiling, fraud, and user correlation.

These risks are amplified when digital interactions, once confined to
secure and controlled environments, transition to broader, large-scale
open ecosystems. Such ecosystems, which are expanding on national and
international levels to leverage advancements in digital credentials
standards development, cannot be governed by a single entity, making
comprehensive oversight challenging.

To deal with these risks among and across heterogenous ecosystems, most,
if not all, digital wallets include intricate cryptography and protocols
limiting the expertise needed to identify and mitigate these
vulnerabilities. Consequently, there is a risk that well-meaning digital
wallet initiatives, when deployed on a large scale, could inadvertently
introduce issues that undermine or erode trust in the ecosystem,
particularly if user profiling and correlation become widespread.

A pertinent example is the evolution of internet cookies, which, while
originally designed for simple tasks like maintaining shopping cart
contents, have evolved into potent tools for user tracking and
surveillance.

Developers and product managers that are concerned and curious can use
this document to navigate this new world of digital wallets in their own
work, or to ask their suppliers the right questions to ensure they
create safer digital wallets that mitigate these risks for their users
based on the intended use case(s).

To simplify a very complex topic, this document separates wallet safety
considerations into ten categories, each of which is described in more
detail:

1.  Privacy

2.  Security

3.  Wallet Locking and Unlocking Mechanisms

4.  Holder Binding

5.  Regulatory Compliance

6.  Certification

7.  User Interface / User Experience

8.  Counterparties

9.  Audit

10. Accountability

Each category includes details on considerations that should be taken
into account, as well as useful references and links to additional
information.

## Privacy

In the context of digital wallets, privacy primarily relates to how a
user's activities are protected from unwanted **tracking,**
**correlation, and observation**.

Digital wallets and the digital credentials they manage, along with the
protocols involved in their issuance and verification, introduce a new
set of challenges that don't exist in the world of physical (paper and
plastic) credentials.

### Tracking

-   Holder-specific or wallet-specific unique identifiers that may be
    shared, without holder choice, with every transaction should be
    avoided.

    -   Such identifiers are akin to a tracking beacon that allows
        colluding entities to correlate associated activities of a
        holder using that wallet.

    -   This is particularly dangerous when proxy verification services
        are used, that process verifications for many relying parties
        and will be able to observe and track such an identifier and
        profile the behaviors of associated holders.

    -   An example of such an identifier is a wallet serial number in
        the "metadata" of the credential exchange transaction.

    -   Although not necessarily wallet-specific, the exposure of IP
        addresses used in digital interchanges should be factored into
        the overall operational risk profile.

-   Credential-specific unique identifiers that are shared, without user
    choice, are another class of unique identifiers that should be
    avoided.

    -   While not as privacy impacting as holder or wallet-specific
        identifiers, because it isn't necessarily shared with every
        transaction, a credential-specific identifier that the user
        cannot avoid sharing will enable transaction correlation
        whenever that credential is used.

    -   An example of a credential-specific identifier is a revocation
        index position or an issuer signature in the "metadata" of the
        credential exchange transaction.

    -   Another example of credential-specific identifiers may come in
        the form of payment credentials which may contain unique
        identifiers for compliance within the financial services
        industry.

    NOTE: A useful comparison of different credential types has been
    carried out by [Andre Kudra, Torsten Lodderstedt, Paul Bastian, Mirko
    Mollik, Maaike van Leuken, Caspar
    Roelofs](https://docs.google.com/spreadsheets/d/1X93ptJcmfX1NZEo5E7ElnqJ-knDS4Dj6JOYSJ_2PsUw/edit#gid=1084392809).

### Correlation

-   Digital wallets and their associated ecosystem(s) and supporting
    functions should prevent issuers from being able to track where,
    when, or with whom holders use their digital credentials.

-   Digital Wallet ecosystems should prevent Issuers and verifiers of
    verifiable credentials from tracking their use which would enable
    them to, for example, build user profiles. However, transactions
    where usage tracking is a fundamental part of the use case that
    holders are fully aware of (payments being an example) would be
    accepted in that context.

    -   Although not necessarily wallet-specific, Issuers should not be
        able to aggregate holder information.

    -   Although not necessarily wallet-specific, Verifiers should be
        prevented from contacting issuers (decoupling) for any reason
        including to check the revocation status of verifiable
        credentials. If decoupling is not implemented, issuers could
        track the use of digital credentials they have issued. This is
        known as the "phone home" problem[^1]:

        -   Phone home architecture should not be used.

        -   Back-channel interactions between verifiers and issuers that
            are not visible to holders should not be used.

    -   Holder Wallet agents should check the authenticity and integrity
        of each issuer-signed credential to determine whether to trust
        it.

    -   Verifiers should not be able to access any digital wallet
        content without holder consent

### Observation

-   The wallet should support privacy preserving sharing mechanisms
    that, for example, provide only the verifiable proofs required by
    the service provider to obtain the requested service (e.g., the
    ability for the wallet to disclose only the requested first name and
    photo from a driving license rather than all the data in that
    license), and proving possession of data without revealing the
    values of the data itself (such as generating an age predicate proof
    to prove over 18 without revealing date of birth).

    -   This can be achieved using techniques such as selective
        disclosure and zero-knowledge proofs.

-   The wallet should support privacy enhancing sharing mechanisms that
    establish secure communication with issuers and verifiers (NOTE:
    covered in the Security section in greater detail)

-   Digital wallet code providers and/or digital wallet cloud operators
    should not be able to observe or track transactions undertaken by
    wallet holders.

    -   This is particularly important in the case of hybrid and pure
        cloud wallets, where transactions are performed on the wallet
        operator's infrastructure.

    -   Wallet code providers and wallet cloud operators should not be
        able to access the contents of digital wallet transactions or
        backups.

    -   Wallet code providers and wallet cloud operators should not have
        a "master key" that enables them to access the contents of
        holder wallets for which they have custody.

-   Digital Wallet ecosystem and technology providers.

    -   Organizations that provide the infrastructure to which digital
        wallets connect in order to issue or verify credentials
        (typically called credential exchange platforms) should not be
        able to examine the contents, source or destination of wallet
        transactions.

    -   In many situations, such credential exchange platforms will need
        to "translate" from an encrypted credential envelope to/from
        clear text for integration with other systems, such as customer
        onboarding systems.

    -   In this case, the credential exchange platform should manage the
        data in such a way that it is transient and not stored,
        observable, or trackable to protect wallet holder privacy.

-   Proxy services may provide credential issuance/verification services
    for many issuers and verifiers. In doing so, they could observe and
    correlate wallet transactions across large ecosystems.

    -   Proxy services should not observe, store and correlate wallet
        transactions.

    -   Holders should be informed that they are dealing with a proxy
        service rather than the true end issuer/verifier.

-   The wallet should provide clear, understandable and easy-to-use
    mechanisms for the user to provide consent to add data to, or read
    data from, their wallet. This is a major privacy consideration and
    ensures the user is in control of their data.

-   Users (wallet holders) should be able to track the consent that they
    have given.

-   The act of provision of consent by the user should not leak personal
    information itself. For example, holder wallet apps based React
    Native framework commonly make use of this open-source npm package
    https://www.npmjs.com/package/react-native-device-info which exposes
    sensitive information such as unique device identifier, device type
    and brand etc. A unique device identifier may be classified as PII
    under certain jurisdictions such as CCPA.

### Privacy Checklist

-----------------------------------------------------------------------
- [ ] Holder- or wallet-specific unique identifiers shared without
      holder choice are not used.
      
- [ ] Credential-specific unique identifiers shared without holder
      choice not used.
      
- [ ] A credential issuer is unable to track where, when or with whom
      holders use those credentials.
      
- [ ] The wallet supports privacy preserving credential mechanisms.

- [ ] Wallet developers, providers or operators are not able to observe
      or track transactions undertaken by holders.
      
- [ ] Credential exchange platform providers should not be able to
      examine the content, source or destination of wallet transactions.
      
- [ ] Credential issuance and/or verification proxy services should not
      be able to observe, store and correlate wallet transactions.
      
- [ ] The wallet should provide clear and simple consent mechanisms.

- [ ] Holders should be able to track consents given.

-----------------------------------------------------------------------

## Security

At its most basic, a digital wallet is a holder-controlled digital
container sitting between Issuers of verifiable credentials and a
Verifier and/or Relying Party that authorizes access to, and the
provisioning of, services.

A digital wallet is a critical confluence point in a credential-based
interaction and should be able to establish, maintain and attest to the
trusted processes required for a trustworthy, secure and safe digital
transaction.

According to the European Union[^2], a compliant EU digital wallet _will
provide a secure and convenient way for European citizens and business
to **share identity data** needed for accessing digital services
such as checking in at the airport, renting a car, opening a bank
account, or logging in to their accounts on large online platforms._

Digital wallets are instrumental to the acquisition, storage and
presentation of credential-based assertions, and the security of wallets
is essential to safeguarding the integrity and privacy of those
assertions. Wallet architecture should consider security by design and
Zero Trust security best practices with a focus of least privilege for
applications. Wallet components should correspondingly be based on
robust security controls capable of providing evidence to the context,
methodology, and strength of the controls as well as confirm their
authenticity and state while in use. Wallet security controls should
also mitigate risks from evolving attack surfaces and vectors on
consumer devices, to detect potential vulnerabilities such as (but not
limited to) phishing attacks, man-in-the-middle, relay attacks, malware
and lost or stolen devices.

The Digital Identity and Authentication Council of Canada's (DIACC's)
Digital Wallet Component Conformance Criteria states: "The integrity of
a Trusted Process is paramount because many Participants may rely on the
output of the process, often across jurisdictional, organizational, and
sectoral boundaries."

The DIACC's Digital Wallet Conformance Profile[^3] also includes a
comprehensive breakout detailing the Type of Risk, Threat Category,
Impact and Proposed Mitigation, which is a good example of what and how
to assess digital wallet conformance to these critical design elements.

Expanding on the foundational work that DIACC has done, this document
describes Trusted Processes and Security Design Controls and
Considerations that may be necessary to provide safety for wallet
holders as well as meet the required levels of assurance for issuers,
verifiers and relying parties and provide an awareness of state via
attestation for:

### Trusted Processes

-   Wallet Selection: Wallet selection refers to the process of the user
    or device operating system choosing a digital wallet for a specific
    purpose while ensuring optimal security and safety. In a situation
    where multiple wallets are available, a wallet selector is an
    additional step in the wallet user flow when sending or receiving
    transactions, to prompt a provider to choose the specific digital
    wallet they wish to use for a specific use-case. The goal is to
    select a wallet that not only provides convenience but also ensures
    safety and security for all interactions on an ongoing basis. This
    is fundamental to the establishment of trust, the assurance of
    privacy and the efficacy necessary to create a positive and
    adoptable wallet-holder experience. Wallet selection can pose
    several security risks and considerations for prevention include
    (but are not limited to):

    -   Malware:

        -   Regular Software Updates: Continually update wallet
            software, operating systems, internet browsers, phone
            firmware, and antivirus software to fix known
            vulnerabilities as they are discovered

        -   Secure connections and end-point management for all network
            interactions, including NFC and Bluetooth low-energy enabled
            hardware

        -   Phishing resistant authentication

        -   Obtain wallet software from official sources

        -   Root detection for mobile devices

    -   Social Engineering prevention involves a combination of
        technical measures, policy enforcement and wallet holder
        education. Strategies for mitigation include:

        -   User Education: Users should be educated about the common
            tactics used in social engineering attacks and how to
            identify potential scams.

        -   Phishing resistant authentication

        -   End-point security

        -   Regular audits of accounts and access levels

        -   Software updates to prevent evolving known vulnerabilities

        -   Policy enforcement for policies and procedures that consider
            potential social engineering vectors and provide specific
            guidance on steps to take to avoid successful attacks

    -   Brute Force Attack Mitigation options:

        -   Phishing resistant authentication

        -   Account lockouts and rate limiting

        -   Strong data encryption and storage

    -   End-point authentication to prevent:

        -   Man-in-the-Middle Attacks such as:

            -   Relay Attacks: relaying information between parties

            -   Replay Attacks: Capturing and reusing information

-   Key Management: this is an essential function involving the handling
    and safeguarding of cryptographic keys to ensure the security and
    integrity of the holder's digital assets. Primary security
    considerations and controls for key management are:

    -   Storage: Keys should be stored securely to prevent unauthorized
        access.

    -   Key Generation

    -   Backup and Recovery: A robust key recovery system, or process,
        is critical to ensure users are able to regain access to their
        wallet(s) if the private keys are lost or compromised.

    -   Usage: Keys should be protected while in use in a secure manner
        and within a secure environment

    -   Key Rotation: The process of changing keys to maintain integrity
        and security

    -   Key Revocation: The process of revoking and replacing
        compromised keys

    -   Audit: Processes for logging and detecting security risks to
        keys.

-   Credential Signature / Format: A credential signature in the context
    of a digital wallet is a digital proof that verifies the
    authenticity of the credential. For a secure credential signature,
    it is important for the wallet to support:

    -   Credential Signature Verification: mechanisms to verify the
        authenticity of the credential signatures to ensure they have
        not been tampered with and are issued by a legitimate trusted
        authority

    -   Secure Storage of Credentials: Secure storage to prevent
        unauthorized access and tampering with verified signatures

    -   Privacy Preservation: Mechanisms to support the verification of
        credentials without revealing unnecessary personal information,
        such as selective disclosure and zero-knowledge proofs.

-   Credential Management: Credential management in the context of a
    digital wallet refers to the process of handling and safeguarding
    digital credentials to ensure their integrity.

    -   Storage: Credentials should be stored securely to prevent
        unauthorized access.

    -   Backup and Recovery: A recovery system, or process, to ensure
        holders are able to regain access to their wallet(s) if their
        credentials are lost or compromised.

    -   Usage: Digital wallet architecture should support credential use
        in a secure manner and within a secure environment

    -   Revocation: The process of revoking and replacing compromised
        credentials

    -   Audit: Processes for logging and detecting security risks to
        credentials.

-   Presentation Protocols: Presentation protocols in the context of a
    digital wallet refer to the standardized methods for presenting,
    sharing and verifying digital credentials. The protocols ensure
    interoperability and secure communication between different entities
    in the digital ecosystem, include standards-based credential
    presentation and verification and are crucial to the security and
    privacy of a holder's digital identity. To preserve the integrity
    of presentation protocols several wallet security measures should be
    implemented:

    -   Phishing-resistant user authentication to ensure the holder
        presenting the credentials is the legitimate holder of both the
        wallet and the credential

    -   Secure, Phishing and 'spoof' resistant user interface

    -   Strong data encryption and storage to secure credentials and
        prevent unauthorized access

    -   Digital wallet user interface and architecture to support
        credential presentation and usage in a secure manner

    -   Privacy-preserving mechanisms to support the presentation of
        credentials without revealing unnecessary personal information,
        such as selective disclosure and/or zero-knowledge proofs

    -   Audit processes for logging and detecting security risks, such
        as malware, phishing attacks, man-in-the-middle attacks, etc,
        that may impact credential presentation.

-   Mechanisms to convey consent: User Consent is a critical aspect of
    privacy and security in digital wallets. It provides credential
    holders with control over wallet interactions and the sharing of
    specific information, such as credentials with a service provider.
    To support secure holder-consent, the following mechanisms should be
    implemented:

    -   Phishing-resistant user authentication to ensure the holder
        providing consent is the legitimate holder of both the wallet
        and the credential

    -   Phishing and 'spoof' resistant user interface

    -   Strong data encryption and storage to secure sensitive data and
        consent records and prevent unauthorized access

    -   Revocation mechanism to provide holders with the option to
        revoke consent such as a protocol for sending the revocation to
        the relying party, and a regulatory framework for requiring the
        relying party to act upon such revocation.

### Security Design Controls and Considerations

-   Security by design: Implementing secure by design strategies
    throughout the software development lifecycle to enhance security
    outcomes. These approaches aim to improve collective security by
    incorporating security considerations throughout the software
    development life cycle. In the context of open-source digital
    wallets, these strategies are essential for advancing collective
    security. By implementing secure by design principles during the
    design phase of product development, the number of vulnerabilities
    that can be exploited by adversaries can be minimized:

    -   Zero Trust: assumption of breach requiring verification of each
        request

    -   Open Design: the security of a mechanism should not depend on
        the secrecy of its design or implementation

    -   Attack surface minimization: a security strategy that aims to
        reduce the number of potential vulnerabilities in a wallet by
        limiting the ways in which it can be attacked. This can be
        achieved by reducing the number of entry, end points and APIs
        and by limiting the functionality and access of the wallet to
        only what is necessary for its intended purpose. By minimizing
        the attack surface, the wallet becomes more difficult to
        compromise, as there are fewer ways for an attacker to gain
        access or exploit vulnerabilities.

    -   Defense in depth: a security strategy that employs multiple
        layers of protection to slow down or prevent an attack from
        gaining unauthorized access to information. Each layer provides
        protection so that if one layer is breached, a subsequent layer
        is already in place to prevent further exposure.

    -   Least privilege: a security concept that requires each user,
        system, or process related to the wallet to have a minimum level
        of access necessary to perform its function. This means that
        users, systems, or processes should only have access to the
        resources and information related to the wallet that they need
        to do their job, and nothing more. This approach helps to reduce
        the risk of unauthorized access or malicious actions, as it
        limits the potential damage that can be caused if a user,
        system, or process is compromised

    -   Need to know: a security concept that states that access to
        information should be restricted to individuals who require that
        information to perform a specific task or function. This means
        restricting access to the information that is necessary for them
        to complete a task, and no more. This principle is closely
        related to the principle of least privilege. By following the
        need-to-know principle, wallet developers can reduce the risk of
        unauthorized access or disclosure of sensitive information

    -   Role Based Access Controls (RBAC): is a method of regulating
        access to resources based on the roles of individual users. In
        RBAC, permissions are assigned to roles, and users are assigned
        to roles. This allows for access to be restricted based on
        function, such as wallet Holder, Software Developer, Quality
        Assurance (QA), Project Managers, Security Analysts, and System
        Administrators, with roles being broad for general access or
        fine-grained to restrict specific capabilities.

    -   Separation of Duties: a security principle that shifts the
        burden of security as much as possible away from the end-user,
        or holder in the context of a wallet, to the wallet
        developer(s). This principle is based on the idea that no single
        individual should have complete control over a critical process
        or system, and that by distributing responsibilities and
        privileges, the potential for abuse or misuse is reduced.
        Separation of duties is often implemented through role-based
        access controls (RBAC).

-   Secure by Default: is a principle aimed at shifting the burden of
    security as much as possible away from the end-user (or holder) back
    to the wallet developer(s). Essentially it is about designing
    wallets that require minimal hardening and are secure when deployed.
    In the context of digital wallets this is much harder to do than
    secure by design, as each wallet holder's environment is different.
    What works well for one wallet architecture might not work for
    another. It is also important to consider that secure by default
    features go through rigorous testing and periods of customer
    feedback to ensure benefit to the largest number of end users
    possible.

-   Software Security Controls: such as [NIST
    800-53](https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final)
    and [OWASP MASVS](https://mas.owasp.org/MASVS/), are
    safeguards, or countermeasures, prescribed to meet a set of defined
    security requirements. Controls are designed to address specific
    needs as specified by a set of security requirements. They aid in
    protecting the integrity of systems that support the wallet, involve
    flaw remediation, malicious code protection, system monitoring and
    software integrity and include:

    -   Management Controls: security controls that focus on the
        management of risk and the management of information system
        security.

    -   Operational Controls: controls that are primarily implemented
        and executed by people (as opposed to systems).

    -   Technical Controls: security controls that are primarily
        implemented and executed by the information system through
        mechanisms contained in the hardware, software, or firmware
        components of the system.

-   Software Bill of Materials (SBOM): An SBOM is a key building block
    in software security and software supply chain risk management. It
    provides transparency into all constituent parts of the software,
    which is crucial for understanding exactly what has gone into the
    software that is being distributed and used for the wallet. The
    specifics of what is included in an SBOM can vary depending on the
    software in question, however it should be regularly updated with
    details including:

    -   Names of components

    -   Versions

    -   Licenses

    -   Component relationships and dependencies

    -   Third party libraries, artifacts, scripts and package versions

    -   Catalog of all the software in an application including deeply
        nested

-   Software Development Best Practices and Software Assurance Models:
    such as [NIST
    800-218](https://csrc.nist.gov/pubs/sp/800/218/final)
    and [OWASP SAMM](https://owaspsamm.org/about/) to
    improve software security postures for the design, development and
    deployment of secure software.

### Security Checklist

-----------------------------------------------------------------------
- [ ] A wallet selection protocol is in place when multiple wallets exist
      on a device in a secure manner where possible, and avoiding vendor
      lock-in.
      
- [ ] Key management is designed and addressed appropriately for current
      and future envisaged use cases, and regulatory and/or regional
      requirements.

- [ ] The wallet should be designed to support "chain of custody"
      requirements.

- [ ] The wallet is designed to be resistant to spoofing,
      attacker-in-the-middle, and phishing attacks.

- [ ] Security By Design or Security by Default is utilized consistently
      throughout the wallet design, development and deployment process.

- [ ] Software security controls are utilized to protect the code and
      operations of the digital wallet.

- [ ] A software bill of materials is available and acceptable.

- [ ] Appropriate software development assurance models are applied.

- [ ] Recovery should be designed taking into account how it is a major
      attack vector, and that some credentials and data should not be
      recoverable.
      
-----------------------------------------------------------------------

## Wallet Locking and Unlocking Mechanisms

A safe digital wallet will provide a secure and user-friendly means
through which an authorized user may unlock and lock it to minimize
fraudulent use. While these lock/unlock mechanisms fall into the
categories of security and UI/UX, the authors feel that it is important
to highlight them here, separately. It is also important to
differentiate wallet lock and unlock requirements, which are typically
driven by the wallet provider, from user authentication requirements,
which are typically driven by the requirements of relying parties -
although they may utilize similar technologies.

The mechanism and controls[^4] to lock and unlock a wallet are dependent
on the level of assurance (as defined by issuers and verifiers of
credentials) of the wallet and the sensitivity of the data that the
wallet will store.

-   At a minimum, the wallet should require a PIN or password to access
    sensitive information including, but not limited to, personal
    identifying information (PII) and personal health information (PHI).

-   For mobile wallets, the wallet security mechanism may be tied to the
    device security mechanism, such as a device PIN/Password or
    biometric. In addition, device biometrics (fingerprint/FaceID) may
    be used to bypass a PIN/Password. Consideration should be given to
    the possibility of the device holder switching off device-specific
    security completely.

-   A wallet (web/mobile) may use an external authenticator as part of
    the wallet unlock mechanism.

-   For medium or high assurance wallets a PIN/Password should adhere to
    complexity rules to reduce the possibility of guessing the
    PIN/Password. For example, minimum lengths, no patterns or
    dictionary words. In addition, the wallet user should have a limited
    number of attempts to enter the PIN/Password with increasing timeout
    delays (rate limiting).

-   High assurance wallets should support multi-factor authentication -
    e.g., Biometrics, hardware cryptographic authenticators,
    password/PIN and OTP schemes

Once unlocked the wallet should include additional controls to protect
the privacy of user data and maintain the appropriate level of security
of the wallet; please refer to the Security section for further detail.
The following is a minimal list of controls specific to wallet lock and
unlock.

-   The wallet locks if focus is lost.

-   The wallet locks after a pre-defined period of inactivity.

-   On mobile devices, application thumbnails (displayed during app
    switching or selection) are blank or otherwise rendered unreadable
    to protect sensitive information.

-   The wallet should properly secure the PIN/Password and should not
    persist the PIN/Password in memory after an authentication event.

-   Authentication events may be triggered during sensitive operations
    such as displaying credential data, presenting a credential,
    changing a password/PIN, or operations that support holder binding
    requirements. The authentication event may use the default wallet
    unlock mechanism or require additional authentication mechanisms
    (i.e. step-up authentication). See the security section.

For other examples of level of assurance-based requirements related to
wallet locking see NIST SP 800-63B[^5] and the PCTF Digital Wallet
Conformance Profile[^6].

In proximity use cases, the wallet should be able to present information
without requiring the physical device to be unlocked while the holder is
advised of what information is being requested and provided a means to
consent to sharing it for the specified purpose(s) - see the section on
UI/UX for further detail. In this case it is important that the reader
is authenticated to prevent any bad actor with a reader nearby
extracting data without user consent. This feature protects the user's
privacy and enforces the principle of data minimization. Unlocking a
digital wallet at the point of presentation may expose sensitive
information outside of the context of the data being requested by the
verifier, either through theft of the host device or legal authority to
inspect/confiscate a host device.

Accessibility and usability should be incorporated into the functional
and non-functional requirements of the unlocking mechanism while taking
into account associated risks. Adoption will be impacted if a control
mechanism is not usable or accessible leading to the use of less secure
methods and/or segments of the population being excluded from using the
wallet.

In summary, wallet lock/unlock mechanisms protect the wallet from
unauthorized access which includes viewing, adding, updating, sharing
and deleting wallet contents based on wallet design requirements whereas
relying parties dictate the Identity, Authenticator, and Federation
Assurance Levels, as applicable, they require access to their services.

### Locking and Unlocking Checklist

-----------------------------------------------------------------------
- [ ] Locking and unlocking methods are sufficient for the required use
      case(s) and context.
      
- [ ] Once unlocked, appropriate controls are in place to maintain the
      appropriate level of security.

- [ ] Proximity use without physical device unlocking is implemented
      appropriately for the required use case(s) and context.
       
-----------------------------------------------------------------------

## Holder Binding

Digital wallets are applications used to receive, store, and share
attributes in a secure, privacy enhancing fashion. To prove that the
legitimate, natural person is receiving, in possession of, or sharing
these attributes requires a means to bind the wallet and the credentials
it manages to the natural person.

In 1995, for example, the International Civil Aviation Organization
(ICAO) clearly recognized the desirability of pursuing the use of
biometrics in travel documents as the single best way to link the
document and its rightful "owner".[^7]

In this example, the issuing authority binds the identity attributes to
the authorized holder during the issuance process by including biometric
data in the cryptographically signed logical data structure. When the
holder makes an identity claim, the Relying Party (verifier) can
determine the authenticity and integrity of the identity attributes and,
through biometric recognition, determine if the authorized holder is
presenting the information during the verification process. This works
well for the intended use case: in-person identity verification by
government authorities for cross-border travel.

From a wallet safety perspective, holder binding can be split into
sub-categories relating to the points in the chain of custody of the
wallet and the credentials it contains. It should be noted that chain of
custody differs depending on whether the wallet will perform holder
authentication during a transaction with a relying party, or whether the
relying party will perform holder authentication (e.g. by comparing the
portrait image from the authenticated credential to the presenter of the
credential).

-   Holder binding to the device and wallet.

    -   The wallet should have a mechanism to associate, and
        differentiate, one or more natural persons to the device as part
        of the wallet provisioning and setup process.

    -   Where biometric binding is used, the wallet should have a
        mechanism to store, and share, associated metadata such as:
        signature of authority providing the biometric data, live
        capture by authority indicator, quality assessment method and
        result, presentation attack detection (PAD) method and result,
        morph attack detection (MAD) method and result.

    -   The wallet should have a mechanism to store, and share, the
        associated assurance level of the issuance process (e.g.,
        reflective of in-person, remote supervised, remote; uniqueness
        determination).

    -   The wallet should take any action if previously set up device
        security (e.g. a fingerprint) is changed (e.g. the addition of a
        new fingerprint which could come from another person).

    -   The wallet may have its own person binding method in addition to
        the one implemented by the device's operating system.

-   Holder binding to their credentials at issuance.

    -   The wallet should provide a mechanism whereby the issuer is able
        to confirm that the person they are issuing the credential to is
        the correct person.

    -   The issuer may be able to insert into the credential (as an
        attribute or metadata) a confirmation that such a check has been
        performed, and how it was performed, such that a relying party
        can confirm what checks the issuer carried out.

-   Holder binding to their keys (see Key Management in the Security
    section).

    -   The wallet should have a mechanism to bind the private keys
        within the wallet that are used for proving possession, for
        signing, etc, to each holder. For example:

        -   Device keys are bound to the device.

        -   A holder is bound to the device keys via the device OS.

        -   A holder is bound to an identity credential via the
            biometric contained in the identity credential.

        -   The identity credential is bound to the device via the
            device keys included in the identity credential (and signed
            by the issuer).

        -   A relying party will need a mechanism to determine the level
            of confidence it can place in each of these bindings.

    -   This mechanism should operate within a secure enclave or trusted
        execution environment.

-   Holder binding at the point of presentation.

    -   The wallet should have a mechanism to check that the person
        releasing a presentation ("proof") to a relying party is the
        same person to whom the credential was issued.

    -   The wallet may be able to inform the relying party what
        mechanism it used to perform such a check and provide evidence
        of the success of the check.

    -   The wallet should support multiple methods for executing holder
        binding at the point of presentation e.g. PIN entry, biometrics.

    -   The wallet should have the ability to configure the holder
        binding checking it does in response to a trigger in the relying
        party's proof request, i.e. the relying party can request a high
        assurance binding check for a high value transaction, or a low
        assurance check (with less friction) for a low assurance
        transaction.

### Additional information regarding biometrics in holder binding

In each of the Holder binding sub-categories where biometrics are used
as part of the binding process, the additional factors described in this
section should be considered.

All biometric systems are probabilistic and will produce Type I (false
non-match) and Type II (false match) errors which should be factored
into the target use case. These error rates are influenced by factors
such as quality, which is impacted by factors such as the equipment used
to capture the biometric data, the resolution, lighting conditions, pose
angles, environment, and demographic differentials.

Relying on a third-party biometric recognition algorithm operating on a
personal device to compare a selfie captured in real-time against the
selfie captured during registration may be sufficient for some use
cases - but not for others. Edge authentication, where the native or a
3rd party biometric sensor and/or matcher is used, is inherently lower
assurance than in-person authentication where the relying party's
biometric sensor and matcher are used and where the relying party can
determine quality and match thresholds.

The EU Digital Identity Wallet legislation[^8], for example, calls for
Level of Assurance HIGH for User Authentication which necessitates the
use of two of three factors where one factor can be inherence. This is
where, "the applicant is identified as the claimed identity through
comparison of one or more physical characteristic of the person with an
authoritative source;"[^9] and "'authoritative source' means any source
irrespective of its form that can be relied upon to provide accurate
data, information and/or evidence that can be used to prove
identity;"[^10]

An 'authoritative source' for high-risk use cases requires biometric
data to be captured live by a trusted entity, evaluated to be of
sufficient quality for automated recognition, and determined to be
unique within the target population to an acceptable False Positive
Identification Rate (FPIR) at a specified False Negative Identification
Rate (FNIR). This is typically performed by a government agency where,
per NIST SP 800-63A and others, the "Expected Outcomes of Identity
Proofing" is to "Resolve a claimed identity to a single, unique identity
within the context of the population of users the CSP serves."[^11]
Comparing a physical attribute of a natural person to one encoded on, or
in, a government issued credential is NOT identity proofing, it is
identity verification.

For identity resolution (aka, deduplication) we are more concerned with
the false negatives (the misses) versus the false positives (the
erroneous matches) which may be adjudicated manually. This is especially
relevant in the Holder Binding to the wallet. For the highest assurance
levels, for example, we expect that the authoritative source for
biometric data is captured live by a trusted entity and determined to be
of sufficient quality for automated recognition.

### Holder Binding Checklist

-----------------------------------------------------------------------
- [ ] The wallet effectively binds the person to the device and the
      wallet.

- [ ] Holder binding at credential issuance is implemented.

- [ ] Binding of holder to their keys is properly implemented.

- [ ] Holder binding at the point of presentation enables relying
      parties to confirm the right person released a credential.

- [ ] The relying party can specify the level of holder binding
      required at the point of presentation.

- [ ] It is possible to measure the wallet's resistance to holder
      binding attacks.

-----------------------------------------------------------------------

## Regulatory Compliance

For widespread adoption of digital wallets, there should be guardrails
in place where both public- and private-sector implementers can turn to
understand conformance - and for the public to derive trust.

There is a balance to be struck between the enforcement of legislative
rules through technological means versus through a court of law. For
example, it may be decided that it is too technically complex to
implement some legislation rules into a digital wallet, so the designers
may elect to rely on the rule of law as implemented by a court instead.
This would mean that technology does not restrict something from
happening in the wallet, and instead, the rules are enforced through
heavy fines or prison time for the transgressors.

An example of this in the automobile industry is that enforcement of
speed limits in cars is done by the police and the courts, not by the
technology in the car (at least not yet).

Some of the identified legislative issues related to wallet-based data
exchanges are summarized below:

-   Legislation that organizations need to adhere to while processing
    data. E.g. Article 30 of the GDPR places an obligation on
    controllers and processors (organizations, issuers/verifiers) to
    have in place within their organizations a detailed record of
    activities the organization carries out which use personal data.

-   Legislation that ensures the digital rights of the individuals are
    taken care of. e.g. The GDPR has a chapter on the rights of data
    subjects (individuals) which includes the right of access, the right
    to rectification, the right to erasure, the right to restrict
    processing, the right to data portability, the right to object and
    the right not to be subject to a decision based solely on automated
    processing.

-   Article 7 (1) of GDPR states that in situations where the processing
    of data is based on consent, the controller shall be able to
    demonstrate that the data subject has consented to the processing of
    his or her personal data.

As digital wallets become more commonplace, legislation is evolving to
catch up. Some examples of privacy-related legislation that applies to
digital wallets are:

| Regulation                              | Acronym    | Year     | Country |
|-----------------------------------------|------------|----------|---------|
| General Data Protection Regulation      | GDPR       | 2018     | EU      |
| European Digital Identity Regulation    | EUDI/eIDAS | 2024     | EU      |
| California Consumer Privacy Act         | CCPA       | 2020     | US/CA   |
| General Personal Data Protection Law    | LGPD       | 2020     | Brazil  |
| Digital Charter Implementation Act 2022 | DCIA       | 2022     | Canada  |
| Digital Personal Data Protection Act    | DPDPA      | 2024     | India   |

### Regulatory Compliance Checklist

-----------------------------------------------------------------------
- [ ] The wallet complies with legislation for its use cases and
      jurisdiction(s).

- [ ] The wallet implements legislation compliance using technical means
      (reducing the need for legal enforcement).

- [ ] The wallet complies with accessibility legislation.

- [ ] The wallet developer is able to provide evidence of legislation
      compliance.

- [ ] The wallet complies with applicable trust frameworks.

-----------------------------------------------------------------------

## Certification

Certification in the context of digital wallets relates to the formal
evaluation of products according to standards such as Common Criteria.
It is closely associated with the Legislation Compliance topic since
digital wallet regulations in some cases include specific certification
requirements.

This framework does not intend to list all applicable certification
criteria for all use cases in all jurisdictions. Instead, it provides a
list of questions that a wallet designer should be able to answer
relating to the certification compliance of their wallet for its
intended usage scenarios.

-   Compliance with regulations:\[JC4\]

    -   The wallet complies with national or regional certification
        requirements. (Example: The eIDAS Revision regulation, where EUDI
        Wallet certification is mandatory.)

-   Components to be certified:

    -   Does the digital wallet mobile app have to be certified, and to
        which certification standard? If so, is the digital wallet
        certified? (Example: FITCEM certification.)

    -   Does the secure element in the mobile device have to be certified,
        and to which certification standard? If so, is the secure element
       certified? (Example: Common Criteria or GlobalPlatform
        certification.)

    -   Does the digital wallet backend have to be certified, and to which
        certification standard? If so, is the digital wallet backend
        certified? (Example: ISO 27001 audit.)

    -   Are there any other components in the digital wallet eco-system to
        be certified, and to which certification standard? If so, are the
        other components certified? (Example: HSMs that are Common Criteria
        or FIPS 140-3 certified.)

-   Evidence of certification:

    -   The digital wallet provider should supply evidence to the user that
        its certification is up to date (example: There could be information
        on the digital wallet's screen that can be tapped on to get more
        details.)

    -   Is there a certification body (in the applicable country) that
        publishes lists of certified digital wallets?

    -   Does the certification body publish certificates or reports about
        the digital wallet certifications?

### Certification Checklist

-----------------------------------------------------------------------
- [ ] The wallet complies with national or regional certification
      requirements.

- [ ] The wallet's component parts are certified (mobile app, secure
      element, wallet backend, other components such as HSMs).

- [ ] The wallet provider should provide evidence to the user that its
      certification is up to date.

-----------------------------------------------------------------------

## User Interface / User Experience

Digital wallets, like other IT, will gain adoption if useful,
inexpensive, safe, and easy to use. The User Interface (UI) and User
Experience (UX) aspects of digital wallets will drive or diminish
adoption. UI refers to the screens, buttons, toggles, icons, and other
visual elements that you interact with whereas UX refers to the entire
interaction you have with the digital wallet, including how you feel
about the interaction.

### UI/UX rules

-   Intuitive navigation: The digital wallet should be easy to navigate,
    with clear and concise labels for all functions. Users should be
    able to quickly and easily find the information and features they
    need.

-   Visual cues: The digital wallet should use visual cues, such as
    icons and colours, to help users understand what they are doing. For
    example, a green check mark could be used to indicate that a
    transaction was successful.

-   Threat alerting: The digital wallet should clearly and simply alert
    the user if it detects that a fraudulent transaction may be in
    progress and advise them what to do next. For example, the wallet
    should be able to verify that a relying party is legitimate and able
    to ask for the information they are asking for. It should be able to
    confirm that an issuer is legitimate and able to issue a credential
    of a certain type. Conversely, it should let the user know if such
    checks have been passed successfully and the transaction is safe to
    proceed.

-   Accessibility: Does the wallet comply with industry standards and
    legal accessibility requirements? Does it offer intelligent features
    where the wallet can make choices on behalf of the holder? Does it
    allow the wallet to be accessed via multiple channels (e.g.,
    smartphones, web browsers)?

-   Security features: The digital wallet should use the latest security
    features to protect users' data and funds. This could include
    features such as two-factor authentication, biometric login (aka,
    unlock), and data encryption. See the Locking/Unlocking section.

-   Transparency: The digital wallet should be transparent about its
    security features and how it protects users' data. This information
    should be easy to find and understand.

-   User feedback: The digital wallet should provide users with feedback
    on their actions. For example, the digital wallet should notify
    users when a transaction is successful or when there is a problem.

### Resources and References

-   [OWF Wallet User Experience](https://docs.google.com/document/d/1XPgYfd2111NfyUyveIJcXDWjiOdYFPUh/)

-   [UI/UX Design for Digital Wallets: Marrying Security with Intuitive Navigation](https://medium.com/@ethercess/ui-ux-design-for-digital-wallets-marrying-security-with-intuitive-navigation-61acaa66a2c8) \| by Ethercess \| Sep, 2023 \| Medium (medium.com)
    

-   [The Role of UX/UI Design in Cryptocurrency Wallet Development](https://medium.com/@naeemhasan588/the-role-of-ux-ui-design-in-cryptocurrency-wallet-development-3f1fbe97b747) \| by
    Naeem Hasan \| Oct, 2023 \| Medium (medium.com)

-   [W3C Accessibility Guidelines (WCAG) 3.0](https://www.w3.org/TR/wcag-3.0/)

-   [7 Best Practices For Enhancing Your Digital Wallet Security](https://www.appknox.com/blog/best-practices-for-digital-wallet-security) \|
    [www.appknox.com](http://www.appknox.com/)

-   [Digital Wallet Design: Enhancing Your User Experience](https://qubstudio.com/blog/digital-wallet-design/) \| qubstudio.com

-   [How to Improve Mobile UX with Digital Wallets](https://cxl.com/blog/digital-wallets/) \| cxl.com

### User Interface Checklist

-----------------------------------------------------------------------
- [ ] The digital wallet is easy to navigate with clear and concise
      labeling.

- [ ] The wallet uses visual cues, colours and icons to help holders
      understand what they are doing, without holders having to be
      familiar with technical details.

- [ ] The wallet alerts the holder to threats in a simple and clear way
      and provides information about what to do next.

- [ ] The wallet informs the holder when a transaction has succeeded or
      failed.

- [ ] The wallet informs the holder that a data request is from a
      legitimate source and the data requested is proportionate, and
      that it is safe to proceed.

- [ ] The wallet uses multi-factor authentication.

- [ ] The wallet provides information about its security features and
      how holder data is protected.

-----------------------------------------------------------------------

## Counterparties

In the context of digital wallets, a counterparty is a person,
organisation or thing to whom a digital wallet is connecting to in order
to execute a transaction of some sort. The counterparty could be an
issuer of credentials, an online shop requesting age verification, a
police officer, or a passport e-gate.

-   Counterparty Identity Verification

    -   The wallet should inform the user that the counterparty that they
        are interacting with is who they say they are (see UI/UX section).
        For example:

        -   If the user is being offered a new digital credential by an
            organization, the user should be able to quickly and easily
            identify the organization and see that it is legitimate.

        -   When the user is being asked to digitally sign a contract, the
            user should be able to quickly identify the who the requester is
            and determine that they are legitimate

        -   The user should be able to proactively send a verification
            request to an organization (or another user) to determine that
            they are legitimate. The wallet may do this for the user
           automatically.

    -   The user should be able to see several levels of detail about the
        counterparty. For example:

        -   Level 1: a visual confirmation (green tick style) that the
            counterparty has been vouched for by some authority.

        -   Level 2: detail about the counterparty's identity, for example
            company name, registered address, company number.

        -   Level 3: detail about the vouching that has taken place e.g.
            digital signature matches, vouching organization process, Legal
            Entity Identifier details, legal and regulatory obligations the
            counterparty may have regarding revealing the shared
            information.

-   Counterparty Action Verification

    -   The user should be able to quickly and easily determine that the
        counterparty is allowed to ask what they are asking, and if it is a
        reasonable request

        -   Some data sharing transactions may be limited by regulation,
            restricting who is allowed to ask for what. This should be
            communicated to the user.

        -   The digital wallet should be able to automatically reject
            illegal requests. The digital wallet should support a rules
            engine, or similar, to determine that a specific request from a
            specific issuer is illegal in one specific jurisdiction and
            legal in another.

        -   The user should be able to determine that "Gerald's Corner Shop"
            is not a legitimate issuer of driving licenses, for example. The
            digital wallet should be able to determine that an issuer is
            both legitimate AND authorized to issue the type of credential
            being offered.

        -   The digital wallet should be able to alert the user when it
            detects oversharing.

### Counterparties Checklist

-----------------------------------------------------------------------
- [ ] The wallet informs the holder that the counterparty they are
      interacting with is who they say they are.

- [ ] The holder is able to access increasingly detailed information
      about a counterparty; e.g., a simple green tick, detail about the
      counterparty's identity, detail about the level of
      vouching/checking that has been carried out on the counterparty.

- [ ] The holder is able to quickly and easily determine that the
      counterparty is asking for or offering data that they are allowed
      to, and the request is reasonable given the context of the
      transaction.
      
-----------------------------------------------------------------------

## Audit

Digital wallets should provide the ability for participants in a digital
credential ecosystem to know what is happening in that ecosystem. It is
tightly linked with the Privacy and Legislation Compliance topics.

Audit requirements and Privacy requirements can and will clash. Care
will need to be taken to design a digital wallet that handles both in
the best way. The balance between user privacy and regulation is also an
important topic, even more so when multiple competing regulations may be
involved.

-   User Audit.

    -   The digital wallet user can see all the transactions that they have
        carried out with their digital wallet.

    -   Can these transactions be used as proof of activity e.g. proof of
        purchase?

    -   Can they delete their own transaction list in an unrecoverable way?

-   Governance and Operational Audit.

    -   Ecosystem governance bodies have tools that enable them to audit the
        correct operation of the ecosystem without harming the privacy of
        the ecosystem members (issuers, holders, verifiers)?

        -   For example, if a relying party is asking for more data than it
            is allowed to, can the governance body see proof of this to stop
            it happening again?

-   Legal Audit.

    -   The digital wallet may need to provide an activity log for one or
        more actions under legal authority.

    -   The digital wallet should satisfy local regulatory audit
        requirements; for example, legal authorities may have the right to
        examine the content and transaction history of a user's digital
        wallet as part of a criminal investigation in the same way as they
        can execute a search warrant to look at the contents of a person's
        filing cabinet.

    -   A legal authority may have the right to access the transaction
        history of an issuer/verifier and prove that a user interacted with
        them without looking at the user's digital wallet.

### Audit Checklist

-----------------------------------------------------------------------
- [ ] The holder is able to see all the transactions that they have
      carried out with their digital wallet.

- [ ] Wallet ecosystem governing bodies are able to audit the correct
      operation of the ecosystem, without harming the privacy of the
      ecosystem members (issuers, holders and verifiers).

- [ ] The wallet ecosystem satisfies audit requirements imposed by legal
      authorities in the wallet ecosystem\s operational
      jurisdiction(s).

-----------------------------------------------------------------------

## Accountability

Digital wallets are used to access services from Counterparties which
may be for nought if the responsible parties cannot ultimately be held
accountable. Like most Safe Digital Wallet categories, requirements for
accountability can be divided into: a) technical mechanisms (those that
can be implemented with hardware, software, and protocols) and, b)
governance mechanisms (those that must be implemented by humans
following prescribed laws, regulation, policies and/or rules, including
via [reputation systems](https://en.wikipedia.org/wiki/Reputation_system)).

### Checklist for Technical Accountability Mechanisms

These are functions of a digital wallet required to produce what a court
of law will consider [admissible evidence](https://en.wikipedia.org/wiki/Admissible_evidence)
of the actions of the relevant parties in the case of harm or damage
resulting from reliance on the wallet or its contents. Without such
evidence, it would be all but impossible to hold specific parties
accountable.

- The digital wallet should provide secure storage of cryptographic
  keys, credentials, and digital assets. If a defense lawyer can create
  reasonable doubt that the keys, credentials, or assets in a digital
  wallet were secure, it becomes very difficult to hold the relevant
  parties accountable since all of them have plausible deniability that
  they took the harmful action.

-  The digital wallet should be able to digitally sign credentials,
  messages and transactions. Only by applying a digital signature to
  each action taken by the relevant parties can that action be tied
  directly to the use of a particular digital wallet in a particular
  interaction.

- The digital wallet should produce a secure audit log of user and
  counterparty interactions and transactions. As described in the Audit
  category (above), only by keeping a history of all the digitally
  signed transactions will the wallet holder be able to produce evidence
  of the alleged harmful actions.

- The wallet should provide alerts for unsafe interactions. In
  addition to compiling evidence, a wallet designed with safety in mind
  can also implement "accountability by design" by designing the wallet
  software to alert either: a) the user, b) a governing body (such as a
  consumer protection agency), or c) both if the wallet detects
  anomalous behavior or a clear policy violation. This "thousand eyes"
  approach can be a highly effective deterrent for many bad behaviors
  and dark patterns online.

- The digital wallet should have integrated technical support for a
  [reputation system](https://en.wikipedia.org/wiki/Reputation_system).
  This is the necessary technical enablement for user-generated
  reputation (see #7 below).

### Checklist for Governance Accountability Mechanisms

While technical mechanisms can produce evidence or notification of
harmful actions, ultimate accountability resides in the ability to take
enforcement action when necessary. This can be supported by any
combination of the following governance mechanisms.

- The digital wallet should be certified, and if so, under specific
  certification programs, for specific assurance levels, under a
  specified trust mark(s). Many governance frameworks will specify
  certification requirements for digital wallets as well as for issuers
  and verifiers of specific digital credentials.

- The digital wallet should be conformant with relevant governmental
  regulations. Many types of digital harms are already covered by
  existing laws and regulations, including commercial codes, consumer
  protection laws, and data protection and privacy regulations.

- The digital wallet should be conformant with relevant governance
  frameworks (aka trust frameworks). Digital wallets, agents, and
  credentials can be issued, held, and verified under the policies of a
  [governance framework](https://docs.google.com/document/d/1fZByfuSOwszDRkE7ARQLeElSYmVznoOyJK4sxRvJpyM/edit#heading=h.2x05z0r097mn)
  published by the relevant [governing body](https://docs.google.com/document/d/1fZByfuSOwszDRkE7ARQLeElSYmVznoOyJK4sxRvJpyM/edit#heading=h.1wptecwzvuvz).
  Specifications, tools and models for digital governance frameworks are
  published by the [Trust Over IP (ToIP) Foundation](https://trustoverip.org/); best practices for
  digital trust frameworks are published by the [Open Identity Exchange](https://openidentityexchange.org/).

- The digital wallet should be audited for continued conformance. Most
  certification programs will require either periodic or on-demand
  audits of the wallet hardware and/or software, as well as audits of
  issuers and/or verifiers.

-  The digital wallet should support a dispute resolution mechanism.
  While legal enforcement is a court of last resort, many governance
  frameworks may specify more progressive, efficient, and less expensive
  [dispute resolution](https://en.wikipedia.org/wiki/Dispute_resolution)
  mechanisms.

- The digital wallet should be covered by one or more liability
  frameworks. Another important accountability topic addressed by
  governance frameworks is liability, i.e., how damages are assessed,
  allocated, and paid when a party is found to be in violation of a
  governance framework. Note: because of their ability to automate
  verifiable transactions, digital wallets may also enable their holders
  to engage in a unique new form of automated [class action](https://en.wikipedia.org/wiki/Class_action).
  Holders that have suffered specific harm could give consent via their
  digital wallets to: a) join the class action lawsuit, and b)
  automatically send the necessary evidence to the class action
  litigator. This could be a particularly powerful deterrent to bad
  actors.

- The digital wallet should support a [reputation system](https://en.wikipedia.org/wiki/Reputation_system).
  The reputation system should cover the safety features of the wallet
  itself. Reputation systems are user-generated accountability
  mechanisms that do not require trusted third parties (other than to
  design, implement, and prevent gaming of the reputation system).

### Accountability Checklist

-----------------------------------------------------------------------
- [ ] The wallet provides secure storage of cryptographic keys,
      credentials, and digital assets so as to meet the requirements for
      admissible evidence.

- [ ] The wallet securely signs credentials, messages and transactions.

- [ ] The wallet produces a secure audit log of user and counterparty
      interactions and transactions.

- [ ] The wallet provides alerts for unsafe interactions.

- [ ] The wallet is certified under one or more certification programs
      for specific assurance levels under a specified trust mark(s).

- [ ] The wallet is conformant with relevant governmental regulations.

- [ ] The wallet is audited for continued conformance.

- [ ] The wallet supports a dispute resolution mechanism.

- [ ] The wallet is covered by one or more liability frameworks.

- [ ] The wallet has integrated support for a reputation system.

-----------------------------------------------------------------------


[^1]: Decoupling is not a digital wallet specific vulnerability but the
    authors felt it imperative to call it out in context of digital
    wallet usage

[^2]: [https://digital-strategy.ec.europa.eu/en/policies/eudi-wallet-toolbox](https://digital-strategy.ec.europa.eu/en/policies/eudi-wallet-toolbox)

[^3]: <https://diacc.ca/wp-content/uploads/2023/04/PCTF-Digital-Wallet_Conformance-Profile-Final-Recommendation-V1.0.pdf>

[^4]: Note related ongoing work on ISO/IEC 23220-5

[^5]: https://pages.nist.gov/800-63-3/sp800-63b.html

[^6]: <https://diacc.ca/wp-content/uploads/2023/04/PCTF-Digital-Wallet_Conformance-Profile-Final-Recommendation-V1.0.pdf>

[^7]: [https://www.icao.int/security/mrtd/downloads/technical%20reports/icao_mrtd_history_of_interoperability.pdf](https://www.icao.int/security/mrtd/downloads/technical%20reports/icao_mrtd_history_of_interoperability.pdf)

[^8]: <https://www.europarl.europa.eu/doceo/document/TA-9-2024-0117_EN.pdf>

[^9]: <https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX:32015R1502&from=en>

[^10]: <https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX:32015R1502>

[^11]: <https://nvlpubs.nist.gov/nistpubs/specialpublications/nist.sp.800-63a.pdf>
