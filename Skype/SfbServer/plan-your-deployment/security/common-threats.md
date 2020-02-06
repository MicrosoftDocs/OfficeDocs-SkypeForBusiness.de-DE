---
title: Häufige Sicherheitsbedrohungen in der modernen EDV
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/22/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
description: Da es sich bei Skype for Business Server um ein Kommunikationssystem auf Unternehmensniveau handelt, sollten Sie sich der allgemeinen Sicherheitsangriffe bewusst sein, die sich auf die Infrastruktur und die Kommunikation auswirken können.
ms.openlocfilehash: 58141a735858d840acbd57e8039aa1c132dbeb8c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815673"
---
# <a name="common-security-threats-in-modern-day-computing"></a>Häufige Sicherheitsbedrohungen in der modernen EDV
 
Da es sich bei Skype for Business Server um ein Kommunikationssystem auf Unternehmensniveau handelt, sollten Sie sich der allgemeinen Sicherheitsangriffe bewusst sein, die sich auf die Infrastruktur und die Kommunikation auswirken können.
  
## <a name="compromised-key-attack"></a>Angriff mit kompromittierten Schlüsseln

Ein Schlüssel ist ein geheimer Code oder eine geheime Nummer zur Verschlüsselung, Entschlüsselung oder Überprüfung geheimer Informationen. In der Public Key-Infrastruktur (PKI) werden zwei vertrauliche Schlüssel verwendet, die berücksichtigt werden müssen: 
  
- Der private Schlüssel, der sich im Besitz des jeweiligen Zertifikatinhabers befindet
    
- Der Sitzungsschlüssel, der nach der erfolgreichen Identifikation und dem Sitzungsschlüsselaustausch durch die Kommunikationspartner verwendet wird
    
Ein Angriff mit kompromittierten Schlüsseln liegt vor, wenn der Angreifer den privaten Schlüssel oder den Sitzungsschlüssel ermittelt. Gelingt dem Angreifer die Ermittlung des Schlüssels, kann er den Schlüssel zum Entschlüsseln verschlüsselter Daten ohne Wissen des Absenders verwenden.
  
Skype for Business Server verwendet die PKI-Features im Windows Server-Betriebssystem, um die für die Verschlüsselung verwendeten Schlüsseldaten für die TLS-Verbindungen (Transport Layer Security) zu schützen. Die für die Medienverschlüsselung verwendeten Schlüssel werden über TLS-Verbindungen ausgetauscht.
  
## <a name="network-denial-of-service-attack"></a>Denial-of-Service-Angriff auf das Netzwerk

Ein Denial-of-Service-Angriff liegt vor, wenn der Angreifer die normale Netzwerknutzung durch gültige Nutzer verhindert. Hierbei überfluten Angreifer den Dienst mit legitimen Anforderungen, sodass er für die berechtigten Nutzer nicht mehr erreichbar ist. Bei einem Denial-of-Service-Angriff eröffnen sich den Angreifern folgende Möglichkeiten:
  
- Er kann ungültige Daten an Anwendungen und Dienste senden, die in dem angegriffenen Netzwerk ausgeführt werden, um ihre Funktionsweise zu beeinträchtigen.
    
- Er kann große Datenmengen senden, um das System zu überlasten, bis es nicht mehr oder nur noch verzögert auf legitime Anforderungen reagiert.
    
- Er kann die Spuren seines Angriffs vertuschen.
    
- Er kann Benutzer vom Zugriff auf die Netzwerkressourcen abhalten.
    
## <a name="eavesdropping-sniffing-snooping"></a>Abhöraktionen ("Sniffing", "Snooping")

Abhöraktionen sind Aktionen, bei denen sich Angreifer Zugriff auf den Datenpfad in einem Netzwerk verschaffen und anschließend den Datenverkehr überwachen und lesen können. Dies wird auch als „Schnüffeln“ (auch „Lauschangriff“, englisch Sniffing oder Snooping) bezeichnet. Wenn der Datenverkehr aus reinem Text besteht, können Angreifer ihn lesen, sobald sie Zugriff auf den Pfad haben. Ein Beispiel wäre ein Angriff, bei dem ein Router auf dem Datenpfad kontrolliert wird. 
  
Die Standardempfehlung und-Einstellung für den Datenverkehr in Skype for Business Server besteht darin, MTLS (Mutual TLS) zwischen vertrauenswürdigen Servern und TLS vom Client zum Server zu verwenden. Diese Schutzmaßnahme macht einen derartigen Angriff innerhalb der Zeitspanne, in der eine Unterhaltung erfolgt, äußerst schwer oder unmöglich. Mit TLS werden alle Parteien authentifiziert und der gesamte Datenverkehr wird verschlüsselt. Damit können Abhöraktionen nicht verhindert werden, aber Angreifer können den Datenverkehr nicht lesen, es sei denn, die Verschlüsselung geht verloren.
  
Das TURN-Protokoll (Traversal Using Relay NAT) setzt keine Verschlüsselung des Datenverkehrs voraus. Die Daten, die darüber versendet werden, unterliegen dem Schutz durch die Nachrichtenintegrität. Es ist rein theoretisch möglich, sie abzuhören, aber die Informationen, die über das TURN-Protokoll gesendet werden (d. h. die IP-Adressen und der Port), können direkt extrahiert werden, indem die Quell- und Zieladressen der Pakete angezeigt werden. Der A/V-Edgedienst stellt sicher, dass die Daten gültig sind, indem er die Nachrichtenintegrität der Nachricht mithilfe des Schlüssels überprüft, der von bestimmten Objekten abgeleitet wird. Dazu gehört auch ein TURN-Kennwort, das nie als Klartext gesendet wird. Wenn SRTP (Secure Real Time Protocol) verwendet wird, so wird auch der Mediendatenverkehr verschlüsselt.
  
## <a name="identity-spoofing-ip-address-and-caller-id-spoofing"></a>Spoofing von Identitäten (IP-Adresse und Spoofing der Rufnummernanzeige)

Identitäts Spoofing tritt auf, wenn der Angreifer eine Telefonnummer eines gültigen Benutzers (Rufnummernanzeige) oder eine IP-Adresse eines Netzwerks, Computers oder einer Netzwerkkomponente ermittelt und verwendet, ohne dafür autorisiert zu werden. Ein erfolgreicher Angriff ermöglicht es dem Angreifer, so zu arbeiten, als wäre der Angreifer die Entität, die normalerweise durch die Telefonnummer (Rufnummernanzeige) oder die IP-Adresse gekennzeichnet ist.

Im Kontext von Skype for Business Server wird die IP-Adressen-Spoofing nur dann wiedergegeben, wenn ein Administrator beide der folgenden Schritte ausgeführt hat:
  
- Er hat Verbindungen konfiguriert, die nur TCP (Transmission Control Protocol) unterstützen. (Dies ist nicht zu empfehlen, da die TCP-Kommunikation unverschlüsselt ist.)
    
- Er hat die IP-Adressen dieser Verbindungen als vertrauenswürdige Hosts markiert.
    
Dies ist für TLS-Verbindungen (Transport Layer Security) weniger ein Problem, da TLS alle Parteien authentifiziert und den gesamten Datenverkehr verschlüsselt. Die Verwendung von TLS verhindert Spoofingangriffe auf bestimmte Verbindungen (Mutual TLS-Verbindungen). Ein Angreifer kann aber weiterhin die Adresse des DNS-Servers spoofen, den Skype for Business Server verwendet. Da die Authentifizierung in Skype for Business jedoch mit Zertifikaten durchgeführt wird, verfügt ein Angreifer nicht über ein gültiges Zertifikat, das für die Spoofing einer der Parteien in der Kommunikation erforderlich ist.

Auf der anderen Seite wird die Rufnummernanzeige-Spoofing ins Spiel gesetzt, wenn Sie einen SIP-Trunk zwischen einem Anbieter, einem PSTN-Gateway oder einem anderen PBX-System und einem Skype for Business-Server eingerichtet haben. In diesen Fällen bietet Skype for Business Server keinen Schutz vor Spoofing durch die Rufnummernanzeige. Dies bedeutet, dass ein Skype for Business-Benutzer einen Anruf vom SIP-Stamm mit einer gefälschten Rufnummernanzeige empfangen kann, die die Telefonnummer oder den Anzeigenamen (falls Reverse-Number-Lookup gilt) eines anderen Skype for Business-Benutzers anzeigt. Dieser Schutz sollte auf der Anbieterseite, dem PSTN-oder dem PBX-Gateway angewendet werden.
  
## <a name="man-in-the-middle-attack"></a>Man-in-the-Middle-Angriff

Ein man-in-the-Middle-Angriff tritt auf, wenn ein Angreifer die Kommunikation zwischen zwei Benutzern über den Computer des Angreifers umleitet, ohne die beiden kommunizierenden Benutzer kennen zu müssen. Die Angreifer können die übertragenen Daten überwachen und lesen, ehe sie an den eigentlichen Empfänger weitergeleitet werden. Beide Kommunikationspartner senden unwissentlich Daten an die Angreifer und empfangen von ihnen Daten, sind aber dabei in dem Glauben, ausschließlich mit der beabsichtigten Person zu kommunizieren. Dies kann passieren, wenn es Angreifern gelingt, die Active Directory-Domänendienste so zu ändern, dass ihr Server als vertrauenswürdiger Server hinzugefügt wird, oder wenn sie den DNS-Eintrag (Domain Name System) so ändern können, dass Clients auf ihrem Weg zum Server über den Computer der Angreifer geleitet werden. Ein Man-in-the-Middle-Angriff kann auch bei Mediendatenverkehr zwischen zwei Clients erfolgen, wobei jedoch in skype16_server_short Point-to-Point-Audio-, Video- und Anwendungsfreigabe-Datenströme mit dem Secure Real-Time Transport Protocol (SRTP) verschlüsselt werden. In der Skype for Business Server-Punkt-zu-Punkt-Audio-, Video-und Anwendungsfreigabe werden Streams jedoch mit SRTP verschlüsselt, wobei kryptografische Schlüssel verwendet werden, die zwischen den Peers ausgehandelt werden, die SIP (Session Initiation Protocol) über TLS verwenden. Server wie Gruppenchat nutzen HTTPS zur Erhöhung der Sicherheit des Webdatenverkehrs.
  
## <a name="rtp-replay-attack"></a>Angriff mit Aufzeichnungswiederholung (RTP-Datenverkehr)

Ein Replay-Angriff liegt vor, wenn eine gültige Medienübertragung zwischen zwei Parteien abgefangen und für böswillige Zwecke erneut übertragen wird. SRTP, das in Verbindung mit einem sicheren Signalisierungsprotokoll verwendet wird, schützt Übertragungen vor Replay-Angriffen, indem es dem Empfänger ermöglicht, einen Index der bereits empfangenen RTP-Pakete beizubehalten und jedes neue Paket mit den bereits im Index aufgeführten zu vergleichen.
  
## <a name="spim"></a>SPIM (Spam over Instant Messaging)

Unter SPIM sind unaufgeforderte Werbe-SMS oder Anwesenheitsabonnementanforderungen zu verstehen. Zwar wird das Netzwerk nicht unmittelbar beeinträchtigt, doch ist SPIM zumindest ärgerlich, kann die Ressourcenverfügbarkeit und die Produktivität reduzieren und möglicherweise zu einer Beeinträchtigung des Netzwerks führen. Ein Beispiel für Spimming sind Nutzer, die sich gegenseitig Anfragen zusenden. Nutzer können sich gegenseitig blockieren, um dies zu verhindern. Ein koordinierter Spimangriff im Partnerverbund kann jedoch schwer abzuwehren sein, wenn Sie den Verbund für den Partner nicht deaktivieren.
  
## <a name="viruses-and-worms"></a>Viren und Würmer

Ein Virus ist eine Codeeinheit, deren Zweck die Reproduktion zusätzlicher, ähnlicher Codeeinheiten ist. Ein Virus benötigt, um zu funktionieren, einen Host, z. B. eine Datei, eine E-Mail oder ein Programm. Aworm ist eine Codeeinheit, deren Zweck darin besteht, zusätzliche, ähnliche Codeeinheiten zu reproduzieren, aber kein Host erforderlich ist. Viren und Würmer treten vor allem bei Dateiübertragungen zwischen Clients oder beim Versenden von URLs von anderen Benutzern auf. Wenn sich ein Virus auf Ihrem Computer befindet, kann er beispielsweise Ihre Identität verwenden und Sofortnachrichten in Ihrem Namen versenden.
  
## <a name="personally-identifiable-information"></a>Informationen zur Identifikation von Personen

Skype for Business Server hat das Potenzial, Informationen über ein öffentliches Netzwerk offenzulegen, die möglicherweise mit einer Person verknüpft werden können. Bei diesen Informationen kann es sich um zwei Kategorien von Angaben handeln:
  
- **Erweiterte Anwesenheitsdaten** Erweiterte Anwesenheitsdaten sind Informationen, die ein Benutzer für die Freigabe oder nicht Freigabe über einen Link zu einem Föderationspartner oder mit Kontakten in einer Organisation auswählen kann. Diese Daten werden nicht an Benutzer in einem öffentlichen IM-Netzwerk weitergegeben. Client-Richtlinien und andere Client-Konfigurationen können dem Systemadministrator eine gewisse Kontrolle verschaffen. In Skype for Business Server kann der Erweiterte Anwesenheitsdaten Schutzmodus für einen einzelnen Benutzer so konfiguriert werden, dass Skype for Business-Benutzer nicht in der Kontaktliste des Benutzers die Anwesenheitsinformationen des Benutzers sehen können. Der Datenschutzmodus für erhöhte Anwesenheit verhindert nicht, dass Benutzer von Microsoft Office Communicator 2007 und Microsoft Office Communicator 2007 R2 die Anwesenheitsinformationen eines Benutzers sehen. Details zum Bereitstellen von Client und Anwesenheit finden Sie unter [Bereitstellen von Clients für Skype for Business Server](../../deploy/deploy-clients/deploy-clients.md) und [Planen von Sofortnachrichten und Anwesenheit in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).
    
- **Obligatorische Daten** Obligatorische Daten sind für den ordnungsgemäßen Betrieb des Servers oder des Clients erforderlich und unterliegen nicht der Kontrolle durch den Client oder die System Administration. Es handelt sich um Informationen, die auf Server- oder Netzwerkebene für das Routing, die Statuspflege und die Signalübermittlung erforderlich sind.
    
In den folgenden Tabellen wird angegeben, welche Daten über ein öffentliches Netzwerk offengelegt werden.
  
**Erweiterte Anwesenheitsdaten**

|**Offengelegte Daten**|**Mögliche Einstellungen**|
|:-----|:-----|
|Persönliche Daten  <br/> |Name, Titel, Unternehmen, E-Mail-Adresse, Zeitzone  <br/> |
|Telefonnummern  <br/> |Geschäftlich, mobil, privat  <br/> |
|Kalenderdaten  <br/> |Frei/Gebucht, Abwesenheitsmitteilung, Besprechungsdetails (für Personen mit Zugriff auf Ihren Kalender)  <br/> |
|Anwesenheitsstatus  <br/> |Abwesend, verfügbar, gebucht, nicht stören, offline  <br/> |
   
**Pflichtdaten**


| **Offengelegte Daten** | **Beispieldaten**                            |
|:-------------------|:---------------------------------------------------|
| IP-Adresse  <br/>  | Tatsächliche Computer- oder NAT-Adresse  <br/> |
| SIP-URI  <br/>     | jeremylos@litwareinc.com  <br/>                    |

