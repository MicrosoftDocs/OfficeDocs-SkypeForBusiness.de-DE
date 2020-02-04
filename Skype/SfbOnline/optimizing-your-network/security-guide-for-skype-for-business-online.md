---
title: Sicherheitsleitfaden für Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: ''
ms.date: 01/22/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Security
description: Sicherheitsleitfaden für Skype for Business Online <add description>
ms.openlocfilehash: 268a9859439ca91b5ad7cd8d5e32edf707860cde
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706810"
---
# <a name="security-and-skype-for-business-online"></a>Sicherheit und Skype for Business Online

Skype for Business Online (SfBO), im Rahmen des Office 365-Diensts, befolgt alle bewährten Sicherheitsmethoden und-Verfahren wie die Sicherheit auf Dienstebene durch tief greifende, kundenspezifische Steuerelemente innerhalb des Diensts, Sicherheits Härtung und bewährte Methoden für den Betrieb. Ausführliche Informationen finden Sie im Microsoft Trust Center (https://microsoft.com/trustcenter).

## <a name="trustworthy-by-design"></a>Vertrauenswürdiger Aufbau
Skype for Business Online is designed and developed in compliance with the Microsoft Trustworthy Computing Security Development Lifecycle (SDL), which is described at https://www.microsoft.com/en-us/sdl/default.aspx. The first step in creating a more secure unified communications system was to design threat models and test each feature as it was designed. Multiple security-related improvements were built into the coding process and practices. Build-time tools detect buffer overruns and other potential security threats before the code is checked in to the final product. Of course, it is impossible to design against all unknown security threats. No system can guarantee complete security. However, because product development embraced secure design principles from the start, Skype for Business Online incorporates industry standard security technologies as a fundamental part of its architecture. 

## <a name="trustworthy-by-default"></a>Vertrauenswürdig durch seine Standardeinstellungen
Network communications in Skype for Business Online are encrypted by default. By requiring all servers to use certificates and by using OAUTH, TLS, Secure Real-Time Transport Protocol (SRTP), and other industry-standard encryption techniques, including 256-bit Advanced Encryption Standard (AES) encryption, all Skype for Business Online data is protected on the network.

## <a name="how-sfbo-handles-common-security-threats"></a>So geht SfBO mit allgemeinen Sicherheitsbedrohungen um
In diesem Abschnitt werden die häufigeren Bedrohungen für die Sicherheit des SfBO-Diensts und die Art und Weise erläutert, wie Microsoft jede Bedrohung abschwächt.

### <a name="compromised-key-attack"></a>Angriff mit kompromittierten Schlüsseln
Ein Schlüssel ist ein Geheimcode oder eine Nummer, mit der geheime Informationen verschlüsselt, entschlüsselt oder überprüft werden. In der Public Key-Infrastruktur (PKI) werden zwei vertrauliche Schlüssel verwendet, die berücksichtigt werden müssen: der private Schlüssel, den die einzelnen Zertifikatbesitzer besitzen, und der Sitzungsschlüssel, der nach einer erfolgreichen Identifikation und einem Sitzungsschlüssel Austausch durch die kommunizierenden Partner verwendet wird. Ein Angriff mit Gefährdung durch den Schlüssel erfolgt, wenn der Angreifer den privaten Schlüssel oder den Sitzungsschlüssel bestimmt. Wenn der Angreifer bei der Ermittlung des Schlüssels erfolgreich ist, kann er den Schlüssel verwenden, um verschlüsselte Daten ohne Wissen des Absenders zu entschlüsseln.

Skype for Business Online uses the PKI features in the Windows Server operating system to protect the key data used for encryption for the Transport Layer Security (TLS) connections. The keys used for media encryptions are exchanged over TLS connections. 

### <a name="network-denial-of-service-attack"></a>Denial-of-Service-Angriff auf das Netzwerk
The denial-of-service attack occurs when the attacker prevents normal network use and function by valid users. By using a denial-of-service attack, the attacker can:
- Er kann ungültige Daten an Anwendungen und Dienste senden, die in dem angegriffenen Netzwerk ausgeführt werden, um ihre Funktionsweise zu beeinträchtigen.
- Er kann große Datenmengen senden, um das System zu überlasten, bis es nicht mehr oder nur noch verzögert auf legitime Anforderungen reagiert.
- Er kann die Spuren seines Angriffs vertuschen.
- Er kann Benutzer vom Zugriff auf die Netzwerkressourcen abhalten.

SfBO mildert diese Angriffe ab, indem Sie Azure DDoS-Netzwerkschutz ausführen und Clientanforderungen von denselben Endpunkten, Subnetzen und Verbund Entitäten einschränken.

### <a name="eavesdropping"></a>Abhörschutz
Abhöraktionen sind Aktionen, bei denen sich Angreifer Zugriff auf den Datenpfad in einem Netzwerk verschaffen und anschließend den Datenverkehr überwachen und lesen können. Dies wird auch als „Schnüffeln“ (auch „Lauschangriff“, englisch Sniffing oder Snooping) bezeichnet. Wenn der Datenverkehr aus reinem Text besteht, können Angreifer ihn lesen, sobald sie Zugriff auf den Pfad haben. Ein Beispiel wäre ein Angriff, bei dem ein Router auf dem Datenpfad kontrolliert wird. 

SfBO uses mutual TLS (MTLS) for server communications within O365 and TLS from clients to the service, rendering this attack very difficult to impossible to achieve within the time period in which a given conversation could be attacked. TLS authenticates all parties and encrypts all traffic. This does not prevent eavesdropping, but the attacker cannot read the traffic unless the encryption is broken.

Das Turn-Protokoll wird für echt Zeit Medienzwecke verwendet. Das Turn-Protokoll beauftragt nicht, den Datenverkehr zu verschlüsseln, und die gesendeten Informationen sind durch Nachrichtenintegrität geschützt. Obwohl es für Lauschangriffe geöffnet ist, können die gesendeten Informationen (also IP-Adressen und Port) direkt extrahiert werden, indem Sie einfach die Quell-und Zieladressen der Pakete betrachten. Der SfBO-Dienst stellt sicher, dass die Daten gültig sind, indem die Nachrichtenintegrität der Nachricht mit dem von einigen wenigen Elementen abgeleiteten Schlüssel überprüft wird, einschließlich eines Turn-Kennworts, das nie in Klartext gesendet wird. SRTP wird für Mediendatenverkehr verwendet und ebenfalls verschlüsselt.

### <a name="identity-spoofing-ip-address-spoofing"></a>Identitätsvortäuschung (Spoofing der IP-Adresse)
Spoofing occurs when the attacker determines and uses an IP address of a network, computer, or network component without being authorized to do so. A successful attack allows the attacker to operate as if the attacker is the entity normally identified by the IP address. Within the context of Microsoft Lync Server 2010, this situation comes into play only if an administrator has done both of the following:
- Er hat Verbindungen konfiguriert, die nur TCP (Transmission Control Protocol) unterstützen. (Dies ist nicht zu empfehlen, da die TCP-Kommunikation unverschlüsselt ist.)
- Er hat die IP-Adressen dieser Verbindungen als vertrauenswürdige Hosts markiert. 

This is less of a problem for Transport Layer Security (TLS) connections, as TLS authenticates all parties and encrypts all traffic. Using TLS prevents an attacker from performing IP address spoofing on a specific connection (for example, mutual TLS connections). But an attacker could still spoof the address of the DNS server that SfBO uses. However, because authentication in SfBO is performed with certificates, an attacker would not have a valid certificate required to spoof one of the parties in the communication.

### <a name="man-in-the-middle-attack"></a>Man-in-the-Middle-Angriff
A man-in-the-middle attack occurs when an attacker reroutes communication between two users through the attacker’s computer without the knowledge of the two communicating users. The attacker can monitor and read the traffic before sending it on to the intended recipient. Each user in the communication unknowingly sends traffic to and receives traffic from the attacker, all while thinking they are communicating only with the intended user. This can happen if an attacker can modify Active Directory Domain Services to add his or her server as a trusted server or modify Domain Name System (DNS) to get clients to connect through the attacker on their way to the server. 

Ein Man-in-the-Middle-Angriff kann auch bei Medienverkehr zwischen zwei Clients auftreten, außer dass in SfBO Punkt-zu-Punkt Audio-, Video- und Application-Sharing-Streams mit SRTP verschlüsselt werden, wobei kryptographische Schlüssel verwendet werden, die zwischen den Peers über das Session Initiation Protocol (SIP) über TLS ausgehandelt werden. 

### <a name="rtp-replay-attack"></a>Angriff mit Aufzeichnungswiederholung (RTP-Datenverkehr)
A replay attack occurs when a valid media transmission between two parties is intercepted and retransmitted for malicious purposes. SfBO uses SRTP in conjunction with a secure signaling protocol that protects transmissions from replay attacks by enabling the receiver to maintain an index of already received RTP packets and compare each new packet with those already listed in the index.

### <a name="spim"></a>SPIM (Spam over Instant Messaging)
Unter SPIM sind unaufgeforderte Werbe-SMS oder Anwesenheitsabonnementanforderungen zu verstehen. Zwar wird das Netzwerk nicht unmittelbar beeinträchtigt, doch ist SPIM zumindest ärgerlich, kann die Ressourcenverfügbarkeit und die Produktivität reduzieren und möglicherweise zu einer Beeinträchtigung des Netzwerks führen. Ein Beispiel für Spimming sind Nutzer, die sich gegenseitig Anfragen zusenden. Nutzer können sich gegenseitig blockieren, um dies zu verhindern. Ein koordinierter Spimangriff im Partnerverbund kann jedoch schwer abzuwehren sein, wenn Sie den Verbund für den Partner nicht deaktivieren.

### <a name="viruses-and-worms"></a>Viren und Würmer
Bei einem Virus handelt es sich um eine Codeeinheit, deren Zweck darin besteht, zusätzliche, ähnliche Codeeinheiten zu reproduzieren. Um zu funktionieren, benötigt ein Virus einen Host, beispielsweise eine Datei, eine e-Mail oder ein Programm. Wie bei einem Virus handelt es sich bei einem Wurm um eine Codeeinheit, die codiert wird, um zusätzliche, ähnliche Codeeinheiten zu reproduzieren, die aber im Gegensatz zu einem Virus keinen Host benötigen. Viren und Würmer werden in erster Linie bei Dateiübertragungen zwischen Clients angezeigt, oder wenn URLs von anderen Benutzern gesendet werden. Wenn sich ein Virus auf Ihrem Computer befindet, kann er beispielsweise Ihre Identität verwenden und in Ihrem Namen Sofortnachrichten senden. Standard mäßige Client Security-bewährte Methoden wie regelmäßiges Scannen auf Viren können dieses Problem verringern. 

## <a name="personally-identifiable-information"></a>Informationen zur Identifikation von Personen
SfBO has the potential to disclose information over a public network that might be able to be linked to an individual. The information types can be broken down to two specific categories:
- **Enhanced presence data**&nbsp;&nbsp;&nbsp;Enhanced presence data is information that a user can choose to share or not share over a link to a federated partner or with contacts within an organization. This data is not shared with users on a public IM network. Client policies and other client configuration may put some control with the system administrator. In the SfBO service, enhanced presence privacy mode can be configured for an individual user to prevent SfBO users not on the user’s Contacts list from seeing the user’s presence information. 
- **Mandatory data**&nbsp;&nbsp;&nbsp;Mandatory data is data that is required for the proper operation of the server or the client. This is information that is necessary at a server or network level for the purposes of routing, state maintenance, and signaling. The following tables list the data that is required for SfBO to operate.

***Tabelle 1 - Erweiterte Anwesenheitsdaten***

<!--start table here -->


|                      |                                                                                            |   |
|:---------------------|:-------------------------------------------------------------------------------------------|:--|
| **Daten**             | **Mögliche** **Einstellungen**                                                                  |   |
| Persönliche Daten        | Name, Titel, Firma, e-Mail-Adresse, Zeitzone                                             |   |
| Telefonnummern    | Geschäftlich, mobil, privat                                                                         |   |
| Kalenderdaten | Frei/gebucht, Abwesenheitsnotiz, Besprechungsdetails (für Personen, die auf Ihren Kalender zugreifen können) |   |
| Anwesenheitsstatus      | Abwesend, verfügbar, gebucht, nicht stören, offline                                             |   |
|                      |                                                                                            |   |

<!-- end of table -->

***Tabelle 2 - Plichtdaten***

<!--start table here -->


|              |                                                                 |   |
|:-------------|:----------------------------------------------------------------|:--|
| **Kategorie** | **Mögliche Einstellungen**                                           |   |
| IP-Adresse   | Tatsächliche Computer- oder NAT-Adresse                     |   |
| SIP-URI      | <u>david.campbell@contoso.com</u>                               |   |
| Name         | David Campbell (wie in Active Directory Domain Services definiert) |   |
|              |                                                                 |   |

<!-- end of table -->

## <a name="security-framework-for-sfbo"></a>Sicherheitsframework für SfBO
This section provides an overview of the fundamental elements that form the security framework for Microsoft SfBO. These elements are as follows:
- Azure Active Directory (AAD) bietet ein einziges vertrauenswürdiges Back-End-Repository für Benutzerkonten. 
- Die Public Key-Infrastruktur (PKI) verwendet Zertifikate, die von vertrauenswürdigen Zertifizierungsstellen ausgestellt werden, um Server zu authentifizieren und die Datenintegrität zu gewährleisten.
- Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted and integrity checked using Secure Real-Time Transport Protocol (SRTP).
- Branchenstandardprotokolle für die Benutzerauthentifizierung, falls möglich.

In den Themen in diesem Abschnitt wird beschrieben, wie jedes dieser grundlegenden Elemente funktioniert, um die Sicherheit des SfBO-Diensts zu verbessern.

### <a name="azure-active-directory"></a>Azure Active Directory
Azure Active Directory functions as the directory service for O365. It stores all user directory information and policy assignments. 

### <a name="public-key-infrastructure-for-sfbo"></a>Public-Key-Infrastruktur für SfBO
SfBO service relies on certificates for server authentication and to establish a chain of trust between clients and servers and among the different server roles. The Windows Server public key infrastructure (PKI) provides the infrastructure for establishing and validating this chain of trust. Certificates are digital IDs. They identify a server by name and specify its properties. To ensure that the information on a certificate is valid, the certificate must be issued by a Certificate Authority (CA) that is trusted by clients or other servers that connect to the server. If the server connects only with other clients and servers on a private network, the CA can be an enterprise CA. If the server interacts with entities outside the private network, a public CA might be required.

Even if the information on the certificate is valid, there must be some way to verify that the server presenting the certificate is actually the one represented by the certificate. This is where the Windows PKI comes in. Each certificate is linked to a public key. The server named on the certificate holds a corresponding private key that only it knows. A connecting client or server uses the public key to encrypt a random piece of information and sends it to the server. If the server decrypts the information and returns it as plain text, the connecting entity can be sure that the server holds the private key to the certificate and therefore is the server named on the certificate.

#### <a name="crl-distribution-points"></a>Sperrlisten-Verteilungspunkte
SfBO erfordert, dass alle Serverzertifikate mindestens einen CRL-Verteilungspunkt (Certificate Revocation List) enthalten. CRL-Verteilungspunkte (CDPs) sind Speicherorte, an denen CRLs heruntergeladen werden können, um zu überprüfen, ob das Zertifikat seit dem Zeitpunkt, zu dem es ausgestellt wurde, nicht widerrufen wurde und das Zertifikat sich noch innerhalb des Gültigkeitszeitraums befindet. Ein CRL-Verteilungspunkt wird in den Eigenschaften des Zertifikats als URL notiert und ist ein sicheres HTTP. Der SfBO-Dienst überprüft die CRL bei jeder Zertifikatauthentifizierung.

#### <a name="enhanced-key-usage"></a>Erweiterte Schlüsselverwendung
All components of the SfBO service require all server certificates to support Enhanced Key Usage (EKU) for the purpose of server authentication. Configuring the EKU field for server authentication means that the certificate is valid for the purpose of authenticating servers. This EKU is essential for MTLS. 

### <a name="tls-and-mtls-for-sfbo"></a>TLS und MTLS für SfBO
TLS and MTLS protocols provide encrypted communications and endpoint authentication on the Internet. SfBO uses these two protocols to create the network of trusted servers and to ensure that all communications over that network are encrypted. All SIP communications between servers occur over MTLS. SIP communications from client to server occur over TLS.

TLS enables users, through their client software, to authenticate the SfBO servers to which they connect. On a TLS connection, the client requests a valid certificate from the server. To be valid, the certificate must have been issued by a CA that is also trusted by the client and the DNS name of the server must match the DNS name on the certificate. If the certificate is valid, the client uses the public key in the certificate to encrypt the symmetric encryption keys to be used for the communication, so only the original owner of the certificate can use its private key to decrypt the contents of the communication. The resulting connection is trusted and from that point is not challenged by other trusted servers or clients. Within this context, Secure Sockets Layer (SSL) as used with Web services can be associated as TLS-based.

Server-to-server connections rely on mutual TLS (MTLS) for mutual authentication. On an MTLS connection, the server originating a message and the server receiving it exchange certificates from a mutually trusted CA. The certificates prove the identity of each server to the other. In the SfBO service, this procedure is followed.

TLS and MTLS help prevent both eavesdropping and man-in-the middle attacks. In a man-in-the-middle attack, the attacker reroutes communications between two network entities through the attacker’s computer without the knowledge of either party. TLS and SfBO’s specification of trusted servers mitigate the risk of a man-in-the middle attack partially on the application layer by using end-to-end encryption coordinated using the Public Key cryptography between the two endpoints, and an attacker would have to have a valid and trusted certificate with the corresponding private key and issued to the name of the service to which the client is communicating to decrypt the communication. 

### <a name="encryption-for-sfbo"></a>Verschlüsselung für SfBO
SfBO uses TLS and MTLS to encrypt instant messages. All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.

Die folgende Tabelle fasst das von SfBO verwendete Protokoll zusammen.

***Tabelle 3 - Datenverkehrsschutz***

<!--start table here with header -->


|||
|:-----|:-----|
|**Datenverkehrstyp**|**Geschützt durch**|
|Server-zu-Server|MTLS|
|Client-zu-Server|TLS|
|Chat und Anwesenheit|TLS (falls für TLS konfiguriert)|
|Audio und Video und Desktopfreigaben von Medien|SRTP|
|Desktopfreigabe (Signal)|TLS|
|Webkonferenzen|TLS|
|Herunterladen von Besprechungsinhalten, Herunterladen des Adressbuchs, Erweiterung der Verteilergruppe|HTTPS|
|||

<!-- end of table -->

#### <a name="media-encryption"></a>Medienverschlüsselung
Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic. SRTP uses a session key generated by using a secure random number generator and exchanged using the signaling TLS channel. In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP. 

SfBO generates username/passwords for secure access to media relays over TURN. Media relays exchange the username/password over a TLS-secured SIP channel.

#### <a name="fips"></a>FIPS
SfBO verwendet FIPS (Federal Information Processing Standard) konforme Algorithmen für den Austausch von Verschlüsselungsschlüsseln. 

### <a name="user-and-client-authentication"></a>Benutzer- und Client-Authentifizierung 
Ein vertrauenswürdiger Benutzer ist einer, dessen Anmeldeinformationen von Aad in Office 365 authentifiziert wurden. 

Authentication is the provision of user credentials to a trusted server or service. SfBO uses the following authentication protocols, depending on the status and location of the user.
- **Moderne Authentifizierung** ist die Microsoft-Implementierung von OAUTH 2,0 für Client-zu-Server-Kommunikation. Sie ermöglicht Sicherheitsfeatures wie Office 365-zertifikatbasierte Authentifizierung, Office 365 mehrstufige Authentifizierung und Office 365 bedingten Zugriff. Um MA verwenden zu können, müssen sowohl der Online Mandant als auch die Clients für MA aktiviert sein. SfBO-Mandanten, die nach May 2017 erstellt wurden, haben MA standardmäßig aktiviert. Für Mandanten, die vor diesem Zeitpunkt erstellt wurden, folgen Sie den Anweisungen hier, um Sie zu aktivieren. Die folgenden Clients unterstützen alle MA: Skype for Business 2015 oder 2016 Client, Skype for Business für Mac, lync 2013-Client, 3PIP IP-Telefone, IOS und Android. 
- Die **org-ID** wird verwendet, wenn die moderne Authentifizierung nicht aktiviert ist (oder nicht verfügbar ist).
- Das **Digestprotokoll** für sogenannte anonyme Benutzer. Anonyme Benutzer sind externe Benutzer, die nicht über anerkannte Active Directory-Anmeldeinformationen verfügen, aber zu einer lokalen Konferenz eingeladen wurden und einen gültigen Konferenzschlüssel besitzen. Die Digestauthentifizierung wird nicht für andere Clientinteraktionen verwendet.

Die SfBO-Authentifizierung besteht aus zwei Phasen:
1. Zwischen dem Client und dem Server wird eine Sicherheitszuordnung eingerichtet.
2. Client und Server verwenden die vorhandene Sicherheitszuordnung, um Nachrichten, die sie senden, zu signieren, und Nachrichten, die sie empfangen, zu überprüfen. Nicht authentifizierte Nachrichten von einem Client werden nicht akzeptiert, wenn die Authentifizierung auf dem Server aktiviert ist.

User trust is attached to each message that originates from a user, not to the user identity itself. The server checks each message for valid user credentials. If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in SfBO.

Benutzer mit gültigen Anmeldeinformationen, die von einem Verbundpartner ausgegeben wurden, sind vertrauenswürdig, erhalten aber optional aufgrund zusätzlicher Einschränkungen nicht sämtliche Berechtigungen, die internen Benutzern erteilt werden.

For media authentication, the ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC. For details, see [media traversal](#external-user-av-traffic-traversal).

Client Zertifikate stellen eine alternative Möglichkeit für Benutzer dar, von SfBO authentifiziert zu werden. Anstatt einen Benutzernamen und ein Kennwort anzugeben, verfügen Benutzer über ein Zertifikat und den privaten Schlüssel, der dem Zertifikat entspricht, das zum Beheben einer kryptografischen Herausforderung erforderlich ist. 

### <a name="windows-powershell-and-sfbo-management-tools"></a>Windows PowerShell und SfBO-Verwaltungstools
In SfBO können IT-Administratoren ihren Dienst über das Office 365-Administratorportal oder mithilfe der Mandanten-Remote-PowerShell (TRPS) verwalten. Mandantenadministratoren verwenden die moderne Authentifizierung, um sich bei TRPS zu authentifizieren.

### <a name="configuring-access-to-sfbo-at-your-internet-boundary"></a>Konfigurieren des Zugriffs auf SfBO an Ihrer Internetgrenze
Damit SfBO ordnungsgemäß funktioniert (Benutzer können an Besprechungen teilnehmen usw.), müssen Kunden den Internetzugriff so konfigurieren, dass der ausgehende UDP-und TCP-Datenverkehr zu Diensten in der SfBO-Cloud zulässig ist. Weitere Informationen finden Sie hier:https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_lyo 

### <a name="udp-3478-3481-and-tcp-443"></a>UDP 3478-3481 und TCP 443

Die UDP-3478-3481-und TCP 443-Ports werden von Clients verwendet, um den Dienst vom A/V-Edgedienst anzufordern. Ein Client verwendet diese beiden Ports zum Zuweisen von UDP-und TCP-Ports für den Remote Partner, mit dem eine Verbindung hergestellt werden soll. Um auf den a/v-Edgedienst zuzugreifen, muss der Client zunächst eine authentifizierte SIP-Signalisierungs Sitzung mit der SfBO-Registrierungsstelle eingerichtet haben, um die Anmeldeinformationen für eine/v-Edgedienst-Authentifizierung abzurufen. Diese Werte werden über den TLS-geschützten Signalisierungskanal gesendet und zur Abwehr von Wörterbuchangriffen Computer generiert. Clients können diese Anmeldeinformationen dann für die Digestauthentifizierung mit dem A/V-Edgedienst verwenden, um Ports für die Verwendung in einer Mediensitzung zuzuweisen. Eine anfängliche Zuordnungsanforderung wird vom Client gesendet und mit einer 401-Fehler/-Herausforderungs Nachricht vom a/V-Edgedienst beantwortet. Der Client sendet einen zweiten Allocate-Wert, der den Benutzernamen und einen Hash Message Authentication Code (HMAC)-Hash des Benutzernamens und des Augenblicks enthält. 

A sequence number mechanism is also in place to prevent replay attacks. The server calculates the expected HMAC based on its own knowledge of the user name and password and if the HMAC values match, the allocate procedure is carried out. Otherwise, the packet is dropped. This same HMAC mechanism is also applied to subsequent messages within this call session. The lifetime of this user name/password value is a maximum of eight hours at which time the client reacquires a new user name/password for subsequent calls.

### <a name="udptcp-5000059999"></a>UDP/TCP 50000 – 59.999
TCP 50,000 outbound is used for SfBO, including for application and desktop sharing, file transfer. UDP/TCP 50,000-59,999 port ranges are used for media sessions with Microsoft Office Communications Server 2007 partners that require NAT/firewall traversal service from the A/V Edge service. Because the A/V Edge service is the sole process using these ports, the size of the port range does not indicate the potential surface of attack. Good security practice is to always minimize the total number of listening ports by not running unnecessary network services. If a network service is not running, it is not exploitable by a remote attacker and the surface of attack of the host computer is reduced. However, within a single service, reducing the number of ports does not provide the same benefit. The A/V Edge service software is no more exposed to attack with 10,000 ports open as it is with 10. The allocation of ports within this range is done randomly and ports not currently allocated do not listen for packets.

### <a name="external-user-av-traffic-traversal"></a>Externer Benutzer A/V-Verkehrdurchlauf
Enabling external users and internal users to exchange media requires an Access Edge service to handle the SIP signaling that is necessary to set up and tear down a session. It also requires an A/V Edge service to act as a relay for the transfer of the media. The call sequence is illustrated in the following figure.


![Aufrufsequenz in der Besprechungsteilnahme](media/sfbo-call-sequence-security.png) 

1. A user receives an email containing an invitation to join an SfBO meeting. The email contains a conference key and a HTTP-based URL linking to the conference. Both the key and the URL are unique for a particular meeting.<p>Der Benutzer initiiert die Teilnahme Prozedur durch Klicken auf die Besprechungs-URL in der e-Mail, die einen Client Erkennungsprozess auf dem Computer des Benutzers initiiert. Wenn der Client erkannt wird, wird dieser Client gestartet. Wenn Sie nicht erkannt wird, wird der Benutzer an den WebClient weitergeleitet.<p/>
2. Der SfBO-Client sendet eine SIP-Einladung mit den Anmeldeinformationen des Benutzers. Ein Verbund-oder Remotebenutzer nimmt eine Konferenz unter Verwendung seiner Unternehmensanmeldeinformationen an. Bei einem Föderationsbenutzer wird die SIP-Einladung zuerst an seinen Home-Server gesendet, der den Benutzer authentifiziert und die Einladung an SfBO weiterleitet. Ein anonymer Benutzer muss die Digest-Authentifizierung übergeben.<p>SfBO authenticates the remote or anonymous user and notifies the client. As mentioned in step 2, federated users joining a conference are authenticated by their enterprise.<p/>

3. Der Client sendet eine INFO-Anforderung, um den Benutzer der A/V-Konferenz hinzuzufügen.

    Die a/v-Konferenzen senden eine Antwort des Benutzers hinzufügen, die das Token enthält, das dem a/v-Konferenz-Edgedienst unter anderen Informationen zur Verfügung steht.

    Hinweis  Der gesamte vorhergehende SIP-Datenverkehr wurde über den Access Edge-Dienst durchlaufen.

    The client connects to the A/V Conference Server, which validates the token and proxies the request, which contains another authorization token, to the internal A/V Conferencing Server. The A/V Conferencing Server validates the Authorization Token, which it originally issued over the SIP channel, to further ensure that a valid user is joining the conference.

4. Zwischen dem Client und dem a/V-Konferenz Server wird eine Medien Verbindung ausgehandelt und über SRTP eingerichtet.
5. A user receives an email containing an invitation to join an SfBO meeting. The email contains a conference key and a HTTP-based URL linking to the conference. Both the key and the URL are unique for a particular meeting.

### <a name="federation-safeguards-for-sfbo"></a>Verbund Garantien für SfBO
Föderation bietet Ihrer Organisation die Möglichkeit, mit anderen Organisationen zu kommunizieren und Chats und Anwesenheitsinformationen freizugeben. In SfBO ist der Verbund standardmäßig aktiviert. Mandantenadministratoren haben jedoch die Möglichkeit, dies über das Office 365-Verwaltungsportal zu kontrollieren. Weitere Informationen.

## <a name="addressing-threats-to-sfbo-conferences"></a>Handhaben von Bedrohungen für SfBO-Konferenzen

SfBO provides the capability for enterprise users to create and join real-time Web conferences. Enterprise users can also invite external users who do not have an AAD/O365 account to participate in these meetings. Users who are employed by federated partners with a secure and authenticated identity can also join meetings and, if promoted to do so, can act as presenters. Anonymous users cannot create or join a meeting as a presenter, but they can be promoted to presenter after they join.

Enabling external users to participate in SfBO meetings greatly increases the value of this feature, but it also entails some security risks. To address these risks, SfBO provides the following additional safeguards:
- Teilnehmerrollen bestimmen die Berechtigungen für die Konferenzsteuerung.
- Mithilfe der Teilnehmertypen können Sie den Zugriff auf bestimmte Besprechungen einschränken.
- Definierte Besprechungstypen legen fest, welche Teilnehmertypen teilnehmen können.
- Die Konferenzplanung ist auf Benutzer mit einem AAD-Konto und einer SfBO-Lizenz beschränkt.
- Anonymous, that is, unauthenticated, users who want to join a dial-in conference dial one of the conference access numbers and then they are prompted to enter the conference ID. Unauthenticated anonymous users are also prompted to record their name. The recorded name identifies unauthenticated users in the conference. Anonymous users are not admitted to the conference until at least one leader or authenticated user has joined, and they cannot be assigned a predefined role.

### <a name="participant-roles"></a>Teilnehmerrollen
Die Besprechungsteilnehmer gliedern sich in drei Gruppen mit jeweils eigenen Privilegien und Einschränkungen:
- **Organizer** &nbsp; &nbsp;der Benutzer, der eine Besprechung erstellt, ob spontan oder durch planen. Ein Organisator muss ein authentifizierter Unternehmensbenutzer sein und alle Endbenutzer Aspekte einer Besprechung kontrollieren.
- **** &nbsp;Referent &nbsp;ein Benutzer, der berechtigt ist, Informationen in einer Besprechung zu präsentieren, wobei alle Medien unterstützt werden. Ein Besprechungsorganisator ist definitionsgemäß auch Referent und bestimmt, wer sonst ein Referent sein kann. Ein Organisator kann diese Entscheidung treffen, wenn eine Besprechung geplant ist oder die Besprechung läuft.
- &nbsp; &nbsp; **Teilnehmer** : ein Benutzer, der zur Teilnahme an einer Besprechung eingeladen wurde, aber nicht autorisiert ist, als Referent zu fungieren.

Ein Referent kann auch einen Teilnehmer während der Besprechung für die Rolle des Referenten befördern.

### <a name="participant-types"></a>Teilnehmertypen

Meeting participants are also categorized by location and credentials. You can use both of these characteristics to specify which users can have access to specific meetings. Users can be divided broadly into the following categories:
1.  **Benutzer, die dem Mandanten** &nbsp; &nbsp;angehören diese Benutzer verfügen über eine Anmeldeinformationen in Azure Active Directory für den Mandanten.<br/> a. *Inside corpnet* – These users are joining from inside the corporate network.<br/>b. *Remote users* – These users are joining from outside the corporate network. They can include employees who are working at home or on the road, and others, such as employees of trusted vendors, who have been granted enterprise credentials for their terms of service. Remote users can create and join conferences and act as presenters.
2.  **Benutzer, die nicht zum Mandaten gehören**&nbsp;&nbsp;Diese Benutzer haben keine Anmeldeinformation im Azure Active Directory für den Mandanten.<br/>a. *Federated-Benutzer* – Föderationsbenutzer besitzen gültige Anmeldeinformationen für Federated-Partner und werden daher von SfBO als authentifiziert behandelt. Föderationsbenutzer können an Konferenzen teilnehmen und zu Referenten heraufgestuft werden, nachdem Sie der Besprechung beigetreten sind, aber Sie können keine Konferenzen in Unternehmen erstellen, mit denen Sie verbunden sind.<br/>b. *Anonymous Users* - Anonymous users do not have an Active Directory identity and are not federated with the tenant. 

Customer data shows that many conferences involve external users. Those same customers also want reassurance about the identity of external users before allowing those users to join a conference. As the following section describes, SfBO limits meeting access to those user types that have been explicitly allowed and requires all user types to present appropriate credentials when entering a meeting.

### <a name="participant-admittance"></a>Teilnehmerzulassung
In SfBO, anonymous users are transferred to a waiting area called the lobby. Presenters can then either admit these users to the meeting or reject them. These users are transferred to the lobby, the leader is notified, and the users then wait until a leader either accepts or rejects them or their connection times out. While in the lobby, the users hear music. 

Standardmäßig gehen Teilnehmer, die sich aus dem PSTN einwählen, direkt zur Besprechung, aber diese Option kann geändert werden, um die Einwahl der Teilnehmer in die Lobby zu erzwingen.  
Meeting organizers control whether participants can join a meeting without waiting in the lobby. Each meeting can be set up to enable access using any one of the following methods:
- **Nur ich, der Organisator des Treffens**&nbsp;&nbsp;Jeder außer dem Organisator muss in der Lobby warten, bis er zugelassen wird.
- **Personen, die ich aus meinem Unternehmen einlade**&nbsp;&nbsp;Jeder aus Ihrem Unternehmen kann direkt zur Besprechung kommen, auch wenn er nicht eingeladen ist.
- **Anyone from my organization**&nbsp;&nbsp;All SfBO users in the O365 tenant can join the meeting without waiting in the lobby, even if those who are not on the distribution list. All others, including all external and anonymous users, must wait in the lobby until admitted.
- ****&nbsp;Jeder&nbsp;Benutzer (es gibt keine Einschränkungen), der Zugriff auf den Besprechungslink hat, wird direkt an der Besprechung teilnehmen. Wenn eine Methode mit Ausnahme von Organizer (gesperrt) angegeben wird, kann der Besprechungsorganisator auch angeben, dass Personen, die sich per Telefon einwählen, die Lobby umgehen. 

### <a name="presenter-capabilities"></a>Referentenfunktion
Meeting organizers control whether participants can present during a meeting. Each meeting can be set up to limit presenters to any one of the following:
- **Organisator nur**&nbsp;&nbsp;der Besprechungsorganisator kann anwesend sein.
- **Personen aus meinem Unternehmen**&nbsp;&nbsp;, die alle internen Benutzer präsentieren können.
- **Alle Personen, einschließlich Personen außerhalb meines Unternehmens**&nbsp;&nbsp;(es gibt keine Einschränkungen), die der Besprechung beitreten, können anwesend sein.
- **Personen, die ich wähle**&nbsp;&nbsp;Der Organisator der Besprechung legt fest, welche Benutzer präsentieren können, indem er sie einer Liste von Referenten hinzufügt.

## <a name="related-topics"></a>Verwandte Themen
[Microsoft Trust Center](https://microsoft.com/trustcenter)

