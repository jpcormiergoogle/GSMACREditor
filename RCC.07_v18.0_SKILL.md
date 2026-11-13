---
name: rcc-07-v18-0-cr-review
description: >-
  Reviews GSMA PRD RCC.07 v18.0 Change Requests (CRs) for filename format,
  active voice, UK English spelling, double spaces, and terminology/capitalisation consistency.
---

# RCC.07 v18.0 Change Request Review Skill

## Preamble

I am editing GSMA standard **RCC.07 v18.0** and have drafted a Change Request (CR) to this specification. Please review my changes against the following rules:

1. **Filename Format**: Check that the suffix of the filename of this CR matches the format `<CR number, e.g. 2026_CR05>R<Revision Number, e.g. 3>-<Target PRD, e.g. RCC.07>-<CR Title>.docx` and contains no spaces.
2. **Active Voice**: Ensure the added text (with changemarks) does not use passive voice. The subject shall perform the action.
3. **UK English Spelling**: Check that no US English spelling is used in this document; only UK English spelling shall be used.
4. **Spacing**: Check for and highlight any double spaces.
5. **Terminology & Capitalisation**: Compare the terms used in my changes against the table of terms below and highlight any terms that are not properly capitalised or spelled correctly so that the changes remain consistent with the document. Note that the CR may introduce new definitions and terms, so take those into account as well.

## Table of Terms

| Term | Description |
| :--- | :--- |
| 2G | 2nd Generation of Global System for Mobile Communications (GSM) |
| 5GC | 5G Core |
| 5GS | 5G System |
| ABNF | Augmented Backus–Naur Form |
| ACK | Acknowledgement |
| ACS | Auto-Configuration Server |
| AF | Anonymization Function |
| ALG | Application Layer Gateway |
| AMR | Adaptive Multi-Rate |
| APN | Access Point Name |
| AP | Authentication Proxy |
| API | Application Programming Interface |
| AS | Application Server |
| AuC | Authentication Centre |
| BA | Broadband Access |
| B2BUA | Back-to-Back User Agent |
| bool | Boolean |
| bps | Bits per second (used with Mbps: Mega-, kbps: kilo-) |
| BSF | Bootstrapped Security Function |
| B-TID | Bootstrapping Transaction Identifier |
| CAB | Converged Address Book |
| CFS | Client Fallback to SMS |
| Chatbot | See [GSMA PRD-RCC.71] |
| Chatbot Information | Meta information on a Chatbot, amongst others a description and contact information |
| Chatbot Information Function | A function providing meta information on a Chatbot. The provided information will include amongst others a description and contact information |
| Chatbot Platform | See [GSMA PRD-RCC.71] |
| CMS | Common Message Store |
| CPIM | Common Profile for Instant Messaging |
| CPM | Converged IP Messaging |
| CRLF | Carriage Return Line Feed |
| CS | Circuit Switched |
| CSS | Cascading Style Sheets |
| DER | Distinguished Encoding Rules (defined in ITU-T X.690) |
| DNS | Domain Name System |
| DNS SRV | Domain Name System Service record |
| DRX | Discontinuous Reception |
| DTM | Dual Transfer Mode |
| DTX | Discontinuous Transmission |
| e2ae | end-to-access edge |
| e2e | end-to-end |
| E2EE | End-to-End Encryption |
| eIMS-AGW | Enhanced IP Multimedia Subsystem-Access GateWay |
| eP-CSCF | Enhanced Proxy-Call Session Control Function |
| EPSG | European Petroleum Survey Group |
| EUCR | End User Confirmation Request |
| FIFO | First IN First Out |
| FIR | Full Intra Request |
| Foreign User Profile Server | A User Profile Server that the client is communicating with through their Home Profile Server. |
| FQDN | Fully Qualified Domain Name |
| FTTH | Fibre To The Home |
| GAA | Generic Authentication Architecture |
| GBA | Generic Bootstrapping Architecture |
| GBR | Guaranteed Bitrate |
| GML | Geography Markup Language |
| GPRS | General Packet Radio Service |
| Group Chat Session Identity | Public Service Identity assigned to a Group Chat. It is assigned by the Messaging Server and used by the client for addressing the Messaging Server. |
| GRUU | Globally Routable User agent URI |
| GSM | Global System for Mobile Communications |
| GSMA | GSM Association |
| GSO | Group State Object |
| Home User Profile Server | A User Profile Server that the client is directly communicating with. |
| HOS | Home Operator Services |
| HPLMN | Home Public Land Mobile Network |
| HPSI | Home Profile Server Interface, proprietary interface that the RCS Client uses to share and fetch shared User Profiles from the Home User Profile Server |
| HSPA | High Speed Packet Access |
| HTTP | Hyper-Text Transfer Protocol<br>NOTE: This specification uses the term “HTTP POST” and “HTTP GET” as a generic reference to the action of using the POST or GET methods of HTTP. Whether for a particular request HTTP or HTTPS is used depends on the scheme specified in the definition of that request. |
| HTTPS | Hyper-Text Transfer Protocol Secure |
| HW | HardWare |
| IARI | IMS Application Reference Identifier |
| I-CSCF | Interworking Call Session Control Function |
| ICSI | IMS Communication Service Identifier |
| ID | IDentifier |
| IEI | Information Element Identifier |
| IETF | Internet Engineering Task Force |
| IFC | initial Filter Criteria |
| IM | Instant Messaging. The term chat is also applied in this document to the same concept. |
| IMDN | Instant Message Disposition Notification |
| IMEI | International Mobile Station Equipment Identity |
| IMPI | Internet Protocol Multimedia Subsystem Private Identity |
| IMPU | Internet Protocol Multimedia Subsystem PUblic identity |
| IMS | Internet Protocol Multimedia Subsystem |
| IMS AKA | IMS Authentication and Key Agreement |
| Int | Integer |
| IP | Internet Protocol |
| IPsec | Internet Protocol Security |
| IPSI | Inter-Profile Server Interface, interface used by the Foreign and Home User Profile Server to exchange profiles. |
| IP-SM-GW | Internet Protocol Short Message Gateway |
| IPX | Internet Protocol Packet eXchange |
| ISIM | Internet Protocol Multimedia Services SIM |
| ISF | Interworking Selection Function |
| IWF | InterWorking Function |
| JSON | JavaScript Object Notation |
| JWK | JSON Web Key |
| JWS | JSON Web Signature |
| KB | KiloByte (i.e. 1024 bytes) |
| kB | Kilobyte 1 kilobyte = 10³ bytes = 1000 bytes. |
| KDS | Key Distribution Service |
| LSB | Least Significant Bit |
| LTE | Long Term Evolution |
| MaaP | Messaging as a Platform |
| MAP | Mobile Application Part |
| Messaging Server | A server providing support for the standalone messaging service (see section 3.2.2) and/or Chat and Group Chat (see sections 3.2.3 and 3.2.4) according to [GSMA PRD-RCC.11] |
| MIME | Multipurpose Internet Mail Extensions |
| MIVC | Messaging-Initiated Video Call. See [GSMA PRD-RCC.71] |
| MMS | Multimedia Message Service |
| MMS-C | Multimedia Messaging Service Centre |
| MMTEL | MultiMedia TELephony |
| MNO | Mobile Network Operator |
| MO | Management Object |
| MSB | Most Significant Bit |
| MSISDN | Mobile Subscriber Integrated Services Digital Network Number |
| MSRP | Message Session Relay Protocol |
| MSRPoTLS | Message Session Relay Protocol over Transport Layer Security |
| Multimedia Telephony | Voice or Video Calling following [GSMA PRD-IR.92], [GSMA PRD-IR.94], [GSMA PRD-IR.51] or [GSMA PRD-NG.114] depending on the used access and packet core network |
| NAL | Network Abstraction Layer |
| NAT | Network Address Translation |
| NFS | Network Fallback to SMS |
| NGBR | Non-Guaranteed Bitrate |
| NNI | Network Interface |
| NR | New Radio |
| NW | NetWork |
| OEM | Original Equipment Manufacturer |
| OMA | Open Mobile Alliance |
| OS | Operating System |
| P-CSCF | Proxy-Call Session Control Function |
| PC | Personal Computer |
| PCC | Personal Contact Card |
| PDP | Packet Data Protocol |
| PIDF | Presence Information Data Format |
| PKI | Public Key Infrastructure |
| POSIX | Portable Operating System Interface |
| PPS | Picture Parameter Set |
| PRD | Permanent Reference Document |
| PS | Packet Switched |
| Push Controlled Idle State | A state of the RCS client where the client is waiting for Push Notification |
| Push Notification | A notification to the RCS client, when not connected to the RCS Service Provider, that a new incoming communication event (e.g. new Chat Message, File Transfer, Audio Message, Message or File Transfer Status / State notifications) is available for the user. The Push Notification is sent by the RCS Service Provider to wake up the RCS client for establishing a connection to the RCS Service Provider for the new incoming communication event. |
| Push Notification Mechanism | A mechanism that enables the RCS Service Provider to enable non-persistent connections between the RCS Service Provider and the RCS client (in contrast to the mechanism that uses persistent connections) for communication event delivery. The mechanism is not visible to the user. |
| Push Service Provider | An entity which provides Push Notification Mechanism to the RCS client. |
| QCI | Quality of Service Class Identifier |
| QoS | Quality of Service |
| RCS | Rich Communication Suite |
| RCS User | An end user that has device or client (and the corresponding Service Provider subscription) supporting the RCS Capability Discovery framework and at least one of the services defined in the current specification. |
| RCS Video Chat | A WebRTC [RFC8825] implementation of MIVC |
| RFC | Request For Comments |
| RLC | Radio Link Control |
| RLS | Resource List Server |
| RRAM | RCS Recorded Audio Message |
| RTCP | Real-time Transport Control Protocol |
| RTP | Real-time Transport Protocol |
| SBC | Session Border Controller |
| S-CSCF | Serving Call Session Control Function |
| SDP | Session Description Protocol |
| SGs interface | 3GPP defined reference point between the Mobility Management Entity and the Mobile Switching Centre |
| SIM | Subscriber Identity Module |
| SIMPLE | Session Initiation Protocol for Instant Messaging and Presence Leveraging Extensions |
| SIO | Session Info Object |
| SIP | Session Initiation Protocol |
| SIPoTLS | Session Initiation Protocol over Transport Layer Security |
| SMPP | Short Message Peer-to-Peer |
| SMS | Short Message Service |
| SMS-C | Short Message Service Centre |
| SMSoIP | Short Message Service over Internet Protocol |
| SP | Service Provider |
| SPN | Service Provider Network |
| SFU | Selective Forwarding Unit |
| SSO | Single Sign On |
| STUN | Simple Traversal of User Datagram Protocol through Network Address Translations |
| Suggested Chip List | See [GSMA PRD-RCC.71] |
| SUPL | Secure User Plane Location |
| TCP | Transmission Control Protocol |
| tel URI | telephone Uniform Resource Identifier |
| TID | Transaction IDentifier |
| TLS | Transport Layer Security |
| TON | Type Of Number |
| TPDU | Transfer Protocol Data Unit |
| Trust Store | A trusted repository for establishing the chain of trust when validating Root certificates and Certificate Authorities |
| UA | User Agent |
| UCS2 | 2-byte Universal Character Set |
| UDP | User Datagram Protocol |
| UE | User Equipment |
| UI | User Interface |
| UID | Unique IDentifier |
| UNI | User Network Interface |
| URI | Uniform Resource Identifier |
| URL | Uniform Resource Locator |
| User Profile | Personal information related to a user (e.g. name and picture). |
| User Profile Server | A server used for storing and retrieving User Profiles. |
| USIM | Universal Subscriber Identity Module |
| UTC | Coordinated Universal Time |
| UUID | Universally Unique IDentifier |
| UX | User Experience |
| vCard | A format for electronic business cards |
| Verification Authority | A provider of verification for Chatbots (as defined in [GSMA PRD-NG.131]) |
| VoLTE | Voice over Long Term Evolution |
| VoWiFi | Voice over EPC-integrated Wi-Fi as specified in [GSMA PRD-IR.51] |
| WebRTC | Web Real Time Communication |
| Wi-Fi | Trademark of Industry Consortium "Wi-Fi Alliance" used as synonym for WLAN (Wireless Local Area Network) |
| WLAN | Wireless Local Area Network |
| XML | Extensible Markup Language |
| xSIM | Generic reference to different types of SIMs (e.g. USIM, ISIM, etc.) |
