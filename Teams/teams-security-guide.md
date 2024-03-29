---
title: Sicherheitshandbuch für Microsoft Teams – Übersicht
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 04/12/2022
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: Sicherheitsratschläge und Schulungen für IT-Administratoren zur Installation, Konfiguration und Wartung von Microsoft Teams.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6e5dcee1e45ec191853f088887e7ed36f8e3fbc6
ms.sourcegitcommit: 39fc58109da6b4628ffb658f2c6b94099e0ab604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2022
ms.locfileid: "66103202"
---
# <a name="security-and-microsoft-teams"></a>Sicherheit und Microsoft Teams

> [!IMPORTANT]
> Das Teams-Dienstmodell kann geändert werden, um die Kundenzufriedenheit zu verbessern. So können beispielsweise die standardmäßigen Ablaufzeiten des Zugriffs- oder Aktualisierungstokens geändert werden, um die Leistung und die Authentifizierungssicherheit für Benutzer von Teams zu verbessern. Solche Änderungen würden vorgenommen, um die Sicherheit und Vertrauenswürdigkeit von Teams zu gewährleisten.

Microsoft Teams folgt als Teil der Microsoft 365- und Office 365-Dienste allen bewährten Methoden und Verfahren für die Sicherheit, wie z. B. Sicherheit auf Dienstebene durch mehrschichtige Abwehrmaßnahmen, Kundenkontrollfunktionen innerhalb des Dienstes, Sicherheitshärtung und betriebliche bewährte Methoden. Die vollständigen Details finden Sie unter [Microsoft Trust Center](https://microsoft.com/trustcenter).

## <a name="trustworthy-by-design"></a>Vertrauenswürdigkeit als Konzept

Teams Online wurde in Übereinstimmung mit dem Microsoft Trustworthy Computing Security Development Lifecycle (SDL) entwickelt, der unter [Microsoft Security Development Lifecycle (SDL)](https://www.microsoft.com/sdl/default.aspx) beschrieben wird. Der erste Schritt beim Erstellen eines sicheren einheitlichen Kommunikationssystems bestand in der Entwicklung von Gefahrenmodellen und im Testen jedes einzelnen Features während seines Entwurfs. Viele sicherheitsrelevante Verbesserungen wurden während der Codephase getestet und integriert. Mit Buildzeittools werden Pufferüberläufe und andere potenzielle Sicherheitsbedrohungen erkannt, bevor der Code in das Endprodukt übernommen wird. Es ist nicht möglich, so zu entwerfen, dass alle unbekannten Sicherheitsbedrohungen beseitigt werden. Es gibt kein System, für das vollständige Sicherheit garantiert werden kann. Da bei der Produktentwicklung jedoch von Anfang an sichere Entwurfsprinzipien angewendet wurden, umfasst Teams die branchenüblichen Standardsicherheitstechnologien als grundlegenden Bestandteil seiner Architektur.

## <a name="trustworthy-by-default"></a>Vertrauenswürdigkeit als Standard

Die Netzwerkkommunikation in Teams ist standardmäßig verschlüsselt. Indem verlangt wird, dass alle Server Zertifikate verwenden müssen, und durch die Verwendung von OAUTH, Transport Layer Security (TLS) und Secure Real-Time Transport Protocol (SRTP) sind alle Teams-Daten im Netzwerk geschützt.

## <a name="how-teams-handles-common-security-threats"></a>So wird in Microsoft Teams mit allgemeinen Sicherheitsbedrohungen umgegangen

Dieser Abschnitt beschreibt die häufigsten Bedrohungen für die Sicherheit des Teams-Dienstes und wie Microsoft jede Bedrohung entschärft.

### <a name="compromised-key-attack"></a>Angriff mit kompromittiertem Schlüssel

Teams verwendet die PKI-Features des Windows Server-Betriebssystems, um die für die Verschlüsselung der TLS-Verbindungen verwendeten Schlüsseldaten zu schützen. Die für die Medienverschlüsselung verwendeten Schlüssel werden über TLS-Verbindungen ausgetauscht.

### <a name="network-denial-of-service-attack"></a>Denial-of-Service-Angriff auf Netzwerke

Ein verteilter Denial-of-Service-Angriff (DDOS) liegt vor, wenn der Angreifer die normale Nutzung und Funktion des Netzwerks durch gültige Benutzer verhindert. Mit einem Denial-of-Service-Angriff kann der Angreifer:

- Er kann ungültige Daten an Anwendungen und Dienste senden, die in dem angegriffenen Netzwerk ausgeführt werden, um ihre Funktionsweise zu beeinträchtigen.
- Er kann große Datenmengen senden, um das System zu überlasten, bis es nicht mehr oder nur noch verzögert auf legitime Anforderungen reagiert.
- Er kann die Spuren seines Angriffs vertuschen.
- Er kann Benutzer vom Zugriff auf die Netzwerkressourcen abhalten.

Teams mildert diese Angriffe, indem es den Azure DDOS-Netzwerkschutz ausführt und Client-Anforderungen von denselben Endpunkten, Subnetzen und Verbundentitäten einschränkt.

### <a name="eavesdropping"></a>Abhörschutz

Ein Lauschangriff liegt vor, wenn sich ein Angreifer Zugriff auf den Datenpfad in einem Netzwerk verschafft und anschließend die Möglichkeit hat, den Datenverkehr zu überwachen und zu lesen. „Lauschen“ wird auch als „Schnüffeln“ (englisch „Sniffing“ oder „Snooping“) bezeichnet. Wenn der Datenverkehr aus reinem Text besteht, können Angreifer ihn lesen, sobald sie Zugriff auf den Pfad haben. Ein Beispiel wäre ein Angriff, bei dem ein Router auf dem Datenpfad kontrolliert wird.

Microsoft Teams verwendet Mutual TLS (MTLS) und Server-zu-Server (S2S)-OAuth (neben anderen Protokollen) für die Serverkommunikation innerhalb von Microsoft 365 und Office 365 sowie TLS von Clients zum Dienst. Der gesamte Datenverkehr im Netzwerk wird verschlüsselt.

Diese Kommunikationsmethoden machen das Mithören innerhalb des Zeitraums einer einzelnen Unterhaltung schwierig oder unmöglich. TLS authentifiziert alle Parteien und verschlüsselt den gesamten Datenverkehr. Obwohl TLS Lauschangriffe nicht verhindert, kann der Angreifer den Datenverkehr nur auslesen, wenn die Verschlüsselung aufgehoben wird.

Das *Traversal Using Relays around NAT*-Protokoll (TURN) wird für Echtzeit-Medienzwecke verwendet. Es schreibt keine Verschlüsselung des Datenverkehrs vor, und die Informationen, die darüber versendet werden, werden durch die Nachrichtenintegrität geschützt. Obwohl es für Lauschangriffe offen ist, können die von ihm gesendeten Informationen (d. h. IP-Adressen und Port) direkt extrahiert werden, indem man einfach die Quell- und Zieladressen der Pakete betrachtet. Der Teams-Dienst stellt sicher, dass die Daten gültig sind, indem er die Nachrichtenintegrität der Nachricht anhand des Schlüssels überprüft, der aus einigen Elementen abgeleitet wird, einschließlich eines TURN-Kennworts, welches niemals im Klartext gesendet wird. SRTP wird für den Mediendatenverkehr verwendet und ist ebenfalls verschlüsselt.

### <a name="identity-spoofing-ip-address-spoofing"></a>Identitätsspoofing (Spoofing von IP-Adressen)

Spoofing liegt vor, wenn der Angreifer unbefugt die IP-Adresse eines Netzwerks, Computers oder einer Netzwerkkomponente identifiziert und verwendet. Bei einem erfolgreichen Angriff kann der Angreifer so agieren, als wäre er die Entität, die normalerweise durch die IP-Adresse identifiziert wird.

TLS authentifiziert alle Parteien und verschlüsselt den gesamten Datenverkehr. Die Verwendung von TLS verhindert, dass ein Angreifer IP-Adressspoofing auf bestimmte Verbindungen (z. B. gemeinsame TLS-Verbindungen) durchführen kann. Ein Angreifer könnte die Adresse des verwendeten DNS (Domain Name System)-Servers trotzdem noch spoofen. Da die Authentifizierung in Teams jedoch mittels Zertifikaten erfolgt, würde ein Angreifer über keine gültigen Informationen verfügen, die für das Spoofing einer der Parteien in der Kommunikation notwendig wären.

### <a name="man-in-the-middle-attack"></a>Man-in-the-Middle-Angriff

Von einem "Man-in-the-Middle-Angriff" spricht man, wenn Angreifer die Kommunikation zwischen zwei Nutzern ohne deren Wissen über ihren eigenen Computer leiten. Die Angreifer können die übertragenen Daten überwachen und lesen, ehe sie an den eigentlichen Empfänger weitergeleitet werden. Beide Kommunikationspartner senden unwissentlich Daten an die Angreifer und empfangen von ihnen Daten, sind aber dabei in dem Glauben, ausschließlich mit der beabsichtigten Person zu kommunizieren. Dieses Szenario kann vorkommen, wenn es Angreifern gelingt, die Active Directory-Domänendienste so zu ändern, dass ihr Server als vertrauenswürdiger Server hinzugefügt wird, oder wenn sie die DNS-Konfiguration ändern oder andere Mittel verwenden, damit Clients auf dem Weg zum Server über den Computer der Angreifer geleitet werden.

Man-in-the-Middle-Attacken gegen den Mediendatenverkehr zwischen zwei Endpunkten, die an Teams Audio-, Video- und der Anwendungsfreigabe teilnehmen, werden durch die Verwendung von *Secure Real-Time Transport-Protokoll* (SRTP) zum Verschlüsseln des Mediendatenstroms verhindert. Kryptografieschlüssel werden zwischen den beiden Endpunkten über ein proprietäres Signalprotokoll (Teams Call Signaling Protocol) ausgehandelt, das einen mit TLS 1.2 und AES-256 (im GCM-Modus) verschlüsselten UDP- oder TCP-Kanal nutzt.

### <a name="real-time-transport-protocol-rtp-replay-attack"></a>RTP-Replay-Angriff (Real-Time Transport-Protokoll)

Ein Replay-Angriff liegt vor, wenn eine gültige Medienübertragung zwischen zwei Parteien abgefangen und für böswillige Zwecke erneut übertragen wird. Microsoft Teams verwendet SRTP mit einem sicheren Signalübermittlungsprotokoll, das die Übertragungen vor Angriffen mit Aufzeichnungswiederholung schützt. Mit SRTP können Empfänger einen Index der bereits empfangenen RTP-Pakete erstellen und jedes neue Paket mit den bereits enthaltenen abgleichen.

### <a name="spim"></a>Spim

Bei Spim handelt es sich um unerwünschte kommerzielle Chatnachrichten oder Anwesenheitsabonnementanforderungen (beispielsweise Spam), jedoch in Form von Chatnachrichten. Dies an sich ist zwar keine Kompromittierung des Netzwerks, aber es ist dennoch mindestens ärgerlich, kann die Verfügbarkeit von Ressourcen und der Produktion verringern und möglicherweise zu einer Kompromittierung des Netzwerks führen. Ein Beispiel dafür sind Benutzer, die sich gegenseitig durch das Senden von Anforderungen zuspimmen. Benutzer können sich gegenseitig blockieren, um Spimming zu verhindern, aber in einem Partnerverbund kann es schwierig sein, dies zu verhindern, wenn ein böswilliger Akteur einen koordinierter Spim-Angriff einrichtet, sei denn, Sie deaktivieren den Partnerverbund für den Partner.

### <a name="viruses-and-worms"></a>Viren und Würmer

Ein Virus ist eine Codeeinheit, deren Zweck darin besteht, weitere, ähnliche Codeeinheiten zu reproduzieren. Für seine Arbeit benötigt der Virus einen Host wie z. B. eine Datei, eine E-Mail oder ein Programm. Ähnlich wie ein Virus ist auch ein Wurm eine Codeeinheit, die weitere, ähnliche Codeeinheiten reproduziert, aber im Gegensatz zu einem Virus keinen Host benötigt. Viren und Würmer treten vornehmlich bei Dateiübertragungen zwischen Clients auf, oder wenn URLs von anderen Benutzern gesendet werden. Wenn sich auf Ihrem Computer ein Virus befindet, kann er beispielsweise Ihre Identität verwenden und Sofortnachrichten in Ihrem Namen versenden. Standardmäßige bewährte Methoden für die Client-Sicherheit wie z. B. die regelmäßige Überprüfung auf Viren können dieses Problem entschärfen.

## <a name="security-framework-for-teams"></a>Sicherheitsframework für Teams

Teams unterstützt Sicherheitsideen wie Zero Trust und die Prinzipien des geringstprivilegierten Zugriffs. Dieser Abschnitt enthält eine Übersicht über grundlegende Elemente, die ein Sicherheitsframework für Microsoft Teams bilden.

Die wichtigsten Elemente sind:

- Azure Active Directory (Azure AD) bietet ein einziges vertrauenswürdiges Back-End-Repository für Benutzerkonten. Informationen zu Benutzerprofilen werden in Azure AD durch die Aktionen von Microsoft Graph gespeichert.
  - Möglicherweise wurden mehrere Token ausgegeben, die bei Verfolgung des Netzwerkdatenverkehrs ggf. angezeigt werden. Dazu gehören Skype-Token, die beim Betrachten des Chats und Audiodatenverkehr möglicherweise in Ablaufverfolgungen angezeigt werden.
- Transport Layer Security (TLS) verschlüsselt den Kanal in Bewegung. Die Authentifizierung erfolgt entweder mithilfe von gegenseitigen TLS (MTLS), basierend auf Zertifikaten oder mithilfe der Diesnt-zu-Dienst-Authentifizierung basierend auf Azure AD.
- Punkt-zu-Punkt-Audio-, Video- und Anwendungsfreigabestreams werden verschlüsselt und die Integrität mithilfe des Secure Real-Time Transport Protocol (SRTP) überprüft.
- In Ihrer Spur wird OAuth-Datenverkehr angezeigt, insbesondere beim Tokenaustausch und dem Aushandeln von Berechtigungen beim Wechseln zwischen Registerkarten in Teams, z. B. um von Posts zu Dateien zu wechseln. Ein Beispiel für den OAuth-Ablauf für Registerkarten [finden Sie in diesem Dokument](/microsoftteams/platform/tabs/how-to/authentication/auth-flow-tab).
- Teams verwenden nach Möglichkeit branchenübliche Protokolle für die Nutzerauthentifizierung.

In den nächsten Abschnitten werden einige dieser Kerntechnologien erläutert.

### <a name="azure-active-directory"></a>Azure Active Directory

Azure Active Directory fungiert als Verzeichnisdienst für Microsoft 365 und Office 365. Es speichert alle Nutzer- und Anwendungsverzeichnisinformationen und Richtlinienzuweisungen.

### <a name="traffic-encryption-in-teams"></a>Datenverkehrsverschlüsselung in Teams

Diese Tabelle zeigt die wichtigsten Datenverkehrstypen und das Protokoll, das für die Verschlüsselung verwendet wird.

|**Datenverkehrstyp**|**Verschlüsselt durch**|
|:-----|:-----|
|Server-zu-Server|TLS (mit MTLS oder Dienst-zu-Dienst-OAuth)|
|Client-zu-Server, z. B. Chat und Anwesenheit|TLS|
|Medienflüsse, z. B. die Audio- und Videofreigabe von Medien|TLS|
|Audio- und Videofreigaben von Medien|SRTP/TLS|
|Signalisierung|TLS|
|Erweiterte Client-zu-Client-Verschlüsselung (z. B. End-to-End-Verschlüsselungsaufrufe)|SRTP/DTLS|
|||

#### <a name="certificate-revocation-list-crl-distribution-points"></a>Verteilungspunkte für Zertifikatsperrlisten (Certificate Revocation List, CRL)

Microsoft 365- und Office 365-Datenverkehr erfolgt über TLS/HTTPS-verschlüsselte Kanäle, was bedeutet, dass Zertifikate zur Verschlüsselung des gesamten Datenverkehrs verwendet werden. In Teams müssen alle Serverzertifikate einen oder mehrere CRL-Verteilungspunkte enthalten. CRL-Verteilungspunkte (CRL Distribution Points, CDPs) sind Speicherorte, von denen CRLs heruntergeladen werden können, um zu prüfen, ob das Zertifikat seit seiner Ausstellung nicht widerrufen wurde, und ob es sich noch im Gültigkeitszeitraum befindet. Ein CRL-Verteilungspunkt wird in den Eigenschaften des Zertifikats als URL angegeben und ist sicheres HTTP. Der Teams-Dienst überprüft die CRL bei jeder Zertifikatauthentifizierung.

#### <a name="enhanced-key-usage"></a>Erweiterte Schlüsselverwendung

Alle Komponenten des Teams-Diensts erfordern, dass alle Serverzertifikate die erweiterte Schlüsselverwendung (Enhanced Key Usage, EKU) für die Serverauthentifizierung unterstützen. Die Konfiguration des EKU-Felds für die Serverauthentifizierung bedeutet, dass das Zertifikat für die Authentifizierung von Servern gültig ist. Diese EKU ist wesentlich für MTLS.

#### <a name="tls-for-teams"></a>TLS für Teams

**Teams-Daten werden während der Übertragung und im Ruhezustand in Microsoft-Dienste, zwischen Diensten sowie zwischen Clients und Diensten verschlüsselt.** Microsoft verwendet dazu Branchenstandardtechnologien wie TLS und SRTP, um alle Daten während der Übertragung zu verschlüsseln. Zu den übertragenen Daten gehören Nachrichten, Dateien, Besprechungen und andere Inhalte. Ruhende Unternehmensdaten in Microsoft-Dienste werden ebenfalls so verschlüsselt, dass Organisationen Inhalte bei Bedarf entschlüsseln können, um ihre Sicherheits- und Complianceanforderungen zu erfüllen, z. B. mit eDiscovery. Weitere Informationen zur Verschlüsselung in Microsoft 365 finden Sie unter [Verschlüsselung in Microsoft 365](/microsoft-365/compliance/encryption).

TCP-Datenflüsse werden mithilfe von TLS verschlüsselt, und MTLS- und Dienst-zu-Dienst-OAuth-Protokolle bieten endpunktauthentifizierte Kommunikationen zwischen Diensten, Systemen und Clients. Microsoft Teams verwendet diese Protokolle, um ein Netzwerk vertrauenswürdiger Systeme zu erstellen und sicherzustellen, dass die gesamte Kommunikation über dieses Netzwerk verschlüsselt ist.

Bei einer TLS-Verbindung fordert der Client ein gültiges Zertifikat vom Server an. Um gültig zu sein, muss das Zertifikat von einer Zertifizierungsstelle ausgestellt worden sein, der auch vom Client vertraut wird, und der DNS-Name des Servers muss mit dem DNS-Namen in dem Zertifikat übereinstimmen. Wenn das Zertifikat gültig ist, verwendet der Client den öffentlichen Schlüssel im Zertifikat, um die symmetrischen Verschlüsselungsschlüssel, die für die Kommunikation verwendet werden, zu verschlüsseln, sodass nur der ursprüngliche Eigentümer des Zertifikats seinen privaten Schlüssel für die Entschlüsselung der Inhalte der Kommunikation verwenden kann. Die daraus resultierende Verbindung ist vertrauenswürdig und wird von diesem Punkt an von anderen vertrauenswürdigen Servern oder Clients nicht angezweifelt.

Die Verwendung von TLS trägt dazu bei, Abhöraktionen und Man-in-the-Middle-Angriffe zu verhindern. Bei einem Man-in-the-Middle-Angriff leitet der Angreifer die Kommunikation zwischen zwei Netzwerkentitäten ohne Wissen der Beteiligten über seinen Computer um. TLS und die Microsoft Teams-Spezifikation vertrauenswürdiger Server mindern das Risiko von Man-in-the-Middle-Angriffen teilweise auf Anwendungsebene durch die Verwendung von Verschlüsselung, die über Public Key-Kryptografie zwischen den zwei Endpunkten koordiniert wird. Ein Angreifer bräuchte ein gültiges und vertrauenswürdiges Zertifikat mit dem entsprechenden privaten Schlüssel, das zudem auf den Namen des Dienstes ausgestellt ist, mit dem der Client kommuniziert, um die Kommunikation entschlüsseln zu können.

#### <a name="encryption-in-teams-and-microsoft-365"></a>Verschlüsselung in Teams und Microsoft 365

Es gibt mehrere Verschlüsselungsebenen innerhalb Microsoft 365. Die Verschlüsselung in Microsoft Teams wirkt mit der restlichen Microsoft 365-Verschlüsselung zusammen, um die Inhalte Ihrer Organisation zu schützen. In diesem Artikel werden für Microsoft Teams spezifische Verschlüsselungstechnologien beschrieben. Eine Übersicht über die Verschlüsselung in Microsoft 365 finden Sie unter [Verschlüsselung in Microsoft 365](/microsoft-365/compliance/encryption).

#### <a name="media-encryption"></a>Medienverschlüsselung

Anrufflüsse in Teams basieren auf dem Angebots- und Antwortmodell [Session Description Protocol (SDP) RFC 8866](https://datatracker.ietf.org/doc/html/rfc8866) über HTTPS. Sobald der Angerufene einen eingehenden Anruf annimmt, stimmen Anrufer und Angerufener den Sitzungsparametern zu.

Mediendatenverkehr zwischen Anrufer und Angerufenem wird über Secure RTP (SRTP) verschlüsselt, ein Profil von RTP (Real-Time Transport-Protokoll), das Vertraulichkeit, Authentifizierung und Schutz vor Replay-Angriffen für RTP-Datenverkehr bietet. SRTP verwendet einen Sitzungsschlüssel, der von einem sicheren Zufallszahlengenerator generiert und über den signalisierenden TLS-Kanal ausgetauscht wird. Der Client-zu-Client-Mediendatenverkehr wird meistens über Client-zu-Server-Verbindungssignale verhandelt, und bei direktem Client-zu-Client mit SRTP verschlüsselt.

Bei normalen Anrufflüssen erfolgt die Aushandlung des Verschlüsselungsschlüssels über den Anrufsignalkanal. Bei einem End-to-End-verschlüsselten Anruf ist der Signalisierungsfluss derselbe wie bei einem normalen 1:1-Microsoft Teams-Anruf. Allerdings wird in Microsoft Teams mittels DTLS ein Verschlüsselungsschlüssel basierend auf Zertifikaten pro Anruf abgeleitet, die auf beiden Clientendpunkten generiert werden. Da DTLS den Schlüssel basierend auf den Clientzertifikaten ableitet, ist der Schlüssel für Microsoft undurchsichtig. Sobald sich beide Clients mit dem Schlüssel einverstanden erklären, beginnt der Medienfluss mit diesem mit DTLS ausgehandelten Verschlüsselungsschlüssel über SRTP.

Zum Schutz vor einem Man-in-the-Middle-Angriff zwischen dem Anrufer und dem Aufgerufenen leitet Microsoft Teams einen 20-stelligen Sicherheitscode aus den SHA-256-Fingerabdrücken der Endpunktanrufzertifikate von Anrufer und Angerufenem ab. Der Aufrufer und der Angerufene können die 20-stelligen Sicherheitscodes überprüfen, indem sie sich gegenseitig vorlesen, um festzustellen, ob sie übereinstimmen. Wenn die Codes nicht übereinstimmen, wurde die Verbindung zwischen dem Aufrufer und dem Angerufenen im Rahmen eines Man-in-the-Middle-Angriffs abgefangen. Wenn der Anruf kompromittiert wurde, können die Benutzer den Anruf manuell beenden.

Teams verwendet ein auf Anmeldeinformationen basierendes Token für den sicheren Zugriff auf Medienrelays über TURN. Medienrelays tauschen das Token über einen TLS-gesicherten Kanal aus.

### <a name="federal-information-processing-standard-fips"></a>Federal Information Processing Standard (FIPS)

Microsoft Teams verwendet FIPS-konforme Algorithmen für den Austausch von Verschlüsselungsschlüsseln. Weitere Informationen zur Implementierung von FIPS finden Sie unter [FIPS (Federal Information Processing Standard) Publication 140-2](/microsoft-365/compliance/offering-fips-140-2).

### <a name="user-and-client-authentication"></a>Nutzer- und Clientauthentifizierung

Bei einem vertrauenswürdigen Benutzer handelt es sich um eine Person, deren Anmeldeinformationen in Microsoft 365 oder Office 365 von Azure AD authentifiziert wurden.

Authentifizierung bedeutet die Bereitstellung von Benutzeranmeldeinformationen gegenüber einem vertrauenswürdigen Server oder Dienst. Microsoft Teams verwendet abhängig vom Status und Standort des Benutzers die nachstehenden Authentifizierungsprotokolle.

- **Moderne Authentifizierung (MA)** ist die Microsoft-Implementierung von OAUTH 2.0 für die Client-Server-Kommunikation. Sie ermöglicht Sicherheitsfunktionen wie mehrstufige Authentifizierung (MA) und bedingten Zugriff. Für die Nutzung von MA müssen sowohl der Onlinemandant als auch die Clients für MA aktiviert sein. Alle Microsoft Teams-Clients über PC und Mobilgeräte hinweg sowie der Webclient [unterstützen die mehrstufige Authentifizierung](./sign-in-teams.md).

> [!NOTE]
> Weitere Informationen zu Azure AD-Authentifizierungs- und Autorisierungsmethoden finden Sie in diesem Artikel in den Abschnitten "Einführung" und "Grundlegendes zur Authentifizierung in Azure AD".

Die Teams-Authentifizierung erfolgt über Azure AD und OAuth. Der Authentifizierungsprozess kann vereinfacht werden:

- Benutzeranmeldung > Token-Ausgabe > Nächste Anforderung verwendet ausgegebenes Token.

Anforderungen vom Client an den Server werden über Azure AD unter Verwendung von OAuth authentifiziert und autorisiert. Nutzer mit gültigen Anmeldeinformationen, die von einem Verbundpartner ausgestellt wurden, sind vertrauenswürdig und durchlaufen denselben Prozess wie native Benutzer. Weitere Einschränkungen können jedoch von Administratoren eingeführt werden.

Für die Medienauthentifizierung verwenden die ICE- und TURN-Protokolle auch die Digest-Challenge, wie im IETF TURN RFC beschrieben.

### <a name="windows-powershell-and-team-management-tools"></a>Windows PowerShell- und Team-Verwaltungstools

In Microsoft Teams können IT-Administratoren ihren Dienst über das Microsoft 365 Admin Center oder mithilfe von Tenant Remote PowerShell (TRPS) verwalten. Mandantenadministratoren verwenden die moderne Authentifizierung, um sich bei TRPS zu authentifizieren.

### <a name="configuring-access-to-teams-at-your-internet-boundary"></a>Konfigurieren des Zugriffs auf Microsoft Teams an Ihrer Internetgrenze

Damit Teams ordnungsgemäß funktioniert, sodass Benutzer beispielsweise an Besprechungen teilnehmen können, müssen Kunden ihren Internetzugang so konfigurieren, dass ausgehender UDP- und TCP-Datenverkehr zu Diensten in der Teams-Cloud zulässig ist. Weitere Informationen finden Sie unter [Office 365-URLs und -IP-Adressbereiche](/office365/enterprise/urls-and-ip-address-ranges).

### <a name="udp-3478-3481-and-tcp-443"></a>UDP 3478-3481 und TCP 443

Die Ports UDP 3478-3481 und TCP 443 werden von Clients verwendet, um einen Dienst für audiovisuelle Medien anzufordern. Ein Client verwendet diese beiden Ports, um UDP- bzw. TCP-Ports zuzuweisen und diese Medienflüsse zu aktivieren. Die Medienflüsse an diesen Ports sind mit einem Schlüssel geschützt, der über einen TLS-geschützten Signalisierungskanal ausgetauscht wird.

### <a name="federation-safeguards-for-teams"></a>Verbundsschutz für Microsoft Teams

Verbund bietet Ihrer Organisation die Möglichkeit, mit anderen Organisationen zu kommunizieren, um einen Chat und Präsenz zu teilen. In Teams ist der Verband standardmäßig aktiviert. Mandantenadministratoren können dies jedoch über das Microsoft 365 Admin Center steuern.

## <a name="addressing-threats-to-teams-meetings"></a>Umgang mit Bedrohungen für Microsoft Teams-Besprechungen

Es gibt zwei Möglichkeiten zu steuern, wer an Teams-Besprechungen teilnimmt und wer Zugriff auf die von Ihnen präsentierten Informationen hat.

1. Sie können steuern, wer an Ihren Besprechungen teilnimmt, indem Sie Einstellungen für die **Lobby** vornehmen.</p>

    |Optionen für die Einstellung "Wer kann den Wartebereich umgehen" auf der Seite Besprechungsoptionen   |Benutzertypen, die direkt an der Besprechung teilnehmen  |Benutzertypen, die in den Wartebereich wechseln   |
    |---------|---------|---------|
    |Personen in meinem Unternehmen     |  – Benutzer innerhalb des Mandanten  </br>– Gast des Mandanten         |  – Verbundbenutzer</br>  – Anonyme Benutzer</br>  – Einwahl über Telefonfestnetz</br>     |
    |Personen in meiner Organisation und vertrauenswürdigen Organisationen      |  – Benutzer innerhalb des Mandanten</br> – Gast des Mandanten</br> – Verbundbenutzer</br>        |  – Anonyme Benutzer</br>  – Einwahl über Telefonfestnetz</br>      |
    |Jeder      |   – Benutzer innerhalb des Mandanten</br>  – Gast des Mandanten</br>  – Anonymer Benutzer im Verbund</br>  – Einwahl über Telefonfestnetz</br>       |         |

2. Der zweite Weg führt über **strukturierte Besprechungen** (bei denen Moderatoren alles tun können, was getan werden sollte, und die Teilnehmer haben eine kontrollierte Erfahrung). Nach der Teilnahme an einer strukturierten Besprechung steuern die Moderatoren, was die Teilnehmer in der Besprechung tun können. </p>

    |Aktionen  |Moderatoren  |Teilnehmer  |
    |---------|---------|---------|
    |Sprechen Sie und teilen Sie ihr Video     |   J      |   J      |
    |Nehmen Sie am Besprechung-Chat teil     |   J    |    J     |
    |Ändern Sie die Einstellungen in den Besprechungsoptionen     |   J      |  N       |
    |Andere Teilnehmer stumm schalten| J | N |
    |Andere Teilnehmer entfernen      |  J       |   N      |
    |Inhalte freigeben     |     J    |     N    |
    |Andere Teilnehmer aus der Lobby aufnehmen|  J       |   N      |
    |Andere Teilnehmer zu Moderatoren oder Teilnehmern machen     |   J      | N        |
    |Aufnahme starten oder stoppen     |     J    |    N     |
    |Übernehmen Sie die Kontrolle, wenn ein anderer Teilnehmer ein PowerPoint teilt     |  J         | N        |

Teams bietet Unternehmensbenutzern die Möglichkeit, Besprechungen in Echtzeit zu erstellen und daran teilzunehmen. Enterprise-Benutzer können auch externe Benutzer zur Teilnahme an diesen Besprechungen einladen, die nicht über ein Azure AD-, Microsoft 365- oder Office 365-Konto verfügen. Nutzer, die bei externen Partnern mit einer sicheren und authentifizierten Identität beschäftigt sind, können ebenfalls an Besprechungen teilnehmen und, wenn sie dazu gemacht werden, als Moderatorenn fungieren. Anonyme Benutzer können keine Besprechungen als Moderator erstellen oder ihnen beitreten. Sie können jedoch nach ihrem Beitritt zum Moderator ernannt werden.

Damit anonyme Nutzer an Teambesprechungen teilnehmen können, muss die Einstellung für Teilnehmerbesprechungen im Teams Admin Center aktiviert sein.

> [!NOTE]
> Der Begriff *anonyme Nutzer* bezeichnet Nutzer, die nicht beim Mandanten der Organisation authentifiziert sind. In diesem Zusammenhang gelten alle externen Nutzer als anonym. Zu den authentifizierten Nutzern gehören Mandantenbenutzer und Gastbenutzer des Mandanten.

Die Teilnahme externer Benutzer an Microsoft Teams-Besprechungen ermöglichen kann nützlich sein, birgt jedoch einige Sicherheitsrisiken. Um diesen Risiken zu begegnen, werden in Microsoft Teams die folgenden Schutzmaßnahmen verwendet:

- Teilnehmerrollen bestimmen die Berechtigungen zur Besprechungssteuerung.
- Mit den Teilnehmertypen können Sie den Zugriff auf bestimmte Besprechungen beschränken.
- Das Planen von Besprechungen ist auf Nutzer beschränkt, die über ein AAD-Konto und eine Teams-Lizenz verfügen.
- Anonyme, dh. nicht authentifizierte Nutzer, die an einer Einwahlkonferenz teilnehmen möchten, wählen eine der Konferenzzugriffsnummern. Wenn die Einstellung "Anrufern immer erlauben, die Lobby zu umgehen" *aktiviert* ist, müssen sie auch warten, bis ein Moderator oder ein authentifizierter Benutzer an der Besprechung teilnimmt.

  > [!CAUTION]
  > Wenn Sie nicht möchten, dass anonyme Benutzer (nicht explizit eingeladene Benutzer) an einer Besprechung teilnehmen, müssen Sie sicherstellen, dass die Option **Anonyme Benutzer können an einer Besprechung teilnehmen** für den Besprechungsabschnitt **Teilnehmer** auf **Aus** festgelegt ist.

Ein Organisator kann auch Einstellungen konfigurieren, damit Einwählanrufer die erste Person in einer Besprechung sind. Diese Einstellung wird in den Audiokonferenzeinstellungen für Nutzer konfiguriert und gilt für alle vom Nutzer geplanten Besprechungen.

> [!NOTE]
> Weitere Informationen zum Gast- und externen Zugriff in Teams finden Sie in diesem[Artikel](./communicate-with-users-from-other-organizations.md). Es wird erläutert, welche Funktionen Gast- oder externe Nutzer erwarten können, wenn sie sich bei Teams anmelden. <p> Wenn Sie Besprechungen aufzeichnen und eine Berechtigungsmatrix für den Zugriff auf die Inhalte anzeigen möchten, lesen Sie [diesen Artikel](./tmr-meeting-recording-change.md) und dessen Matrix.

### <a name="participant-roles"></a>Teilnehmerrollen

Die Besprechungsteilnehmer gliedern sich in drei Gruppen mit jeweils eigenen Privilegien und Einschränkungen:

- **Organisator** Der Nutzer, der ein Besprechung erstellt, sei es spontan oder durch Terminplanung. Ein Organisator muss ein authentifizierter Mandantenbenutzer sein und die Kontrolle über alle Endbenutzeraspekte einer Besprechungen haben.
- **Moderator** Ein Nutzer, der berechtigt ist, Informationen in einer Besprechung zu präsentieren, unabhängig davon, welches Medium unterstützt wird. Ein Besprechungsorganisator ist per Definition auch ein Referent und bestimmt, wer sonst noch ein Referent sein kann. Ein Organisator kann diese Entscheidung treffen, wenn eine Besprechung geplant ist oder während die Besprechung stattfindet.
- **Teilnehmer** Ein Nutzer, der zu einer Besprechung eingeladen wurde, aber nicht berechtigt ist, als Moderator zu fungieren.

Ein Referent kann auch einen Teilnehmer während der Besprechung für die Rolle des Referenten befördern.

### <a name="participant-types"></a>Teilnehmertypen

Die Besprechungsteilnehmer werden auch nach Aufenthaltsort und Anmeldeinformationen kategorisiert. Mit diesen beiden Merkmalen können Sie entscheiden, welche Nutzer Zugriff auf bestimmte Besprechungen haben. Nutzer können grob in die folgenden Kategorien unterteilt werden:

- **Benutzer, die zum Mandanten gehören**. Diese Benutzer verfügen über Anmeldeinformationen in Azure Active Directory für den Mandanten.

    *Personen in meiner Organisation* – Diese Nutzer verfügen über Anmeldeinformationen in Azure Active Directory für den Mandanten. Zu den *Personen in meiner Organisation* gehören eingeladene Gastkonten.

    *Remotebenutzer* – Diese Nutzer treten von außerhalb des Unternehmensnetzwerks bei. Dazu gehören Mitarbeiter, die zu Hause oder unterwegs arbeiten, und andere, wie Mitarbeiter von vertrauenswürdigen Anbietern, denen für ihre Vertragsbedingungen ein Unternehmenszertifikat erteilt wurde. Remotebenutzer können Besprechungen erstellen und daran teilnehmen und als Moderatoren fungieren.

- **Benutzer, die nicht zum Mandanten gehören**. Diese Benutzer haben keine Anmeldeinformationen in Azure AD für den Mandanten.

    *Verbundbenutzer* – Verbundbenutzer verfügen über gültige Anmeldeinformationen bei Verbundpartnern und werden daher von Teams als authentifiziert behandelt, sind jedoch für den Mandanten des Besprechungsorganisators weiterhin extern. Verbundbenutzer können an Besprechungen teilnehmen und nach der Teilnahme an der Besprechung zu Moderatoren gemacht werden. Sie können jedoch keine Besprechungen in Unternehmen erstellen, mit denen sie verbunden sind.

    *Anonyme Nutzer* – Anonyme Nutzer haben keine Active Directory-Identität und sind nicht mit dem Mandanten verbunden.

An vielen Besprechungen sind externe Nutzer beteiligt. Dieselben Kunden möchten auch die Identität externer Nutzer bestätigen, bevor diese Nutzer an einer Besprechung teilnehmen können. Im nächsten Abschnitt wird beschrieben, wie Teams den Zugriff auf Besprechungen durch diejenigen Benutzertypen beschränkt, die explizit zugelassen wurden, und dass alle Benutzertypen beim Beitreten einer Besprechung die entsprechenden *Anmeldeinformationen* vorlegen müssen.

### <a name="participant-admittance"></a>Zulassung von Teilnehmern

> [!CAUTION]
> Wenn Sie nicht möchten, dass anonyme Benutzer (nicht explizit eingeladene Benutzer) an einer Besprechung teilnehmen, müssen Sie sicherstellen, dass die Option **Anonyme Benutzer können an einer Besprechung teilnehmen** für den Besprechungsabschnitt **Teilnehmer** auf **Aus** festgelegt ist.

In Teams können anonyme Nutzer in einen Wartebereich namens Lobby versetzt werden. Moderatoren können diese Nutzer dann entweder in die Besprechung *aufnehmen* oder *ablehnen*. Wenn diese Nutzer in die Lobby übertragen werden, werden der Moderator und die Teilnehmer benachrichtigt, und die anonymen Nutzer müssen warten, bis sie entweder akzeptiert oder abgelehnt werden oder ihre Verbindung abläuft.

Standardmäßig gehen Teilnehmer, die sich über das PSTN einwählen, direkt zur Besprechung, sobald ein authentifizierter Nutzer der Besprechung beitritt. Diese Option kann jedoch geändert werden, um Einwahlteilnehmer zum Betreten der Lobby zu zwingen.

Besprechungsorganisatoren steuern, ob Teilnehmer an einer Besprechung teilnehmen können, ohne in der Lobby zu warten. Jede Besprechung kann so eingerichtet werden, dass der Zugriff mit einer der folgenden Methoden möglich ist:

Die Standardeinstellungen sind:

- *Personen in meiner Organisation* – Jeder außerhalb der Organisation wartet in der Lobby, bis er zugelassen wird.
- *Personen in meiner Organisation, vertrauenswürdige Organisationen und Gäste* – Authentifizierte Benutzer innerhalb der Organisation, einschließlich Gastbenutzer und Benutzer aus vertrauenswürdigen Organisationen, treten der Besprechung direkt bei, ohne im Wartebereich warten zu müssen. Anonyme Benutzer müssen im Wartebereich warten.
- *Jeder* – Alle Besprechungsteilnehmer umgehen die Lobby, sobald ein authentifizierter Nutzer der Besprechung beigetreten ist.

### <a name="presenter-capabilities"></a>Moderatorfunktionen

Die Organisatoren der Besprechung kontrollieren, ob die Teilnehmer während einer Besprechung anwesend sein können. Jede Besprechung kann so eingerichtet werden, dass die Moderatoren auf einen der folgenden Punkte beschränkt sind:

- *Personen in meiner Organisation* – Alle Mandanten, einschließlich Gäste, können präsentieren
- *Personen in meiner Organisation und vertrauenswürdige Organisationen* – Alle Mandantenbenutzer, einschließlich Gäste, können präsentieren, und externe Nutzer aus Microsoft Teams und Skype for Business-Domänen, die in der Liste der externen Zugriffsberechtigungen aufgeführt sind, können präsentieren.  
- *Jeder* – Alle Besprechungsteilnehmer sind Moderatoren.

### <a name="modify-while-meeting-is-running"></a>Änderungen während der Besprechung

Es ist möglich, die Besprechungsoptionen zu ändern, während eine Besprechung läuft. Wenn die Änderung gespeichert wird, wirkt sie sich innerhalb von Sekunden auf die laufende Besprechung aus. Dies wirkt sich auch auf alle zukünftigen Vorkommen der Besprechung aus.

## <a name="related-topics"></a>Verwandte Themen

[Die wichtigsten 12 Aufgaben für Sicherheitsteams zur Unterstützung der Arbeit von zu Hause aus](/microsoft-365/security/top-security-tasks-for-remote-work)

[Microsoft Trust Center](https://microsoft.com/trustcenter)

[Verwalten von Besprechungseinstellungen in Microsoft Teams](./meeting-settings-in-teams.md)

[Optimieren der Microsoft 365- oder Office 365-Konnektivität für Remotebenutzer mithilfe des geteilten VPN-Tunnels](/Office365/Enterprise/office-365-vpn-split-tunnel)

- [Implementieren eines geteilten VPN-Tunnels](/Office365/Enterprise/office-365-vpn-implement-split-tunnel)

[Besprechungsaufzeichnungen in Teams, wo Aufzeichnungen gespeichert werden und wer darauf zugreifen kann](./tmr-meeting-recording-change.md)
