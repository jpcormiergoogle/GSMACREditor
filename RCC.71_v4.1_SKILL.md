---
name: rcc-71-v4-1-cr-review
description: >-
  Reviews GSMA PRD RCC.71 v4.1 Change Requests (CRs) for filename format,
  active voice, UK English spelling, double spaces, and terminology/capitalisation consistency.
---

# RCC.71 v4.1 Change Request Review Skill

## Preamble

I am editing GSMA standard **RCC.71 v4.1** and have drafted a Change Request (CR) to this specification. Please review my changes against the following rules:

1. **Filename Format**: Check that the suffix of the filename of this CR matches the format `<CR number, e.g. 2026_CR05>R<Revision Number, e.g. 3>-<Target PRD, e.g. RCC.71>-<CR Title>.docx` and contains no spaces.
2. **Active Voice**: Ensure the added text (with changemarks) does not use passive voice. The subject shall perform the action.
3. **UK English Spelling**: Check that no US English spelling is used in this document; only UK English spelling shall be used.
4. **Spacing**: Check for and highlight any double spaces.
5. **Terminology & Capitalisation**: Compare the terms used in my changes against the table of terms below and highlight any terms that are not properly capitalised or spelled correctly so that the changes remain consistent with the document. Note that the CR may introduce new definitions and terms, so take those into account as well.

## Table of Terms

| Term | Description (contains technical and functional terms) |
| :--- | :--- |
| 3GPP | 3rd Generation Partnership Project |
| A2P | Application to Person (communication) |
| Active device or interface | A device or interface will be active for a conversation’s “session” if the user has either started a conversation, or sent events outside of a session from that device or responded to an incoming event with an event listed in R9-3-4 on that device/interface. A session is established and associated with that conversation. Further events sent within the conversation will be sent only to that device in real-time and will be synchronised with other (inactive) devices as required. Any given user can only have one active device / interface at any given point in time for an active session. |
| AF | Anonymization Function |
| Aggregation of device capabilities | All of a user’s capabilities for their RCS services on all of their RCS-enabled devices will be combined into a single set of capabilities which is shared with other users. Other users will not be able to determine on exactly which device another user has a specific capability, nor will other users know whether the user has multiple RCS devices available to him at all (using this capability information shared). |
| AKA | Authentication and Key Agreement |
| AMR | Adaptive Multi-Rate |
| Anonymous Mode | A user has agreed not to share their MSISDN with a Chatbot. |
| A-Party | The party that initiates a communication event e.g. creates and sends a Chat Message or File Transfer or initiates a call to the B-Party. |
| APN | Access Point Name |
| App | Smartphone application. |
| App ID | Unique identifier for an application. |
| API | Application Programming Interface |
| Auto-Accept | A function on the device that shortcuts the user manual acceptance of the incoming communication event (such as chat, files etc.). |
| B-Party | The party that receives or is intended to receive a communication event e.g. Chat Message, File Transfer or call from the A-Party. |
| Call Composer | A view on the device that allows the A-Party to enrich outgoing voice calls with pre-call content before placing the call. |
| Call Log | The view on the device displaying all the user’s call events, e.g. incoming, outgoing, and missed calls. Call logs usually offer a view containing all call events (including call duration and end time) ordered chronologically, plus a detailed view of a single call event or call events with a specific Contact. |
| Capability / Availability | A contact has a device registered for RCS service that can initiate or respond to a requested RCS service. |
| CFB | Call Forward Busy |
| CFS | Client Fallback to SMS incl. Revocation – one of the two procedures of Delivery Assurance in Integrated Messaging. |
| Chatbot | An RCS-based (fully or partly) automated service provided to users whose output is presented in a conversational form. Often a piece of software interfacing with one or more users aiming to simulate intelligent human conversation. Two types of Chatbots can be differentiated:<br>• Generic Chatbots which are referenced as “Chatbot” in this document. (These Chatbots may or may not be verified by a Verification Authority.)<br>• “Critical Chatbots” which have specific attributes assigned that provide them with special rights as defined in this document. |
| Chatbot Directory | A catalogue of all available Chatbots. |
| Chatbot Gallery | Place where a user can explore Chatbots and start a conversation with them. |
| Chatbot Platform | A system that provides a mechanism for Chatbot developers to create and register Chatbots, which can then be exposed to the users connected to the platform through a messaging system. |
| Chatbot Profile Information | Additional information provided by the Chatbot to the user that allows the user to e.g. contact the Brand operating the Chatbot over other channels, or better understand what the purpose of the Chatbot is or what the Brand operating the Chatbot does. |
| Chatbot Welcome Message | A message, defined by the Chatbot, and delivered by the Chatbot Platform to the user, providing context when starting a new interaction between the user and Chatbot. |
| Chat Message | A single text message that was exchanged between two or more RCS communication end points (e.g. users or Chatbots). |
| CLIP | Calling Line Identification Presentation |
| CLIR | Calling Line Identification Restriction |
| Common Message Store (CMS) | Network storage that enables Multi-Device and Backup and Restore use cases. |
| Contact | A contact is a communication partner either selected from the device contact list or typed into the dialler as a telephone number. |
| Contact Card | The details of a single contact that are displayed whenever a contact is selected from the contact list. |
| Contextual Icon | An icon that allows a Suggested Action to be differentiated from a Suggested Reply and visually represents the specific Suggested Action. |
| Conversation History | A list of all the content exchanged between parties of a conversation. |
| CPIM | Common Profile for Instant Messaging |
| CPM | Converged IP Messaging |
| CS | Circuit Switched |
| CSS | Cascading Style Sheets |
| CW | Call Waiting |
| Default Dialler | In the case of multiple diallers on a device, the client chosen by the user to act as the default dialler for setting up and receiving voice and video calls. |
| Default Messaging Client | In the case of multiple messaging clients on a device, the client chosen by the user to act as the default messaging client for messaging notification and composing purposes. |
| Delete Message Indication | A visible indication within the conversation for an RCS Message that was deleted by the sender. |
| Delivery Assurance | A mechanism in Integrated Messaging that improves the timely delivery of messages and files. The procedures that Delivery Assurance uses are Client Fallback to SMS including Revocation (CFS) and Network Fallback to SMS (NFS). |
| Delivery Notification | Indication that a message was successfully received by the B-Party device. |
| Developer | Application owner. |
| Developer ID | ID assigned to application owner. It is not the same as the App ID. |
| Device Wiping | Removing user specific data from the device. |
| Display Notification | When the message has been displayed in the Chat view on the receiving device. |
| Direct Delivery | In multi-device messaging, when an event (e.g. Chat Message, File Transfer, Audio Message, or Geolocation Push) is received, it is received on all of the recipient’s registered and connected devices at the same time. When an event is sent from any of the registered and connected devices, it is sent to all of the sender’s other registered and connected devices at the same time. |
| DNS | Domain Name System |
| DTMF | Dual Tone Multi-Frequency |
| Dual SIM device | A device where two different identities, provided by two different SIMs, are active at the same time. |
| E2EE | End to End Encryption |
| Edit Message | A mechanism that allows the user to edit a sent RCS Message. |
| Edit Message Indication | A visible indication that an RCS Message was edited by the sender. |
| Edit Time Interval | The period during which the Edit Message feature is available to the sender of an RCS Message. |
| Emoji | Emoji are “picture characters”, that is, characters presented as pictographs, images of things such as faces, weather, vehicles and buildings, food and drink, animals and plants or icons that represent emotions, feelings, or activities. |
| Emoticon | A graphical ‘mood’ element that technically is corresponding with a text string. The text string is conveyed by the standard, and interpreted on UI level and replaced with the corresponding graphical element. |
| End to End Encryption | The process of encrypting content and related information on the sender’s device and decrypting on the recipient’s device; ensuring that no third party can access the content and related information, while it is being transferred. |
| Enriched Voice Calling | The ability to share content before, during and after a voice call. |
| EUCR | End User Confirmation Requests |
| E-UTRAN | Evolved UMTS (Universal Mobile Telecommunications System) Terrestrial Radio Access Network |
| Events | Events as used in this Service Description Document are messages, content and notifications in the context of Operator Messaging. |
| External Loudspeaker | Speaker on the device which amplifies the audio of the call when activated. |
| Feature Tag | An IARI Tag assigned to a RCS functionality allowing to identify and route the RCS traffic accordingly. |
| Federated Device | A common term used for all devices federated under the identity of a specific user (federated devices always comprise one primary and one or more secondary devices). |
| File Transfer Status Notification or File Transfer States Notifications | A visible information for the sender of a File Transfer in 1-to-1 Messaging or Group Chat about the progress of the delivery. |
| FQDN | Fully Qualified Domain Name |
| Front Camera | Camera placed on the display side of a communication device. |
| GBA | Generic Bootstrap Architecture |
| GIF | Graphics Interchange Format |
| Global Setting(s) | In a multi-device setup, Global Settings are settings which are changed on one device and change the corresponding setting on any federated devices or interfaces as well (as opposed to Local Settings). |
| GPRS | General Packet Radio Service |
| Group Chat | A conversation where the creator invites 2 or more participants to take part. All participants are aware of each other, and all content exchanged is shared with the entire participants list. |
| Group MIVC | An MIVC that can only include participants of the Group Chat from which the MIVC was initiated. |
| HOS | Home Operator Services |
| HTML | Hyper Text Markup Language |
| HTTP | Hyper Text Transfer Protocol |
| IARI | IMS Application Reference Identifier |
| ICSI | IMS Communication Service Identifier |
| IMDN | Instant Message Disposition Notification |
| IMS | Internet Protocol (IP) Multimedia Subsystem |
| IMSI | International Mobile Subscriber Identification. |
| Inactive device or Interface | A device or interface not currently active in a multi-device scenario. |
| Interconnected RCS Service | An RCS Service that can be accessed between users of MNOs supporting the same RCS Service capabilities. |
| Interface | Any entity that provides RCS Service capabilities to a user, e.g. browser-based, app-based, natively implemented. |
| Integrated Messaging | An MNO messaging service whereby the different message types are proposed to the end user, threaded together in a conversation and can be changed by the user. In this experience the message type used to deliver a message is indicated to the user. |
| IP Video Call | Type of real time communication that uses live audio and video. |
| Is Typing Notification | A visible information for participants in a 1-to-1 Messaging or Group Chat conversation that another participant in the conversation is in the process of creating a message. This message may or may not be sent by that user. |
| JPEG | Joint Photographic Experts Group |
| KB | KiloByte (i.e. 1024 bytes) |
| KDS | Key Distribution Server |
| LED | Light Emitting Diode |
| Local Settings | In a multi-device setup, Local Settings are settings which are changed on one device without any impact on corresponding settings on any federated devices or interfaces (as opposed to Global Settings). |
| LTE | Long Term Evolution |
| MaaP Application | A remote service that the user is able to communicate with from the Messaging Application on the device, e.g. a Chatbot. |
| MDV2 | Multi device Voice and Video |
| Media Share | File Transfer of multi-media content that can be displayed or played back in an RCS client. |
| Messaging event | Associated with any of the services listed in R9-3-4 and includes all types of messages, files, content, new message notifications, previews, icons and message status notifications (sent and received). |
| Message Status Notification or Message States Notifications | A visible information for the sender of a message in 1-to-1 Messaging or Group Chat about the progress of the delivery. |
| Messaging-Initiated Video Call (MIVC) | An IP Video Call initiated from a Messaging conversation that can only include participants of that Messaging conversation. |
| MIME | Multipurpose Internet Mail Extensions |
| MIVC Call Log | A Call Log associated with an MIVC. |
| MMS | Multimedia Messaging service |
| MNO | Mobile network operator. |
| MSISDN | Mobile Subscriber Integrated Services Digital Number, i.e. mobile telephone number. |
| Multi-Device Support | RCS Service that enables a user to register more than one device under a single identity. |
| Multi Device Voice and Video | An MNO service that allows to use SIM based and SIM less devices to make voice and / or video calls (and supporting services around these) under one identity. |
| Multi-SIM | Multi-SIM is an MNO-individual solution to federate SIM-based devices for offering a multi device solution to customers. Multi-SIM solutions may or may not be based on SIMs with identical identities. |
| Multimedia Telephony | Voice and/or Video telephony services over 4G and 5G radio and Wi-Fi bearers as defined in 3GPP and profiled in e.g. GSMA PRDs IR.92, IR.94, IR.51 and NG.114. |
| Multiple Reactions | More than one Reaction sent by the user in response to a specific selected RCS Message. |
| Native RCS Device | A device with an RCS client deeply integrated by the OEM or OS developer (as opposed to a downloaded RCS client). |
| New Incoming Event Notification | An audible and/or visible information for the receiving user (B-Party) that a new message or file has been received. |
| NFS | Network Fallback to SMS – one of the two procedures of Delivery Assurance in Integrated Messaging. |
| NR | New Radio |
| ODSA | On-Device Service Activation |
| OEM | Original Equipment Manufacturer. |
| “offline” user | A user who is known to be RCS enabled and not currently registered to the RCS service. |
| OIDC | Open ID Connect |
| OMA | Open Mobile Alliance |
| On-Net | Communication or signalling that does not go across the interworking interface (NNI) between networks or MNOs. |
| “online” user | A user who is known to be RCS enabled and is currently registered to the RCS service. |
| OS | Operating System |
| Operator Messaging | Integration of all Operator Messaging Services into one single application. There are two options for Operator Messaging: “Integrated Messaging” and “Seamless Messaging”. |
| Operator Messaging Services | One or more services from traditional messaging services (SMS, MMS) or RCS services (Chat, File Transfer, Audio Messaging, vCard Push, Geolocation Push). |
| OTP | One Time Password |
| P2A | Person to Application (communication) |
| P2P | Person to Person (communication) |
| P-CSCF | Proxy Call Session Control Function |
| Plug-in | A mini application that appears within messaging or voice / video calling applications to aesthetically and functionally enrich the content of the conversation. |
| Plug-in Consumer | RCS client that is able to use Plug-ins. |
| Plug-in Provider | Any app that contains and exposes a Plug-in. |
| Primary Device or Primary Interface | Device which contains the SIM that matches the identity which the RCS client uses to register in IP Multimedia Subsystem (IMS). |
| Primary SIM | In the context of a Multi Device solution, the Primary SIM shall be the SIM that provides the identity of the Primary Device or Interface and all federated Secondary Devices or Interfaces. |
| PS | Packet Switched |
| Public Mode | A user has agreed to share their MSISDN with a Chatbot. |
| Push Notification | A notification to the RCS client, when not connected to the RCS Service Provider, that a new incoming communication event (e.g. new Chat Message, File Transfer, Audio Message, Message or File Transfer Status / State notifications) is available for the user. The Push Notification is sent by the RCS Service Provider to wake up the RCS client for establishing a connection to the RCS Service Provider for the new incoming communication event. |
| Push Notification Mechanism | A mechanism that enables the RCS Service Provider to enable non-persistent connections between the RCS Service Provider and the RCS client (in contrast to the mechanism that uses persistent connections) for communication event delivery. The mechanism is not visible to the user. |
| RCS | Rich Communication Services |
| RCS 1-to-1 Messaging | Can either be standalone messaging or 1-to-1 chat as defined in RCC.07. |
| RCS Alias name | A name that is defined by the user that represents the user as a Chat participant on B-Party devices, if no Contact exists in the contact list. |
| RCS-enabled | Capable of the RCS service, activated and ready to operate when the network conditions allow. |
| RCS Service Provider | A company providing Rich Communications Services (RCS) to end customers. RCS Service Providers are Mobile Network Operators. |
| Reachable | The UE can receive service notifications irrespective of RCS service registration or connection to the cellular network. |
| Reaction | An Emoji/Emoticon/image sent by the user in response to a specific selected RCS Message. |
| Rear Camera | Opposite to the Front Camera positioned on the back of the device. |
| Recall Message | A best effort mechanism that allows a user to recall a sent RCS Message without leaving history. |
| Recall Message Indication | A visible indication within the conversation for an RCS Message that was recalled by the sender. |
| Recall Time Interval | The period during which the Recall Message feature is available to the sender of an RCS Message. |
| Recurring Payment | A predictable payment of a fixed amount which the user has agreed to pay on a regular schedule. |
| Reply Message | An RCS Message sent by the user in response to a specific selected RCS Message. |
| Rich Text Formatting | Applying and using various text styling elements within RCS messages. |
| Rich Text Message | An RCS message that includes Rich Text Formatting applied by the sender and intended to be rendered with visual styling on the sender’s and the recipient’s device. |
| Seamless Messaging | An MNO messaging service whereby the user does not have to choose the messaging technology used but the device / network determines which messaging technology is used. |
| Secondary Device or Secondary Interface | Terms used to describe any access to a user’s RCS account and service features from a device or interface not containing the SIM associated with the primary identity. A user may have several secondary devices and/or interfaces available to access their RCS service, including devices containing SIMs not associated with the user's primary identity. |
| Service availability | Service availability is a state of a specific user that is determined using Capability Discovery processes. |
| SG | Signalling Gateway |
| SIM | Subscriber Identity Module |
| SIP | Session Initiation Protocol |
| SMS | Short Message Service |
| Spam Folder | A separated area from the regular conversation and chatbot threads where a user would be able to access messages that have been considered as suspicious by the RCS client. |
| SRVCC | Single Radio Voice Call Continuity |
| SSL | Secure Socket Layer |
| SSO | Single Sign-On |
| Standalone Message | A single text message that was conveyed from one user to another using the RCS Standalone Messaging service. |
| Suggested Action | A suggestion that a Chatbot can provide to an RCS client enabling a user to perform an external action on their device (e.g. opening a web page, adding a calendar entry, etc.). |
| Suggested Chip List | A number of Suggested Replies and/or Suggested Actions that a Chatbot can send to a user along with a message. |
| Suggested Reply | A suggestion that a Chatbot can provide to an RCS client for the user to easily send a pre-defined reply message to the Chatbot. |
| Suspicion Indicator | An indication from the RCS Service Provider for suspicious messages. |
| T&C | Terms & Conditions |
| TE | Technical Enabler |
| Thread (or messaging thread) | A thread (or "messaging thread") is the history of all messages or files exchanged in past between two users, including message exchanged in past which are not part of the current conversation. This notion can be extended to Group, and then represents exchanges between all participants of the group. |
| TLS | Transport Layer Security |
| Trusted Wi-Fi | “Trusted Wi-Fi” refers to a Wi-Fi connection offered by the RCS Service Provider or via a third party trusted by the RCS Service Provider. |
| UE | User Equipment |
| UI | User Interface |
| Universal Profile | Specification that describes a profile of the RCS Standard that has the ambition to work globally on any RCS enabled network. |
| URI | Uniform Resource Identifier |
| User Encryption Identifier | A unique identifier associated with a given user that can be used to verify their identity, when sending or receiving end to end encrypted content. |
| User Initiated Content | Content or related information that is initiated by the user, examples include Chat Message, Contact Card, Emoji, Emoticon, File and associated metadata, and Is Typing Notification. |
| User Profile | Personal information customised by the RCS user (e.g. name & image). |
| UX | User Experience |
| Verification Authority | A provider of verification for Chatbots. A Verification Authority could be, but not limited to, a commercial trusted business (e.g. verification companies from the internet world), an MNO or a governmental function. |
| Verified Chatbot | A Chatbot that was verified to represent the identity (e.g. name, brand or institution) that their name, brand icon and Chatbot Profile Information suggest. |
| Video Message | A UI implementation that allows the user to record a video and send it to a 1-to-1 Messaging conversation, in a similar manner to sending and recording an Audio Message. For maximum duration, Video Message follows Audio Message and/or file transfer maximum size limits (whichever is reached first). |
| VoLTE | Voice over Long Term Evolution |
| VVM | Visual Voice Mail. |
| Voice Mail System (VMS) | The network system that allows users to listen to voice messages, delete voice messages, and compose voice messages. |
| Wi-Fi | Trademark of Industry Consortium "Wi-Fi Alliance" used as synonym for WLAN (Wireless Local Area Network). |
| XML | Extensible Markup Language |
| xMS | The traditional MNO messaging services known as Short Message Service (SMS) and Multimedia Messaging Service (MMS). |
