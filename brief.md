Version: NAFATH-V1
Track: Cybersecurity 


## Overview

The NAFATH national digital login service will allow citizens to access multiple government services through one account using a website or mobile application. Software standards such as OAuth 2.0 and OpenID Connect support authorization and user authentication. Artificial intelligence can identify suspicious login patterns, but its use requires risk management, privacy safeguards, fairness, and ongoing monitoring. Mobile security depends on requesting only necessary Android permissions and explaining their purpose to users. Networking protections such as DNS over HTTPS can encrypt DNS queries, although they do not protect every aspect of online activity. Responsible data handling is also essential to protect citizens' personal information and meet applicable legal obligations. Together, these six IT fields support a secure and reliable government login service. Phishing-resistant authentication is essential to strengthening cybersecurity for this service.

## Software
OAuth 2.0 is an authorization framework that allows applications to obtain limited access to protected resources. OpenID Connect builds on OAuth 2.0 by adding an identity layer that enables applications to authenticate users and receive information about their identity. For NAFATH, OpenID Connect supports user sign-in, while OAuth 2.0 governs delegated access to resources. Understanding this distinction helps separate verifying a citizen's identity from deciding which services they can access.
Resource :RFC 6749 - The OAuth 2.0 Authorization Framework - https://www.rfc-editor.org/rfc/rfc6749

## AI
An AI model that flags suspicious logins can create risks such as false alerts, missed attacks, biased decisions, privacy violations, and unreliable predictions. The NIST AI Risk Management Framework provides guidance for identifying, assessing, and managing these risks. Before deployment, the authority should validate the model using representative data, evaluate performance across relevant user groups, protect login data, monitor outcomes, and provide human review and recovery procedures when legitimate citizens are incorrectly flagged.
Resource: NIST AI Risk Management Framework - https://www.nist.gov/itl/ai-risk-management-framework

## Mobile
Android uses a permission system to restrict an application's access to protected device features and data. Some permissions are granted automatically, while dangerous permissions generally require a runtime request on applicable Android versions. A government login application should request sensitive permissions only when necessary, explain their purpose clearly, and respect the user's decision. Minimizing permissions reduces unnecessary access to personal information and helps build trust in the national login service.
Resource: Request runtime permissions - Android Developers - https://developer.android.com/training/permissions

## Networking
DNS over HTTPS (DoH) sends DNS queries through HTTPS, encrypting the connection between a client and its chosen DNS resolver. This helps prevent observers on a local network from easily reading or modifying DNS queries in transit. However, DoH does not make all browsing activity anonymous, guarantee that the resolver is trustworthy, or replace HTTPS protection for website content. NAFATH should therefore use DoH as one network protection alongside secure web connections and other security controls.
Resource: RFC 8484 - DNS Queries over HTTPS (DoH) - https://www.rfc-editor.org/rfc/rfc8484

## Cybersecurity
from successfully reusing authentication credentials or responses on fraudulent websites. FIDO2/WebAuthn security keys and properly implemented passkeys can provide phishing resistance through cryptographic authentication bound to the legitimate website. In contrast, passwords, SMS codes, and ordinary authenticator-app codes can be captured or relayed through phishing attacks. NAFATH should prioritize authentication methods that meet applicable phishing-resistance requirements and provide secure account recovery for citizens.
Resource: NIST SP 800-63B - Digital Identity Guidelines - https://pages.nist.gov/800-63-4/sp800-63b.html

## Data 
Oman's Personal Data Protection Law, issued under Royal Decree 6/2022, establishes requirements for processing personal data. The authority should verify its applicable legal obligations concerning lawful processing, transparency, data-subject rights, security safeguards, and permitted disclosure. It should collect only data needed for legitimate purposes, restrict access to stored identity information, and establish appropriate retention and incident-handling procedures. The authority must verify the detailed requirements against the law and its implementing regulation before deploying the service.
Resource: Personal Data Protection Law - Ministry of Transport, Communications and Information Technology - https://www.mtcit.gov.om/

## Misconception in My Track
A common misconception is that enabling multi-factor authentication automatically makes a login service resistant to phishing. However, attackers can trick users into entering passwords and one-time codes into fraudulent websites or relay those codes to legitimate services. Phishing resistance depends on how the authentication method binds the authentication process to the legitimate service. FIDO2/WebAuthn methods can provide this protection when properly implemented. NIST's Digital Identity Guidelines discuss phishing resistance in the section addressing authentication protocols and phishing-resistant authenticators.

## Open Question
How can NAFATH implement phishing-resistant authentication while ensuring that citizens using older devices or requiring accessibility support can still access government services securely?
