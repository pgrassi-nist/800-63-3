# DRAFT NIST Special Publication 800-63
## Revision 3

# Digital Authentication Guideline

Paul Grassi  
William E. Burr  
James L. Fenton







This publication is available free of charge from:
![](media/csd.png)
![](media/nist_logo.png)

# DRAFT NIST Special Publication 800-63-3
# Revision 3

# Digital Authentication Guideline

Paul A. Grassi  
*Applied Cybersecurity Division  
Information Technology Laboratory*

William E. Burr  
*Dakota Consulting, Inc.  
Silver Spring, MD*

James L. Fenton  
*Independent Consultant*

This publication is available free of charge from:

Month TBD 2016

![](media/commerce_logo.png)

U.S. Department of Commerce  
*Penny Pritzker, Secretary*

National Institute of Standards and Technology  
*Willie E. May, Under Secretary of Commerce for Standards and
Technology and Director*

### Authority

This publication has been developed by NIST in accordance with its statutory responsibilities under the Federal Information Security Modernization Act (FISMA) of 2014, 44 U.S.C. § 3541 et seq., Public Law  (P.L.) 113-283. NIST is responsible for developing information security standards and guidelines, including minimum requirements for federal information systems, but such standards and guidelines shall not apply to national security systems without the express approval of appropriate federal officials exercising policy authority over such systems. This guideline is consistent with the requirements of the Office of Management and Budget (OMB) Circular A-130.

Nothing in this publication should be taken to contradict the standards and guidelines made mandatory and binding on Federal agencies by the Secretary of Commerce under statutory authority. Nor should these guidelines be interpreted as altering or superseding the existing authorities of the Secretary of Commerce, Director of the OMB, or any other Federal official. This publication may be used by nongovernmental organizations on a voluntary basis and is not subject to copyright in the United States. Attribution would, however, be appreciated by NIST.

<center>
National Institute of Standards and Technology Special Publication
800-63-3  
Natl. Inst. Stand. Technol. Spec. Publ. 800-63-3, xxx pages (MonthTBD
2016)  
CODEN: NSPUE2

This publication is available free of charge from:

**Comments on this publication may be submitted to:
Public comment period: Month Day, YYYY through Month Day, YYYY**
All comments are subject to release under the Freedom of Information Act (FOIA).

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

### Abstract

This document and its companion documents, SP 800-63-3, SP 800-63B, and SP 800-63C, provide technical and procedural guidelines to agencies for the implementation of identity proofing. This document focuses on the enrollment and verification of an identity for for use in digital authentication. Central to this is a process known as *identity proofing* in which an applicant provides evidence to a credential service provider (CSP) reliably identifying themselves, thereby allowing the CSP to assert that identification at a useful identity assurance level. This document defines technical requirements for each of three identity assurance levels. This publication supersedes corresponding sections of NIST SP 800-63-1 and SP 800-63-2.

### Keywords

authentication; credential service provider; electronic authentication; digital authentication; electronic credentials; digital credentials; identity proofing.



### Acknowledgements
The authors would like to acknowledge the contributions and guidance of our international peers, including Adam Cooper, Alastair Treharne, and Julian White from the Cabinet Office, United Kingdom, and Tim Bouma from the Treasury Board of Canada Secretariat, Government of Canada. 

The authors would also like to acknowledge the thought leadership and innovation of the original authors: Donna F. Dodson, Elaine M. Newton, Ray A. Perlner, W. Timothy Polk, Sarbari Gupta, and Emad A. Nabbus.  Without their tireless efforts, we would not have had the incredible baseline by which to evolve 800-63 to the document it is today. 

###Audience  
###Requirements Notation and Conventions
The terms “shall” and “shall not” indicate requirements to be followed strictly in order to conform to the publication and from which no deviation is permitted.
 
The terms “should” and “should not” indicate that among several possibilities one is recommended as particularly suitable, without mentioning or excluding others, or that a certain course of action is preferred but not necessarily required, or that (in the negative form) a certain possibility or course of action is discouraged but not prohibited.
 
The terms “may” and “need not” indicate a course of action permissible within the limits of the publication.
 
The terms “can” and “cannot” indicate a possibility and capability, whether material, physical or causal.

</center>






## Executive Summary

Identity Assurance Level (IAL) refers to the robustness of the identity proofing process and the binding between an authenticator and a specific individual. The separation of IAL from Authenticator Assurance Level (AAL) better supports applications requiring strong authentication that may be pseudonymous, and the separation of authenticator issuance from the establishment of credentials binding those authenticators to individuals.

This guideline deals with how an individual, known as an applicant, can prove their identity to a Credential Service Provider (CSP) and become enrolled as a valid identity.

The three (3) IALs reflect the options agencies may select based on their risk profile and the potential harm caused by an invalid or fraudulent identity accessing their systems.  The IALs are as follows:


**IAL 1**:
At this level, there is no requirement for a applicants identity to be proven.  Any attributes provided in conjunction with the authentication process are self-asserted. 
**IAL 2**:
At IAL 2, the claimed identity is proven with evidence that supports the real world existence of the claimed identity and identifies and verifies the person to whom the claimed identity belongs.  IAL 2 introduces the need for either remote or in-person identity proofing.  Attributes MAY be asserted by CSPs to RPs in support of pseudonymous identity with verified attributes. 
**IAL 3**:
At Identity Assurance Level 3, in-person identity proofing is required. Identifying attributes must be verified by an authorized and trained representative of the CSP. As with IAL 2, attributes MAY be asserted by CSPs to RPs in support of pseudonymous identity with verified attributes. 

A mapping is provided below to allow agencies using the existing Level of Assurance model, specified in OMB Memorandum [M-04-04](sec_references.md/#M-04-04), to select appropriate technology and process based on the selected IAL.

| Level of Assurance |  Identity Assurance Level |
|:------------------:|:------------------------:|
| 1 | 1 |
| 2 (pseudonymous) |  1 |
| 2 (non-pseudonymous) |  2 |
| 3 | 2 |
| 4 | 3 |

## Table of Contents
[1. Purpose and Introduction](sec1_2_introduction.md)

[2. Definitions and Abbreviations](sec3_definitions.md)

[3. Identity Assurance Levels](sec4_ial.md)

[4. Identity Proofing Requirements](sec5_proofing.md)

[5. Threats and Security Considerations](sec7_security.md)

[6. Privacy Considerations](privacy.md)

[7. Usability Considerations](sec_usability.md)

[8. References](sec_references.md)

 