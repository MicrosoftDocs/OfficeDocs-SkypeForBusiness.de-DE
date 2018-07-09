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
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Security
description: Sicherheitsleitfaden für Skype for Business Online <add description>
ms.openlocfilehash: 4d379a827b5dde8780d017834fd0ef011f2055eb
ms.sourcegitcommit: abc0f95ef0efe15a8c38cc27a3991abf7480c30e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2018
ms.locfileid: "20211126"
---
#  <a name="security-and-skype-for-business-online"></a>Sicherheit und Skype for Business Online

Skype für Business Online (SfBO), als Teil des Office 365-Dienstes, befolgt alle bewährte Methoden und Verfahren für die Sicherheit, wie z. B. Sicherheit auf Leistungsebene durch umfassende Abwehrmaßnahmen, Kundenkontrolle innerhalb des Dienstes, Sicherheitshärtung und betriebliche Best Practices.  Weitere Informationen finden Sie im Office 365 Trust Center (https://products.office.com/en-us/business/office-365-trust-center-security).

## <a name="trustworthy-by-design"></a>Zuverlässig durch Design
Skype for Business Online wurde in Übereinstimmung mit dem Microsoft Trustworthy Computing Security Development Lifecycle (SDL) entwickelt, der unter https://www.microsoft.com/en-us/sdl/default.aspx beschrieben wird. Der erste Schritt beim Erstellen eines sicheren Unified Communications-Systems bestand in der Entwicklung von Gefahrenmodellen und im Testen jedes einzelnen Features während seines Entwurfs. Viele sicherheitsrelevante Verbesserungen wurden während der Codephase getestet und integriert. Mit Buildzeittools werden Pufferüberläufe und andere potenzielle Sicherheitsbedrohungen erkannt, bevor der Code in das Endprodukt übernommen wird. Natürlich ist es nicht möglich, so zu entwerfen, dass alle unbekannten Sicherheitsbedrohungen beseitigt werden. Es gibt kein System, für das vollständige Sicherheit garantiert werden kann. Da bei der Produktentwicklung jedoch von Anfang an sichere Designprinzipien angewendet wurden, umfasst Skype for Business Online die branchenüblichen Standard-Sicherheitstechnologien als grundlegenden Bestandteil seiner Architektur. 

## <a name="trustworthy-by-default"></a>Vertrauenswürdig durch seine Standardeinstellungen
Die Netzwerkkommunikation in Skype for Business Online ist standardmäßig verschlüsselt. Da alle Server-Zertifikate verwenden müssen und OAUTH, TLS, Secure Real-Time Transport Protocol (SRTP) und andere branchenübliche Verschlüsselungstechniken, einschließlich der 256-Bit Advanced Encryption Standard (AES)-Verschlüsselung einsetzen, sind alle Skype for Business Online-Daten im Netzwerk geschützt.

## <a name="how-sfbo-handles-common-security-threats"></a>So geht SfBO mit allgemeinen Sicherheitsbedrohungen um
Dieser Abschnitt beschreibt die häufigsten Bedrohungen für die Sicherheit des SfBO-Dienstes und wie Microsoft jede Bedrohung entschärft.

### <a name="compromised-key-attack"></a>Angriff mit kompromittierten Schlüsseln
Ein Schlüssel ist ein geheimer Code oder eine geheime Nummer zur Verschlüsselung, Entschlüsselung oder Überprüfung geheimer Informationen. In der Public-Key-Infrastruktur (PKI) werden zwei sensible Schlüssel verwendet, die berücksichtigt werden müssen: der private Schlüssel, den jeder Zertifikatsinhaber besitzt, und der Sitzungsschlüssel, der nach einer erfolgreichen Identifizierung und dem Austausch von Sitzungsschlüsseln durch die kommunizierenden Partner verwendet wird.  Ein Angriff mit kompromittierten Schlüsseln liegt vor, wenn der Angreifer den privaten Schlüssel oder den Sitzungsschlüssel ermittelt. Gelingt dem Angreifer die Ermittlung des Schlüssels, kann er den Schlüssel zum Entschlüsseln verschlüsselter Daten ohne Wissen des Absenders verwenden.

Skype for Business Online verwendet die PKI-Funktionen des Windows Server-Betriebssystems, um die für die Verschlüsselung für TLS-Verbindungen (Transport Layer Security) verwendeten Schlüsseldaten zu schützen. Die für die Medienverschlüsselung verwendeten Schlüssel werden über TLS-Verbindungen ausgetauscht. 

### <a name="network-denial-of-service-attack"></a>Denial-of-Service-Angriff auf das Netzwerk
Ein Denial-of-Service-Angriff liegt vor, wenn der Angreifer die normale Netzwerknutzung durch gültige Nutzer verhindert. Bei einem Denial-of-Service-Angriff eröffnen sich den Angreifern folgende Möglichkeiten:
- Er kann ungültige Daten an Anwendungen und Dienste senden, die in dem angegriffenen Netzwerk ausgeführt werden, um ihre Funktionsweise zu beeinträchtigen.
- Er kann große Datenmengen senden, um das System zu überlasten, bis es nicht mehr oder nur noch verzögert auf legitime Anforderungen reagiert.
- Er kann die Spuren seines Angriffs vertuschen.
- Er kann Benutzer vom Zugriff auf die Netzwerkressourcen abhalten.

SfBO mildert diese Angriffe, indem es den Azure DDOS-Netzwerkschutz ausführt und Client-Anforderungen von denselben Endpunkten, Subnetzen und Verbundentitäten einschränkt.

### <a name="eavesdropping"></a>Abhörschutz
Abhöraktionen sind Aktionen, bei denen sich Angreifer Zugriff auf den Datenpfad in einem Netzwerk verschaffen und anschließend den Datenverkehr überwachen und lesen können. Dies wird auch als „Schnüffeln“ (auch „Lauschangriff“, englisch Sniffing oder Snooping) bezeichnet. Wenn der Datenverkehr aus reinem Text besteht, können Angreifer ihn lesen, sobald sie Zugriff auf den Pfad haben. Ein Beispiel wäre ein Angriff, bei dem ein Router auf dem Datenpfad kontrolliert wird. 

SfBO verwendet gegenseitiges TLS (MTLS) für die Serverkommunikation innerhalb von O365 und TLS von den Clients zum Dienst, wodurch dieser Angriff innerhalb der Zeitspanne, in der eine bestimmte Konversation angegriffen werden könnte, sehr schwierig bis unmöglich wird. Mit TLS werden alle Parteien authentifiziert und der gesamte Datenverkehr wird verschlüsselt. Damit können Abhöraktionen nicht verhindert werden, aber Angreifer können den Datenverkehr nicht lesen, es sei denn, die Verschlüsselung geht verloren.

Das TURN-Protokoll wird für Echtzeit-Medienzwecke verwendet.  Das TURN-Protokoll schreibt keine Verschlüsselung des Datenverkehrs vor, und die von ihm gesendeten Informationen sind durch die Nachrichtenintegrität geschützt. Obwohl es für Lauschangriffe offen ist, können die von ihm gesendeten Informationen (d. h. IP-Adressen und Port) direkt extrahiert werden, indem man einfach die Quell- und Zieladressen der Pakete betrachtet. Der SfBO-Service stellt sicher, dass die Daten gültig sind, indem er die Nachrichtenntegrität der Nachricht anhand des Schlüssels überprüft, der aus einigen wenigen Elementen einschließlich eines TURN-Kennworts abgeleitet wurde, das niemals im Klartext gesendet wird. SRTP wird für den Medienverkehr verwendet und ist ebenfalls verschlüsselt.

### <a name="identity-spoofing-ip-address-spoofing"></a>Identitätsvortäuschung (Spoofing der IP-Adresse)
Spoofing liegt vor, wenn Angreifer unbefugt die IP-Adresse eines Netzwerks, Computers oder einer Netzwerkkomponente ermitteln und verwenden. Nach einem erfolgreichen Angriff können sich Angreifer als die normalerweise durch diese IP-Adresse identifizierte Entität ausgeben. Im Rahmen des Microsoft Lync Servers 2010 kommt diese Situation nur vor, wenn ein Administrator die folgenden beiden Aktionen ausgeführt hat:
- Er hat Verbindungen konfiguriert, die nur TCP (Transmission Control Protocol) unterstützen. (Dies ist nicht zu empfehlen, da die TCP-Kommunikation unverschlüsselt ist.)
- Er hat die IP-Adressen dieser Verbindungen als vertrauenswürdige Hosts markiert. 

Dies ist für TLS-Verbindungen (Transport Layer Security) weniger ein Problem, da TLS alle Parteien authentifiziert und den gesamten Datenverkehr verschlüsselt. Die Verwendung von TLS verhindert Spoofingangriffe auf bestimmte Verbindungen (Mutual TLS-Verbindungen). Jedoch könnte ein Angreifer die Adresse des von SfBO verwendeten DNS-Servers immer noch durch Spoofing ermitteln. Da die Authentifizierung in SfBO jedoch mittels Zertifikaten erfolgt, verfügen Angreifer nicht über ein gültiges Zertifikat, das für das Spoofing für eine der Kommunikationsparteien notwendig ist.

### <a name="man-in-the-middle-attack"></a>Man-in-the-Middle-Angriff
Von einem „Man-in-the-Middle-Angriff“ spricht man, wenn Angreifer die Kommunikation zwischen zwei Nutzern ohne deren Wissen über ihren eigenen Computer leiten. Die Angreifer können die übertragenen Daten überwachen und lesen, ehe sie an den eigentlichen Empfänger weitergeleitet werden. Beide Kommunikationspartner senden unwissentlich Daten an die Angreifer und empfangen von ihnen Daten, sind aber dabei in dem Glauben, ausschließlich mit der beabsichtigten Person zu kommunizieren. Dies kann passieren, wenn es Angreifern gelingt, die Active Directory-Domänendienste so zu ändern, dass ihr Server als vertrauenswürdiger Server hinzugefügt wird, oder wenn sie den DNS-Eintrag (Domain Name System) so ändern können, dass Clients auf ihrem Weg zum Server über den Computer der Angreifer geleitet werden. 

Ein Man-in-the-Middle-Angriff kann auch bei Medienverkehr zwischen zwei Clients auftreten, außer dass in SfBO Punkt-zu-Punkt Audio-, Video- und Application-Sharing-Streams mit SRTP verschlüsselt werden, wobei kryptographische Schlüssel verwendet werden, die zwischen den Peers über das Session Initiation Protocol (SIP) über TLS ausgehandelt werden. 

### <a name="rtp-replay-attack"></a>Angriff mit Aufzeichnungswiederholung (RTP-Datenverkehr)
Ein Replay-Angriff liegt vor, wenn eine gültige Medienübertragung zwischen zwei Parteien abgefangen und für böswillige Zwecke erneut übertragen wird. SfBO verwendet SRTP in Verbindung mit einem sicheren Signalisierungsprotokoll, das Übertragungen vor Replay-Angriffen schützt, indem es dem Empfänger ermöglicht, einen Index der bereits empfangenen RTP-Pakete zu führen und jedes neue Paket mit den bereits im Index aufgeführten zu vergleichen.

### <a name="spim"></a>SPIM (Spam over Instant Messaging)
Unter SPIM sind unaufgeforderte Werbe-SMS oder Anwesenheitsabonnementanforderungen zu verstehen. Zwar wird das Netzwerk nicht unmittelbar beeinträchtigt, doch ist SPIM zumindest ärgerlich, kann die Ressourcenverfügbarkeit und die Produktivität reduzieren und möglicherweise zu einer Beeinträchtigung des Netzwerks führen. Ein Beispiel für Spimming sind Nutzer, die sich gegenseitig Anfragen zusenden. Nutzer können sich gegenseitig blockieren, um dies zu verhindern. Ein koordinierter Spimangriff im Partnerverbund kann jedoch schwer abzuwehren sein, wenn Sie den Verbund für den Partner nicht deaktivieren.

### <a name="viruses-and-worms"></a>Viren und Würmer
Ein Virus ist eine Codeeinheit, deren Zweck die Reproduktion zusätzlicher, ähnlicher Codeeinheiten ist. Ein Virus benötigt, um zu funktionieren, einen Host, z. B. eine Datei, eine E-Mail oder ein Programm. Ähnlich wie ein Virus ist ein Wurm eine Codeeinheit, die für die Reproduktion zusätzlicher, ähnlicher Codeeinheiten codiert ist, aber im Gegensatz zu einem Virus keinen Wirt benötigt. Viren und Würmer treten vor allem bei Dateiübertragungen zwischen Clients oder beim Versenden von URLs von anderen Benutzern auf. Wenn sich ein Virus auf Ihrem Computer befindet, kann er beispielsweise Ihre Identität verwenden und Sofortnachrichten in Ihrem Namen versenden.  Standardmäßige bewährte Methoden für die Client-Sicherheit, wie z. B. die regelmäßige Überprüfung auf Viren, können dieses Problem entschärfen.  

## <a name="personally-identifiable-information"></a>Informationen zur Identifikation von Personen
In SfBO werden potenziell Informationen über ein öffentliches Netzwerk offengelegt, die u. U. direkt mit einer Person in Zusammenhang gebracht werden können. Bei diesen Informationen kann es sich um zwei Kategorien von Angaben handeln:
- **Erweiterte Anwesenheitsdaten**&nbsp;&nbsp;&nbsp;Erweiterte Anwesenheitsdaten sind Informationen, die ein Benutzer über einen Link zu einem Partner im Verbund oder mit Kontakten innerhalb einer Organisation freigeben oder nicht freigeben kann. Diese Daten werden nicht an Benutzer in einem öffentlichen IM-Netzwerk weitergegeben. Client-Richtlinien und andere Client-Konfigurationen können dem Systemadministrator eine gewisse Kontrolle verschaffen. Im SfBO-Dienst kann der erweiterte vertrauliche Anwesenheitsmodus für einen einzelnen Benutzer konfiguriert werden, um zu verhindern, dass SfBO-Benutzer, die nicht in der Kontaktliste des Benutzers aufgeführt sind, die Anwesenheitsinformationen des Benutzers sehen. 
- **Pflichtdaten**&nbsp;&nbsp;&nbsp;Pflichtdaten sind Daten, die für den ordnungsgemäßen Betrieb des Servers oder des Clients benötigt werden. Es handelt sich um Informationen, die auf Server- oder Netzwerkebene für das Routing, die Statuspflege und die Signalübermittlung erforderlich sind.
Die folgenden Tabellen listen die Daten auf, die für den Betrieb von SfBO benötigt werden.

***Tabelle 1 - Erweiterte Anwesenheitsdaten***

<!--start table here -->

||||
|:-----|:-----|:-----|
|**Daten**|**Mögliche** **Einstellungen**|
|Persönliche Daten |Name, Titel, Unternehmen, E-Mail-Adresse, Zeitzone|
|Telefonnummern|Geschäftlich, mobil, privat|
|Kalenderdaten|Frei/Besetzt, Abwesenheitsmitteilung, Besprechungsdetails (für Personen mit Zugriff auf Ihren Kalender)| 
|Anwesenheitsstatus|Abwesend, verfügbar, gebucht, nicht stören, offline|
|||||

<!-- end of table -->

***Tabelle 2 - Plichtdaten***

<!--start table here -->

||||
|:-----|:-----|:-----|
|**Kategorie** |**Mögliche Einstellungen** |
|IP-Adresse|Tatsächliche Computer- oder NAT-Adresse|
|SIP-URI|<u>david.campbell@contoso.com</u>|
|Name|David Campbell (wie in Active Directory Domain Services definiert)|
|||||

<!-- end of table -->

## <a name="security-framework-for-sfbo"></a>Sicherheitsframework für SfBO
Dieser Abschnitt enthält eine Übersicht über die grundlegenden Elemente, die das Sicherheitsframework für SfBO bilden. Es handelt sich um die folgenden Elemente:
- Azure Active Directory (AAD) bietet ein einziges vertrauenswürdiges Back-End-Repository für Benutzerkonten. 
- Die Public-Key-Infrastruktur (PKI) verwendet zum Authentifizieren des Servers und Sichern der Datenintegrität von vertrauenswürdigen Zertifizierungsstellen ausgestellte Zertifikate.
- Transport Layer Security (TLS), HTTPS über SSL (HTTPS) und Mutual TLS (MTLS) ermöglichen die Endpunktauthentifizierung und IM-Verschlüsselung. Punkt-zu-Punkt-Audio-, Video- und Streams für die Anwendungsfreigabe werden über SRTP (Secure Real-Time Transport Protocol) verschlüsselt.
- Branchenstandardprotokolle für die Benutzerauthentifizierung, falls möglich.

Die einzelnen Themen in diesem Abschnitt beschreiben, wie all diese grundlegenden Elemente funktionieren, um die Sicherheit Ihrer SfBO-Dienste zu verbessern.

### <a name="azure-active-directory"></a>Azure Active Directory
Azure Active Directory fungiert als Verzeichnisdienst für O365. Es speichert alle Benutzerverzeichnisinformationen und Richtlinienzuweisungen. 

### <a name="public-key-infrastructure-for-sfbo"></a>Public-Key-Infrastruktur für SfBO
SfBO-Dienste nutzen Zertifikate für die Serverauthentifizierung und die Einrichtung einer Vertrauenskette zwischen Clients und Servern und zwischen den verschiedenen Serverfunktionen. Die Windows Server Public-Key-Infrastruktur (PKI) stellt die Infrastruktur für den Aufbau und die Validierung dieser Vertrauenskette zur Verfügung.
Zertifikate sind digitale IDs. Sie identifizieren einen Server nach Namen und geben seine Eigenschaften an. Um sicherzustellen, dass die Informationen auf einem Zertifikat gültig sind, muss das Zertifikat von einer Zertifizierungsstelle ausgegeben sein, die für Clients und andere Server, die sich mit dem Server verbinden, vertrauenswürdig ist. Wenn sich der Server nur mit anderen Clients und Servern in einem privaten Netzwerk verbindet, kann die Zertifizierungsstelle eine Unternehmenszertifizierungsstelle sein. Wenn der Server mit Entitäten außerhalb des privaten Netzwerks interagiert, ist möglicherweise eine öffentliche Zertifizierungsstelle erforderlich.

Selbst wenn die Informationen auf dem Zertifikat gültig sind, muss es eine Möglichkeit zum Überprüfen geben, ob der Server, der das Zertifikat präsentiert, tatsächlich der Server ist, der von dem Zertifikat repräsentiert wird. Hier kommt die Windows PKI ins Spiel.
Jedes Zertifikat ist mit einem öffentlichen Schlüssel verbunden. Der auf dem Zertifikat benannte Server verfügt über einen entsprechenden privaten Schlüssel, der nur ihm bekannt ist. Ein sich verbindender Client oder Server verwendet den öffentlichen Schlüssel, um eine beliebige Information zu verschlüsseln und sendet diese an den Server. Wenn der Server die Information entschlüsselt und als Klartext zurückgibt, kann die sich verbindende Entität sicher sein, dass der Server über den privaten Schlüssel zum Zertifikat verfügt und es sich daher um den auf dem Zertifikat benannten Server handelt.

#### <a name="crl-distribution-points"></a>Sperrlisten-Verteilungspunkte
SfBO erfordert, dass alle Serverzertifikate mindestens einen Sperrlisten-Verteilungspunkt (CRL) enthalten. Sperrlisten-Verteilungspunkte sind Standorte, von denen Zertifikatsperrlisten heruntergeladen werden können, um zu prüfen, ob das Zertifikat seit dem Zeitpunkt, an dem es ausgestellt wurde, gesperrt wurde und es sich noch im Gültigkeitszeitraum befindet. Ein Sperrlisten (CRL)-Verteilungspunkt wird in den Eigenschaften des Zertifikats als URL aufgeführt und ist ein sicheres HTTP.  Der SfBO-Dienst prüft die Sperrliste bei jeder Zertifikatsauthentifizierung.

#### <a name="enhanced-key-usage"></a>Erweiterte Schlüsselverwendung
Alle Komponenten des SfBO-Dienstes benötigen alle Serverzertifikate zur Unterstützung der erweiterte Schlüsselverwendung (EKU) zum Zwecke der Serverauthentifizierung. Die Konfiguration des EKU-Felds für die Serverauthentifizierung bedeutet, dass das Zertifikat für den Zweck der Serverauthentifizierung gültig ist. Diese EKU ist wesentlich für MTLS. 

### <a name="tls-and-mtls-for-sfbo"></a>TLS und MTLS für SfBO
Die Protokolle TLS und MTLS bieten verschlüsselte Kommunikation und Endpunkt-Authentifizierung im Internet. SfBO verwendet diese beiden Protokolle, um das Netzwerk vertrauenswürdiger Server zu erstellen und sicherzustellen, dass die gesamte Kommunikation über dieses Netzwerk verschlüsselt ist. Die gesamte SIP-Kommunikation zwischen Servern findet über MTLS statt. SIP-Kommunikation vom Client zum Server findet über TLS statt.

Mit TLS können Benutzer über ihre Clientsoftware die SfBO-Server authentifizieren, mit denen sie sich verbinden. In einer TLS-Verbindung fordert der Client ein gültiges Zertifikat vom Server an. Damit das Zertifikat gültig ist, muss es von einer Zertifizierungsstelle ausgestellt sein, die auch für den Client vertrauenswürdig ist, und der DNS-Name des Servers muss dem DNS-Namen auf dem Zertifikat entsprechen. Wenn das Zertifikat gültig ist, verwendet der Client den öffentlichen Schlüssel im Zertifikat, um die symmetrischen Verschlüsselungsschlüssel, die für die Kommunikation verwendet werden, zu verschlüsseln, sodass nur der ursprüngliche Eigentümer des Zertifikats seinen privaten Schlüssel für die Entschlüsselung der Inhalte der Kommunikation verwenden kann. Die daraus resultierende Verbindung ist vertrauenswürdig und wird von diesem Punkt an nicht von anderen vertrauenswürdigen Servern oder Clients angezweifelt. In diesem Zusammenhang kann Secure Sockets Layer (SSL) bei der Verwendung mit Webdiensten als TLS-basiert zugeordnet werden.

Server-zu-Server-Verbindungen basieren auf gegenseitigem TLS (MTLS) zur gegenseitigen Authentifizierung. Bei einer MTLS-Verbindung tauschen der Server, von dem eine Nachricht stammt, und der Server, der diese empfängt, Zertifikate von einer beiderseits vertrauenswürdigen Zertifizierungsstelle aus. Die Zertifikate beweisen jedem Server die Identität des anderen. Im SfBO-Dienst wird diese Prozedur befolgt.

TLS und MTLS verhindern Lauschangriffe und Man-in-the-Middle-Angriffe. Ein Man-in-the-Middle-Angriff leitet die Kommunikation zwischen zwei Netzwerkeinheiten ohne Wissen einer der beiden Parteien über den Computer des Angreifers um. Die Spezifikation von TLS und SfBO für vertrauenswürdige Server verringern das Risiko eines Man-in-the-Middle-Angriffs teilweise mithilfe der Verwendung einer End-to-End-Verschlüsselung auf der Anwendungsebene, die mithilfe der Public Key-Kryptografie zwischen den beiden Endpunkten koordiniert wird, und ein Angreifer müsste über ein gültiges und vertrauenswürdiges Zertifikat mit dem entsprechenden privaten Schlüssel verfügen und auf den Namen des Dienstes ausgestellt sein, an den der Client kommuniziert, um die Kommunikation zu entschlüsseln. 

### <a name="encryption-for-sfbo"></a>Verschlüsselung für SfBO
SfBO verwendet TLS und MTLS zum Verschlüsseln von Sofortnachrichten. Für den gesamten Server-zu-Server-Datenverkehr ist MTLS erforderlich, unabhängig davon, ob der Datenverkehr auf das interne Netzwerk begrenzt ist oder die Netzwerkgrenze überschreitet.

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
Mediendatenverkehr wird über Secure RTP (SRTP) verschlüsselt, ein Profil von RTP (Real-Time Transport-Protokoll), das Vertraulichkeit, Authentifizierung und Schutz vor Replay-Angriffen für RTP-Datenverkehr bereitstellt. SRTP verwendet einen Sitzungsschlüssel, der mithilfe eines sicheren Zufallszahlengenerators generiert und über den signalisierenden TLS-Kanal ausgetauscht wird. Darüber hinaus werden Medien, die in beide Richtungen zwischen dem Vermittlungsserver und seinem internen nächsten Hop übertragen werden, ebenfalls über SRTP verschlüsselt. 

SfBO generiert Benutzernamen/Kennwörter für den sicheren Zugriff auf Medienrelais über TURN. Medienrelays tauschen den Benutzernamen/Kennwort über einen TLS-gesicherten SIP-Kanal aus.

#### <a name="fips"></a>FIPS
SfBO verwendet FIPS (Federal Information Processing Standard) konforme Algorithmen für den Austausch von Verschlüsselungsschlüsseln. 

### <a name="user-and-client-authentication"></a>Benutzer- und Client-Authentifizierung 
Vertrauenswürdige Benutzer sind Benutzer, deren Anmeldeinformationen von einem AAD in O365 authentifiziert wurden. 

Authentifizierung bedeutet die Bereitstellung von Benutzeranmeldeinformationen für einen vertrauenswürdigen Server oder Dienst. SfBO verwendet abhängig vom Status und Aufenthaltsort des Benutzers die folgenden Authentifizierungsprotokolle.
- **Moderne Authentifizierung** ist die Microsoft-Implementierung von OAUTH 2.0 für die Client-Server-Kommunikation. Sie ermöglicht Sicherheitsfunktionen wie O365-Zertifikatbasierte Authentifizierung, O365-Mehrstufige Authentifizierung und O365-Bedingter Zugriff.  Für die Nutzung von MA müssen sowohl der Online-Mandant als auch die Clients für MA freigeschaltet sein.  SfBO-Mandanten, die nach Mai 2017 erstellt wurden, haben MA standardmäßig aktiviert.  Folgen Sie diesen Anweisungen hier für Mandanten, die vor dieser Zeit erstellt wurden, um diese einzuschalten.  Die folgenden Clients unterstützen MA: Skype for Business 2015 oder 2016 Client, Skype for Business für Mac, Lync 2013 Client, 3PIP IP-Telefone, iOS und Android. 
- **Organisationskennung** wird verwendet, wenn moderne Authentifizierung nicht aktiviert (oder nicht verfügbar) ist
- Das **Digestprotokoll** für sogenannte anonyme Benutzer. Anonyme Benutzer sind externe Benutzer, die nicht über anerkannte Active Directory-Anmeldeinformationen verfügen, aber zu einer lokalen Konferenz eingeladen wurden und einen gültigen Konferenzschlüssel besitzen. Die Digestauthentifizierung wird nicht für andere Clientinteraktionen verwendet.

Die SfBO-Authentifizierung verläuft in zwei Phasen:
1. Zwischen dem Client und dem Server wird eine Sicherheitszuordnung eingerichtet.
2. Client und Server verwenden die vorhandene Sicherheitszuordnung, um Nachrichten, die sie senden, zu signieren, und Nachrichten, die sie empfangen, zu überprüfen. Nicht authentifizierte Nachrichten von einem Client werden nicht akzeptiert, wenn die Authentifizierung auf dem Server aktiviert ist.

Die Benutzervertrauenswürdigkeit ist mit jeder Nachricht verbunden, die von einem Benutzer stammt, nicht mit der Benutzeridentität selbst. Der Server überprüft jede Nachricht auf gültige Benutzeranmeldeinformationen. Wenn die Benutzeranmeldeinformationen gültig sind, wird die Nachricht weder vom ersten Server, der sie empfängt, noch von allen anderen Servern in der SfBO widersprochen.

Benutzer mit gültigen Anmeldeinformationen, die von einem Verbundpartner ausgegeben wurden, sind vertrauenswürdig, erhalten aber optional aufgrund zusätzlicher Einschränkungen nicht sämtliche Berechtigungen, die internen Benutzern erteilt werden.

Zur Medienauthentifizierung verwenden die Protokolle ICE und TURN ebenfalls die Hashwert-Aufforderung, wie im IETF TURN RFC beschrieben. Weitere Details finden Sie unter [Mediendurchlauf](#external-user-av-traffic-traversal).

Client-Zertifikate bieten einen alternativen Weg für die Authentifizierung von Benutzern durch SFBO. Anstelle der Angabe eines Benutzernamens und eines Kennworts haben die Benutzer ein Zertifikat und den privaten Schlüssel, der dem Zertifikat entspricht, das zum Auflösen einer kryptografischen Aufforderung benötigt wird. 

### <a name="windows-powershell-and-sfbo-management-tools"></a>Windows PowerShell und SfBO-Verwaltungstools
In SfBO können IT-Administratoren ihren Dienst über das O365 Admin-Portal oder über Remote-PowerShell (TRPS) des Mandanten verwalten.  Mandantenadministratoren verwenden moderne Authentifizierung, um sich bei TRPS zu authentifizieren.

### <a name="configuring-access-to-sfbo-at-your-internet-boundary"></a>Konfigurieren des Zugriffs auf SfBO an Ihrer Internetgrenze
Damit SfBO ordnungsgemäß funktioniert (Benutzer, die an Meetings teilnehmen können usw.), müssen Kunden ihren Internetzugriff so konfigurieren, dass ausgehender UDP- und TCP-Verkehr zu Diensten in der SfBO-Cloud erlaubt ist.  Weitere Details finden Sie hier: https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_lyo 

### <a name="udp-3478-3481-and-tcp-443"></a>UDP 3478-3481 und TCP 443

Die Client verwenden die Ports UDP 3478-3481 und TCP 443, um Dienste vom A/V Edge-Dienst anzufordern. Ein Client verwendet diese beiden Ports, um UDP- bzw. TCP-Ports für die Verbindung zum Remote-Teilnehmer zuzuweisen. Der Client muss vor dem Zugriff auf den A/V Edge-Dienst zunächst eine authentifizierte SIP-Signalisierungssitzung mit der SFBO-Registrierungsstelle eingerichtet haben, um die Authentifizierungsanmeldeinformationen des A/V Edge-Dienstes zu erhalten. Diese Werte werden über den TLS-geschützten Signalisierungskanal gesendet und sind computergeneriert, um gegen Schlüsselverzeichnisangriffe zu schützen. Clients können diese Anmeldeinformationen dann für die Hashwert-Authentifizierung mit dem A/V Edge-Dienst verwenden, um Ports für die Verwendung in einer Mediensitzung zuzuweisen. Eine erste Zuordnungsanforderung wird vom Client gesendet und mit einer 401 Nonce/Aufforderung-Nachricht vom A/V Edge-Dienst beantwortet. Der Client sendet eine zweite Zuweisung, die den Benutzernamen und einen Hash Message Authentication Code (HMAC) Hash des Benutzernamens und nonce enthält. 

Ein Sequenznummern-Mechanismus zum Verhindern von Replay-Angriffen ist ebenfalls vorhanden. Der Server berechnet den erwarteten HMAC basierend auf seiner eigenen Kenntnis des Benutzernamens und des Kennworts. Wenn die HMAC-Werte übereinstimmen, wird die Zuweisungsprozedur durchgeführt. Andernfalls wird das Paket gelöscht. Der gleiche HMAC-Mechanismus wird auch auf nachfolgende Nachrichten innerhalb dieser Aufrufsitzung angewendet. Die Lebensdauer dieses Benutzername/Kennwortes beträgt maximal acht Stunden, in denen der Client einen neuen Benutzername/ein neues Kennwort für nachfolgende Aufrufe erhält.

### <a name="udptcp-50000-59999"></a>UDP/TCP 50.000 - 59.999
TCP 50.000 wird ausgehend für SfBO verwendet, einschließlich für Anwendungs- und Desktopfreigabe und Dateiübertragung. UDP/TCP 50.000-59.999 Portbereiche werden für Mediensitzungen mit Microsoft Office Communications Server 2007-Partnern verwendet, die den NAT/Firewallüberquerungsdienst des A/V Edge-Diensts benötigen. Da der A/V Edge-Dienst der einzige Prozess ist, der diese Ports verwendet, zeigt die Größe des Portbereichs nicht die mögliche Angriffsfläche an. Eine gute Sicherheitspraxis besteht darin, die Gesamtzahl der Lauschports zu minimieren, indem keine unnötigen Netzwerkdienste ausgeführt werden. Wenn ein Netzwerkdienst nicht ausgeführt wird, ist er für einen Remote-Angreifer nicht ausnutzbar und die Angriffsfläche des Host-Computers wird reduziert. Innerhalb eines einzigen Dienstes bietet die Reduzierung der Anzahl der Ports jedoch nicht den gleichen Nutzen. Die A/V Edge-Dienstsoftware ist mit 10.000 offenen Ports nicht so angreifbar wie mit 10. Die Zuteilung von Ports innerhalb dieses Bereichs erfolgt zufällig und nicht zugewiesene Ports hören nicht auf Pakete ab.
 
### <a name="external-user-av-traffic-traversal"></a>Externer Benutzer A/V-Verkehrdurchlauf
Damit externe und interne Benutzer Medien austauschen können, ist ein Access Edge-Dienst erforderlich, der die SIP-Signalisierung übernimmt, die zum Auf- und Abbau einer Sitzung benötigt wird. Der A/V Edge-Dienst muss auch als Relais für die Übertragung der Medien agieren. Die Aufrufsequenz wird in der folgenden Abbildung dargestellt.


![Aufrufsequenz in der Besprechungsteilnahme](media/sfbo-call-sequence-security.png) 

1. Ein Benutzer erhält eine E-Mail mit einer Einladung zu einer SfBO-Besprechung. Die E-Mail enthält einen Konferenzschlüssel und eine HTTP-basierte URL, die mit der Konferenz verlinkt. Sowohl der Schlüssel als auch die URL sind für eine bestimmte Besprechung eindeutig.<p>Der Benutzer leitet den Anmeldevorgang ein, indem er in der E-Mail auf die URL der Besprechung klickt, die einen Client-Erkennungsprozess auf dem Computer des Benutzers auslöst.  Wenn der Client erkannt wird, startet dieser Client.  Wenn er nicht erkannt wird, wird der Benutzer auf den Web-Client umgeleitet.<p/>
2. Der SfBO-Client sendet eine SIP-EINLADUNG mit den Anmeldeinformationen des Benutzers. Ein Verbund- oder Remote-Benutzer tritt einer Konferenz mit den Anmeldeinformationen seines Unternehmens bei. Für einen Verbundbenutzer wird die SIP-EINLADUNG zunächst an seinen Heimserver gesendet, der den Benutzer authentifiziert und die EINLADUNG an SfBO weiterleitet. Ein anonymer Benutzer wird für das Durchlaufen der Digest-Authentifizierung benötigt.<p>SfBO authentifiziert den Remote- oder anonymen Benutzer und benachrichtigt den Client. Wie in Schritt 2 erwähnt, werden Verbundbenutzer, die einer Konferenz beitreten, von ihrem Unternehmen authentifiziert.<p/>

3. Der Client sendet eine INFO-Anforderung, um den Benutzer der A/V-Konferenz hinzuzufügen.

    Die A/V-Konferenzen senden eine "Benutzer hinzufügen"-Antwort, die unter anderem das Token enthält, das dem AV-Konferenz-Edge-Dienst präsentiert werden soll.

    [Hinweis] Der gesamte vorhergehende SIP-Verkehr erfolgte über den Zugriffs-Edgedienst.

    Der Client verbindet sich mit dem A/V-Konferenzserver, der das Token validiert und die Anforderung, die ein anderes Autorisierungstoken enthält, an den internen A/V-Konferenzserver weiterleitet. Der A/V-Konferenzserver validiert das Autorisierungstoken, das er ursprünglich über den SIP-Kanal ausgegeben hat, um sicherzustellen, dass ein gültiger Benutzer an der Konferenz teilnimmt.
    
4. Zwischen dem Client und dem AV-Konferenzserver wird eine Medienverbindung ausgehandelt und über SRTP aufgebaut.
5. Ein Benutzer erhält eine E-Mail mit einer Einladung zu einer SfBO-Besprechung. Die E-Mail enthält einen Konferenzschlüssel und eine HTTP-basierte URL, die mit der Konferenz verlinkt. Sowohl der Schlüssel als auch die URL sind für eine bestimmte Besprechung eindeutig.

### <a name="federation-safeguards-for-sfbo"></a>Verbundsicherheitsmaßnahmen für SfBO
Verbund bietet Ihrer Organisation die Möglichkeit, mit anderen Organisationen zu kommunizieren, um IM und Anwesenheit zu teilen. In SfBO ist der Verbund standardmäßig aktiviert.  Mandatenenadministratoren können dies jedoch über das O365 Admin-Portal steuern.  Mehr sehen.

## <a name="addressing-threats-to-sfbo-conferences"></a>Handhaben von Bedrohungen für SfBO-Konferenzen

Mit SfBO können Unternehmen Webkonferenzen in Echtzeit erstellen und daran teilnehmen. Unternehmensbenutzer können auch externe Benutzer, die kein AAD/O365-Konto haben, zur Teilnahme an diesen Besprechungen einladen. Benutzer, die von Verbundpartnern mit einer sicheren und authentifizierten Identität angestellt sind, können auch an Besprechungen teilnehmen und, wenn sie dazu befördert werden, als Referenten fungieren. Anonyme Benutzer können keine Besprechung erstellen oder als Referent daran teilnehmen, aber sie können zum Referent befördert werden, nachdem sie sich angemeldet haben.

Die Möglichkeit für externe Benutzer, an SfBO-Meetings teilzunehmen, erhöht den Wert dieser Funktion erheblich, birgt aber auch einige Sicherheitsrisiken. SfBO bietet folgende zusätzlichen Sicherheitsmaßnahmen, um diesen Risiken zu begegnen:
- Teilnehmerrollen bestimmen die Berechtigungen für die Konferenzsteuerung.
- Mithilfe der Teilnehmertypen können Sie den Zugriff auf bestimmte Besprechungen einschränken.
- Definierte Besprechungstypen legen fest, welche Teilnehmertypen teilnehmen können.
- Die Konferenzplanung ist auf Benutzer mit einem AAD-Konto und einer SfBO-Lizenz beschränkt.
- Anonyme, d. h. nicht authentifizierte Benutzer, die an einer Konferenz teilnehmen möchten, wählen eine der Konferenzeinwahlnummern und werden dann zur Eingabe der Konferenz-ID aufgefordert. Nicht authentifizierte anonyme Benutzer werden ebenfalls aufgefordert, ihren Namen aufzuzeichnen. Der aufgezeichnete Name identifiziert nicht authentifizierte Benutzer in der Konferenz. Anonyme Benutzer werden erst dann zur Konferenz zugelassen, wenn mindestens ein Leiter oder authentifizierter Benutzer beigetreten ist. Ihnen kann keine vordefinierte Rolle zugewiesen werden.

### <a name="participant-roles"></a>Teilnehmerrollen
Die Besprechungsteilnehmer gliedern sich in drei Gruppen mit jeweils eigenen Privilegien und Einschränkungen:
- **Organisator**&nbsp;&nbsp;Der Benutzer, der eine Besprechung erstellt, sei es spontan oder durch Terminplanung. Ein Organisator muss ein authentifizierter Unternehmensbenutzer sein und die Kontrolle über alle Endbenutzeraspekte einer Besprechung haben.
- **Referent**&nbsp;&nbsp;Ein Benutzer, der berechtigt ist, Informationen in einer Besprechung zu präsentieren, unabhängig davon, welches Medium unterstützt wird. Ein Besprechungsorganisator ist per Definition auch ein Referent und bestimmt, wer sonst noch ein Referent sein kann. Ein Organisator kann diese Entscheidung treffen, wenn eine Besprechung geplant ist oder während die Besprechung stattfindet.
- **Teilnehmer**&nbsp;&nbsp;Ein Benutzer, der zu einer Besprechung eingeladen wurde, aber nicht berechtigt ist, als Referent zu fungieren.

Ein Referent kann auch einen Teilnehmer während der Besprechung für die Rolle des Referenten befördern.

### <a name="participant-types"></a>Teilnehmertypen

Die Besprechungsteilnehmer werden auch nach Aufenthaltsort und Anmeldeinformationen kategorisiert. Mit diesen beiden Merkmalen können Sie festlegen, welche Benutzer Zugriff auf bestimmte Besprechungen haben. Die Benutzer lassen sich grob in die folgenden Kategorien einteilen:
1.  **Benutzer, die zum Mandaten gehören**&nbsp;&nbsp;Diese Benutzer haben eine Berechtigung im Azure Active Directory für den Mandanten.<br/>
    a. *Im Unternehmensnetzwerk* – Diese Benutzer treten aus dem Unternehmensnetzwerk heraus bei.<br/>b. *Remotebenutzer* - Diese Benutzer kommen von außerhalb des Unternehmensnetzwerks. Dazu gehören Mitarbeiter, die zu Hause oder unterwegs arbeiten, und andere, wie Mitarbeiter von vertrauenswürdigen Anbietern, denen für ihre Vertragsbedingungen ein Unternehmenszertifikat erteilt wurde. Remotebenutzer können Konferenzen erstellen und daran teilnehmen und als Referenten fungieren.
2.  **Benutzer, die nicht zum Mandaten gehören**&nbsp;&nbsp;Diese Benutzer haben keine Anmeldeinformation im Azure Active Directory für den Mandanten.<br/>a. *Verbundbenutzer* - Verbundbenutzer besitzen gültige Anmeldedaten bei Verbundpartnern und werden daher von SFBO als authentifiziert behandelt. Verbundbenutzer können an Konferenzen teilnehmen und zu Referenten befördert werden, nachdem sie der Besprechung beigetreten sind, aber sie können keine Konferenzen in Unternehmen erstellen, mit denen sie verbunden sind.<br/>b. *Anonyme Benutzer* - Anonyme Benutzer haben keine Active Directory-Identität und sind nicht mit dem Mandanten verbunden. 

Kundendaten zeigen, dass viele Konferenzen mit externen Benutzern durchgeführt werden. Dieselben Kunden möchten sich auch über die Identität der externen Benutzer vergewissern, bevor sie an einer Konferenz teilnehmen können. Wie im folgenden Abschnitt beschrieben, beschränkt SfBO den Zugriff auf die Benutzertypen, die explizit zugelassen wurden, und verlangt von allen Benutzertypen, dass sie bei der Teilnahme an einer Besprechung entsprechende Anmeldeinformationen vorlegen.

### <a name="participant-admittance"></a>Teilnehmerzulassung
In SfBO werden anonyme Benutzer in einen Wartebereich, die Lobby, weitergeleitet. Referneten können diese Benutzer dann entweder zur Besprechung zulassen oder ablehnen. Diese Benutzer werden in die Lobby übertragen, der Leiter wird benachrichtigt, und die Benutzer warten dann, bis ein Leiter sie entweder akzeptiert oder ablehnt oder ihre Verbindungszeit abgelaufen ist. In der Lobby hören die Benutzer Musik. 

Standardmäßig gehen Teilnehmer, die sich aus dem PSTN einwählen, direkt zur Besprechung, aber diese Option kann geändert werden, um die Einwahl der Teilnehmer in die Lobby zu erzwingen.  
Besprechungsorganisatoren steuern, ob Teilnehmer an einer Besprechung teilnehmen können, ohne in der Lobby zu warten. Jede Besprechung kann so eingerichtet werden, dass der Zugriff mit einer der folgenden Methoden möglich ist:
- **Nur ich, der Organisator des Treffens**&nbsp;&nbsp;Jeder außer dem Organisator muss in der Lobby warten, bis er zugelassen wird.
- **Personen, die ich aus meinem Unternehmen einlade**&nbsp;&nbsp;Jeder aus Ihrem Unternehmen kann direkt zur Besprechung kommen, auch wenn er nicht eingeladen ist.
- **Jeder aus meiner Organisation**&nbsp;&nbsp;Alle SfBO-Nutzer im O365-Mandanten können an der Sitzung teilnehmen, ohne in der Lobby zu warten, auch wenn sie nicht auf der Verteilerliste stehen. Alle anderen, einschließlich aller externen und anonymen Benutzer, müssen in der Lobby warten, bis sie zugelassen werden.
- **Jeder**&nbsp;&nbsp;Jeder (es gibt keine Einschränkungen) wer Zugriff auf den Besprechungslink hat, kommt direkt in die Besprechung.
Wenn eine beliebige Methode außer Nur Organisator (gesperrt) angegeben ist, kann der Organisator der Besprechung auch Personen angeben, die sich per Telefon einwählen, um die Lobby zu umgehen. 

### <a name="presenter-capabilities"></a>Referentenfunktion
Die Organisatoren der Besprechung kontrollieren, ob die Teilnehmer während einer Besprechung anwesend sein können. Jede Besprechung kann so eingerichtet werden, dass die Referenten auf einen der folgenden Punkte beschränkt sind:
- **Nur Organisator**&nbsp;&nbsp; Nur der Organisator kann Referent sein.
- **Personen aus meinem Unternehmen**&nbsp;&nbsp; Alle internen Benutzer können teilnehmen.
- **Jeder, der Personen außerhalb meines Unternehmens einbezieht**&nbsp;&nbsp; Jeder (es gibt keine Einschränkungen), der der Besprechung beitritt, kann teilnehmen.
- **Personen, die ich wähle**&nbsp;&nbsp;Der Organisator der Besprechung legt fest, welche Benutzer präsentieren können, indem er sie einer Liste von Referenten hinzufügt.

## <a name="related-topics"></a>See Also
[Office 365 Trust Center](https://products.office.com/en-us/business/office-365-trust-center-security)

