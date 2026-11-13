---
name: rcc-16-v4-0-cr-review
description: >-
  Reviews GSMA PRD RCC.16 v4.0 Change Requests (CRs) for filename format,
  active voice, UK English spelling, double spaces, and terminology/capitalisation consistency.
---

# RCC.16 v4.0 Change Request Review Skill

## Preamble

I am editing GSMA standard **RCC.16 v4.0** and have drafted a Change Request (CR) to this specification. Please review my changes against the following rules:

1. **Filename Format**: Check that the suffix of the filename of this CR matches the format `<CR number, e.g. 2026_CR05>R<Revision Number, e.g. 3>-<Target PRD, e.g. RCC.16>-<CR Title>.docx` and contains no spaces.
2. **Active Voice**: Ensure the added text (with changemarks) does not use passive voice. The subject shall perform the action.
3. **UK English Spelling**: Check that no US English spelling is used in this document; only UK English spelling shall be used.
4. **Spacing**: Check for and highlight any double spaces.
5. **Terminology & Capitalisation**: Compare the terms used in my changes against the tables of terms and abbreviations below and highlight any terms that are not properly capitalised or spelled correctly so that the changes remain consistent with the document. Note that the CR may introduce new definitions and terms, so take those into account as well.

## Definition of Terms

| Term | Description |
| :--- | :--- |
| Active Conversation | A Conversation with at least one User Message in the last 30 days. |
| Additional Authenticated Data | Information that is not encrypted but is bound to the ciphertext in a cryptographic way, so that a modification of the information renders the ciphertext invalid. |
| Application Message | Message defined by the [GSMA PRD-RCC.07] unrelated to encryption. |
| Certificate Chain | An ordered list of certificates, from the root certificate to the leaf certificate. Each certificate is signed by its parent. |
| Cipher Suite | As defined in [RFC9420]. A Cipher Suite is a combination of a protocol version and the set of cryptographic algorithms that should be used. |
| Client | A logical device owned by a Participant; an agent that uses this protocol to establish a shared cryptographic state with other Clients. A Client is defined by the cryptographic keys it holds. |
| Client Certificate | An X.509 representation of the Client. The X.509 certificate is verified by the KDS. Asserts the Client & Participant’s identity in a given time window. |
| Client Credential | As defined in [RFC9420]. Each member of a group presents a credential that provides one identity for the member and associates them with the member's signing key. The identities and signing key are verified by the KDS in use. In RCS, the Client Credential contains a Client Certificate. |
| Commit | As defined in [RFC9420]. A message that implements the changes to the group proposed in a set of Proposals. |
| Control Message | Message defined by the MLS specification (e.g. Commit, Welcome). |
| Cryptographic State | The set of keys and other MLS state required to encrypt, decrypt and sign messages as well as create and verify Commits. |
| End-to-End Encryption (E2EE) | A private communication system in which only communicating users can participate. |
| Epoch | As defined in [RFC9420]. A state of a group in which a specific set of authenticated Clients hold shared cryptographic state. |
| Epoch Authenticator | A short cryptographic representation of the state of a given epoch. |
| Era | An identifier representing a version of the MLS Group within an RCS conversation. Each new Era creates a new MLS Group with the same Group Identifier. |
| External Commit | As defined in [RFC9420]. A Commit that is issued by a non-member of the cryptographic group. |
| External Proposal | As defined in [RFC9420]. A Proposal that is sent by a non-member of the group, particularly by the server hosting the group. |
| Foreign KDS | A KDS that a client is communicating with through their Home KDS. |
| Group Context | As defined in [RFC9420]. An object that summarises the shared, public state of the group. The GroupContext is typically distributed in a signed GroupInfo message, which is provided to new members to help them join a group. |
| Group Context Extensions | As defined in [RFC9420]. Additional application-level entries in GroupContext object. |
| Home KDS | A KDS that a client is directly communicating with. |
| Home KDS Interface | Interface between the client and their Home KDS. |
| Inter-KDS Interface | Interface between two KDSes that facilitates federation. |
| Key Delivery Service (KDS) | A server, provided by the application vendor, responsible for associating, holding, and distributing a user’s KeyPackage. |
| KeyPackage | As defined in [RFC9420]. A signed object describing a Client's identity and capabilities, including a hybrid public key encryption (HPKE) [RFC9180] public key that can be used to encrypt to that Client. Other clients can use a Client's KeyPackage to introduce the Client to a new group. |
| Last Resort KeyPackage | As defined in [RFC9420]. A reusable (by multiple members) KeyPackage. |
| Leaf Node | As defined in [RFC9420]. Leaf Node of the MLS Ratchet Tree that describes all the details of an individual Client's appearance in the MLS Group, signed by that Client. |
| MLS Control Message | A CPIM message containing either a Commit or a list of Proposals. |
| MLS Group | Represents a logical collection of Clients that share a common secret value at any given time. Its state is represented as a linear sequence of epochs in which each epoch depends on its predecessor. |
| MLS Message | A public or private message carrying MLS primitives (PublicMessage or PrivateMessage). |
| MLS (Ratchet) Tree | Represents a current state of an encryption in a given conversation and is used to distribute encryption keys to group members. |
| Participant | An entity identified by an RCS primary identifier that logically represents a single end user. |
| Plaintext Message | A message that is transmitted unencrypted. |
| Private-IM | An RCS Message sent to a single Participant of the Group. In 1-to-1 messaging, every message is considered a Private-IM. |
| PrivateMessage | As defined in [RFC9420]. An MLS protocol message that is signed by its sender, authenticated as coming from a member of the group in a particular epoch, and encrypted so that it is confidential to the members of the group in that epoch. |
| Proposal | As defined in [RFC9420]. A message that proposes a change to the group, e.g., adding or removing a member. |
| PublicMessage | As defined in [RFC9420]. An MLS protocol message that is signed by its sender and authenticated as coming from a member of the group in a particular epoch but not encrypted. |
| RCS Conversation | The RCS representation of 1-to-1 or group conversation, which includes all the Participants in that conversation. |
| Signed Encryption Identity Proof | A signature returned by ACS that proves ownership of MSISDN as well as the Participant Key and binds them together. |
| Unencrypted Singleton Era | An Era representing an MLS Group containing only the sending client as its sole member in a case of the client encountering an unrecoverable error. |
| UpdatePath | As defined in [RFC9420]. An MLS procedure to update nodes of the Ratchet Tree with new secrets. |
| User Message | A Message containing user content, such as text, files, audio, as opposed to Control Messages. |

## Abbreviations

| Term | Description |
| :--- | :--- |
| AAD | Additional Authenticated Data |
| ABNF | Augmented Backus-Naur Form |
| ACS | Auto-Configuration Server = Configuration Server as defined in [GSMA PRD-RCC.14] |
| AES-CTR | Advanced Encryption Standard using Counter Mode |
| CA | Certificate Authority |
| CLR | Certificate Revocation List |
| CPIM | Common Presence and Instant Messaging |
| CSPRNG | Cryptographically Secure Pseudorandom Number Generator |
| DBA | Doing Business As |
| E2EE | End-to-end encryption |
| ECDSA | Elliptical Curve Digital Signature Algorithm |
| FTD | Fail to decrypt |
| GUID | Globally Unique Identifier |
| HKDF | Hash Key Derivation Function |
| HKI | Home KDS Interface |
| HMAC | Hash-Based Message Authentication Code |
| HPKE | Hybrid Public Key Encryption |
| IKI | Inter-KDS Interface |
| IMDN | Instant Message Disposition Notification |
| KDS | Key Delivery Service |
| MIME | Multipurpose Internet Mail Extension |
| MLS | Messaging Layer Security |
| mTLS | Mutual Transport Layer Security |
| MSRP | Message Session Relay Protocol |
| NNI | Network Interface |
| NS | Name Space |
| NTP | Network Time Protocol |
| OID | Object Identifier |
| P2P | Person to Person (communication) |
| PRD | Permanent Reference Document |
| RPC | Remote Procedure Call |
| RCS | Rich Communication Suite |
| RCS SPN | RCS Service Provider Network |
| SIP | Session Initiation Protocol |
| SRTP | Secure Real-Time Transport Protocol |
| UNI | User Network Interface |
| URI | Uniform Resource Identifier |
| UUID | Universally Unique Identifier |
| URN | Uniform Resource Names |
| XML | Extensible Markup Language |
