## DRAFT NIST Special Publication 800-63B

# Subscriber Authentication

Paul A. Grassi  
Elaine M. Newton  
Ray A. Perlner  
William E. Burr  
James L. Fenton  

![](../sp800-63-3/media/nist_logo.png)

## DRAFT NIST Special Publication 800-63B

# Subscriber Authentication

Paul A. Grassi  
*Applied Cybersecurity Division  
Information Technology Laboratory*

Elaine M. Newton  
*Information Technology Laboratory*

Ray A. Perlner  
*Computer Security Division  
Information Technology Laboratory*

William E. Burr  
*Dakota Consulting, Inc.  
Silver Spring, MD*

James L. Fenton  
*TBD*

MonthTBD 2016

![](../sp800-63-3/media/commerce_logo.png)

U.S. Department of Commerce  
*Penny Pritzker, Secretary*

National Institute of Standards and Technology  
*Willie E. May, Under Secretary of Commerce for Standards and
Technology and Director*

### Authority

This publication has been developed by NIST to further its statutory
responsibilities under the Federal Information Security Management Act
(FISMA), Public Law (P.L.) 107-347. NIST is responsible for developing
information security standards and guidelines, including minimum
requirements for Federal information systems, but such standards and
guidelines shall not apply to national security systems without the
express approval of appropriate Federal officials exercising policy
authority over such systems. This guideline is consistent with the information security
requirements of Office of Management and Budget (OMB) Circular
A-130.

Nothing in this publication should be taken to contradict the standards
and guidelines made mandatory and binding on Federal agencies by the
Secretary of Commerce under statutory authority. Nor should these
guidelines be interpreted as altering or superseding the existing
authorities of the Secretary of Commerce, Director of the OMB, or any
other Federal official. This publication may be used by nongovernmental
organizations on a voluntary basis and is not subject to copyright in
the United States. Attribution would, however, be appreciated by NIST.

National Institute of Standards and Technology Special Publication
800-63-3  
Natl. Inst. Stand. Technol. Spec. Publ. 800-63B, xxx pages (MonthTBD
2016)  
CODEN: NSPUE2

**Comments on this publication may be submitted to:**

National Institute of Standards and Technology  
Attn: Computer Security Division, Information Technology Laboratory  
100 Bureau Drive (Mail Stop 8930) Gaithersburg, MD 20899-8930  
Email: <eauth-comments@nist.gov>


### Reports on Computer Systems Technology

The Information Technology Laboratory (ITL) at the National Institute of
Standards and Technology (NIST) promotes the U.S. economy and public
welfare by providing technical leadership for the Nation’s measurement
and standards infrastructure. ITL develops tests, test methods,
reference data, proof of concept implementations, and technical analyses
to advance the development and productive use of information technology.
ITL’s responsibilities include the development of management,
administrative, technical, and physical standards and guidelines for the
cost-effective security and privacy of other than national
security-related information in Federal information systems. The Special
Publication 800-series reports on ITL’s research, guidelines, and
outreach efforts in information system security, and its collaborative
activities with industry, government, and academic organizations.

###Requirements Notation and Conventions
The terms “SHALL” and “SHALL NOT” indicate requirements to be followed strictly in order to conform to the publication and from which no deviation is permitted.
 
The terms “SHOULD” and “SHOULD NOT” indicate that among several possibilities one is recommended as particularly suitable, without mentioning or excluding others, or that a certain course of action is preferred but not necessarily required, or that (in the negative form) a certain possibility or course of action is discouraged but not prohibited.
 
The terms “MAY” and “NEED NOT” indicate a course of action permissible within the limits of the publication.
 
The terms “CAN” and “CANNOT” indicate a possibility and capability, whether material, physical or causal.

### Abstract

This document provides technical guidelines for Federal agencies
implementing electronic authentication to implement effective identity proofing processes based on risk. The
recommendation covers remote authentication of users (such as employees,
contractors, or private individuals) interacting with government IT
systems over open networks. It defines technical requirements for each
of the three identity assurance levels. This publication supersedes NIST SP 800-63-1 and SP 800-63-2.

### Keywords

authentication; credential service provider;
electronic authentication; electronic credentials; identity proofing; PKI.

### Acknowledgements
* UK
* Canada
* 
   

### Executive Summary
> tbd - below is old stuff

Electronic authentication (e-authentication) is the process of
establishing confidence in user identities electronically presented to
an information system. E-authentication presents a technical challenge
when this process involves the remote authentication of individual
people over an open network, for the purpose of electronic government
and commerce. The guidelines in this and accompanying documents assume the authentication
and transaction take place across an open network such as the Internet.
In cases where the authentication and transaction take place over a
controlled network, agencies may take these security controls into
account as part of their risk assessment.

This recommendation provides technical guidelines to agencies to allow
an individual to remotely authenticate his or her identity to a Federal
IT system. This document may inform but does not restrict or constrain
the development or use of standards for application outside of the
Federal government, such as e-commerce transactions. These guidelines
address only traditional, widely implemented methods for remote
authentication based on secrets. With these methods, the individual to
be authenticated proves that he or she knows or possesses some secret
information.

These technical guidelines supplement OMB guidance, *E-Authentication
Guidance for Federal Agencies* \[[OMB M-04-04](#OMB_0404)\] and
supersede NIST SP 800-63-1 and SP 800-63-2. OMB M-04-04 defines four levels of
assurance, Levels 1 to 4, in terms of the consequences of authentication
errors and misuse of credentials. Level 1 is the lowest assurance level,
and Level 4 is the highest. The OMB guidance defines the required level
of authentication assurance in terms of the likely consequences of an
authentication error. As the consequences of an authentication error
become more serious, the required level of assurance increases. The OMB
guidance provides agencies with the criteria for determining the level
of e-authentication assurance required for specific applications and
transactions, based on the risks and their likelihood of occurrence of
each application or transaction.

OMB guidance outlines a five-step process by which agencies should meet
their e-authentication assurance requirements:

1.  Conduct a risk assessment of the government system.

2.  Map identified risks to the appropriate assurance level.

3.  Select technology based on e-authentication technical guidance.

4.  Validate that the implemented system has met the required
    assurance level.

5.  Periodically reassess the information system to determine technology
    refresh requirements.

This document provides guidelines for implementing the third step of the
above process.

This document takes a different approach than earlier revisions by defining two separate metrics, referred to as *Authenticator Assurance Level* and *Identity Assurance Level*. Authenticator Assurance Level refers to the robustness of the authentication process itself, while Identity Assurance Level refers to the robustness of the identity proofing process and the binding between an authenticator and a specific individual. A mapping is provided to allow agencies using the existing Level of Assurance model to select appropriate technology based on the corresponding Authenticator and Identity Assurance Levels. The separation of these metrics better supports applications requiring strong authentication that may be pseudonymous, and the separation of authenticator issuance from the establishment of credentials binding those authenticators to individuals.

Accordingly, with this revision SP 800-63 has been split into a family of documents organized as follows:

- SP 800-63-3 *Electronic Authentication Guideline* - Provides guidance on general authentication issues and for using authenticators, credentials, and assertions together in an information system.

- SP 800-63A *Enrollment and Identity Proofing* - Deals with the processes by which a credential, and authenticator(s) associated with that credential can be bound to a specific individual. This typically happens when that individual is enrolled in an identity system, through the identity proofing process.

- SP 800-63B *Subscriber Authentication* - provides guidance on the selection, use, and management of authenticators (formerly called *tokens*) to authenticate a remote subscriber to an identity system at specified levels of authenticator assurance.

- SP 800-63C *Authentication-based Assertions* - Provides guidance on the use of assertions to convey the results of authentication processes to a relying party.

It is anticipated that SP 800-63A, SP 800-63B, and SP 800-63C will be revised asynchronously with each other and with this document. The latest revision of each should be used for guidance.

After completing a risk assessment and mapping the
identified risks to the required assurance level, agencies can select
appropriate technology that, at a minimum, meets the technical
requirements for the required level of assurance. In particular, the
documents state specific technical requirements for each of the
levels of assurance in the following areas:

-   Identity proofing and registration of Applicants (covered in SP 800-63A)

-   Credential lifecycle and management mechanisms (covered in SP 800-63A)

-   Authenticators (typically a cryptographic key or password) for
    authentication (covered in SP 800-63B)
    
-	Authenticator lifecycle and management mechanisms (covered in SP 800-63B)

-   Protocols used to support the authentication mechanism between the
    Claimant and the Verifier (covered in SP 800-63B)

-   Assertion mechanisms used to communicate the results of a remote
    authentication if these results are sent to other parties (covered
    in SP 800-63C).

The following table shows the mapping between Level of Assurance and corresponding Authenticator/Identity Assurance Levels:

| Level of Assurance | Authenticator Assurance Level | Identity Assurance Level |
|:------------------:|:-----------------:|:-------------------:|
| 1 | 1 | 1 |
| 2 (pseudonymous) | 1 | 1 |
| 2 (non-pseudonymous) | 1 | 2 |
| 3 | 2 | 2 |
| 4 | 3 | 3 |



A summary of the technical requirements for each of the authenticator and identity assurance levels is provided below.

*** Do we need to repeat the authenticator levels here? ***

**Authenticator Assurance Level 1** - Authenticator Assurance Level 1 (AAL 1) provides single factor remote network authentication, giving some assurance that the same Claimant who participated in previous transactions is accessing the protected transaction or data. Authenticator Assurance Level 1 allows a wide range of available authentication technologies to be employed and requires only a single authentication factor to be used. It also permits the use of any of the authentication methods of Authenticator Assurance Levels 2 or 3. Successful authentication requires that the Claimant prove through a secure authentication protocol that he or she possesses and controls the authenticator.



**Authenticator Assurance Level 2** – Authenticator Assurance Level 2 (AAL 2) provides higher assurance that the same Claimant who participated in previous transactions is accessing the protected transaction or data. At least two different authentication factors are required. Various types of authenticators, including multi-factor Software Cryptographic Authenticators, may be used as described in SP 800-63A. Authenticator Assurance Level 2 also permits any of the authentication methods of Authenticator Assurance Level 3. AAL 2 authentication requires cryptographic strength mechanisms that protect the primary authenticator against compromise by the protocol threats for all threats at Authenticator Assurance Level 1 as well as verifier impersonation attacks. Approved cryptographic techniques are required for all assertion protocols used at Authenticator Assurance Level 2 and above.

Authentication requires that the Claimant prove, through a secure authentication protocol, that he or she controls the authenticator. The Claimant unlocks the authenticator with a password or biometric, or uses a secure multi-authenticator authentication protocol to establish two-factor authentication (through proof of possession of a physical or software authenticator in combination with some memorized secret knowledge). Long-term shared authentication secrets, if used, are never revealed to any party except, at issuance, to the Claimant; however, session (temporary) shared secrets may be provided to independent Verifiers by the CSP.

**Authenticator Assurance Level 3** – Authenticator Assurance Level 3 is intended to provide the highest practical remote network authentication assurance. Authentication at Authenticator Assurance Level 3 is based on proof of possession of a key through a cryptographic protocol. Authenticator Assurance Level 3 is similar to Authenticator Assurance Level 2 except that only “hard” cryptographic authenticators are allowed. The authenticator is required to be a hardware cryptographic module validated at Federal Information Processing Standard (FIPS) 140-2 Level 2 or higher overall with at least FIPS 140-2 Level 3 physical security. Level 4 authenticator requirements can be met by using the PIV authentication key of a FIPS 201 compliant Personal Identity Verification (PIV) Card.

Authenticator Assurance Level 3 requires strong cryptographic authentication of all communicating parties and all sensitive data transfers between the parties. Either public key or symmetric key technology may be used. Authentication requires that the Claimant prove through a secure authentication protocol that he or she controls the authenticator. All protocol threats at Authenticator Assurance Level 2 must be prevented at Authenticator Assurance Level 3. Protocols shall also be strongly resistant to man-in-the-middle attacks. Long-term shared authentication secrets, if used, are never revealed to any party except the Claimant and Verifiers operated directly by the CSP; however, session (temporary) shared secrets may be provided to independent Verifiers by the CSP. Approved cryptographic techniques are used for all operations. All sensitive data transfers are cryptographically authenticated using keys bound to the authentication process.

At Authenticator Assurance Level 3, “bearer” assertions (as defined in SP 800-63C) are not used to establish the identity of the Claimant to the Relying Party (RP) other than on a very short-term basis to maintain the continuity of a session. “Holder-of-key” assertions (as defined in SP 800-63C) may be used, provided that the assertion contains a reference to a key that is possessed by the Subscriber and is cryptographically linked to the Authenticator Assurance Level 3 authenticator used to authenticate to the Verifier. The RP should maintain records of the assertions it receives, to support detection of a compromised verifier impersonating the subscriber.

**Identity Assurance Level 1** – At this level, attributes provided in conjunction with the authentication process, if any, are self-asserted. They may be used by the relying party but must not be depended upon in making authorization decisions. 
 