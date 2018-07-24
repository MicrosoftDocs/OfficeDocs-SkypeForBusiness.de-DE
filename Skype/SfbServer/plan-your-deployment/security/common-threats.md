---
title: Häufige Sicherheitsbedrohungen in der modernen EDV
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/22/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
description: Da Skype für Business Server einem Enterprise-Klasse Communications-System handelt, sollten Sie häufig vorkommende Angriff beachten, die die Infrastruktur und Kommunikation auswirken könnten.
ms.openlocfilehash: 59f65a6a9a4d56850908fa0749e4a672b23b7a85
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967827"
---
# <a name="common-security-threats-in-modern-day-computing"></a>Häufige Sicherheitsbedrohungen in der modernen EDV
 
Da Skype für Business Server einem Enterprise-Klasse Communications-System handelt, sollten Sie häufig vorkommende Angriff beachten, die die Infrastruktur und Kommunikation auswirken könnten.
  
## <a name="compromised-key-attack"></a>Angriff mit kompromittierten Schlüsseln

Ein Schlüssel ist ein geheimer Code oder eine geheime Nummer zur Verschlüsselung, Entschlüsselung oder Überprüfung geheimer Informationen. Es werden zwei vertrauliche Schlüssel verwendet in public Key-Infrastruktur (PKI), die berücksichtigt werden muss: 
  
- Der private Schlüssel, der sich im Besitz des jeweiligen Zertifikatinhabers befindet
    
- Der Sitzungsschlüssel, der nach der erfolgreichen Identifikation und dem Sitzungsschlüsselaustausch durch die Kommunikationspartner verwendet wird
    
Ein Angriff mit kompromittierten Schlüsseln liegt vor, wenn der Angreifer den privaten Schlüssel oder den Sitzungsschlüssel ermittelt. Gelingt dem Angreifer die Ermittlung des Schlüssels, kann er den Schlüssel zum Entschlüsseln verschlüsselter Daten ohne Wissen des Absenders verwenden.
  
Skype für Business Server verwendet die PKI-Features in das Betriebssystem Windows Server zum Schutz der wichtigsten Daten, die für die Verschlüsselung für die Verbindungen Transport Layer Security (TLS) verwendet. Die für die Medienverschlüsselung verwendeten Schlüssel werden über TLS-Verbindungen ausgetauscht.
  
## <a name="network-denial-of-service-attack"></a>Denial-of-Service-Angriff auf das Netzwerk

Ein Denial-of-Service-Angriff liegt vor, wenn der Angreifer die normale Netzwerknutzung durch gültige Nutzer verhindert. Hierbei überfluten Angreifer den Dienst mit legitimen Anforderungen, sodass er für die berechtigten Nutzer nicht mehr erreichbar ist. Bei einem Denial-of-Service-Angriff eröffnen sich den Angreifern folgende Möglichkeiten:
  
- Er kann ungültige Daten an Anwendungen und Dienste senden, die in dem angegriffenen Netzwerk ausgeführt werden, um ihre Funktionsweise zu beeinträchtigen.
    
- Er kann große Datenmengen senden, um das System zu überlasten, bis es nicht mehr oder nur noch verzögert auf legitime Anforderungen reagiert.
    
- Er kann die Spuren seines Angriffs vertuschen.
    
- Er kann Benutzer vom Zugriff auf die Netzwerkressourcen abhalten.
    
## <a name="eavesdropping-sniffing-snooping"></a>Abhöraktionen ("Sniffing", "Snooping")

Abhöraktionen sind Aktionen, bei denen sich Angreifer Zugriff auf den Datenpfad in einem Netzwerk verschaffen und anschließend den Datenverkehr überwachen und lesen können. Dies ist auch Calledsniffing Orsnooping. Wenn der Datenverkehr aus reinem Text besteht, können Angreifer ihn lesen, sobald sie Zugriff auf den Pfad haben. Ein Beispiel wäre ein Angriff, bei dem ein Router auf dem Datenpfad kontrolliert wird. 
  
Die Standard-Empfehlung und die Einstellung für den Datenverkehr in Skype für Business Server wird mutual TLS (MTLS) zwischen vertrauenswürdigen Servern und TLS vom Client zum Server verwendet. Diese Schutzmaßnahme macht einen derartigen Angriff innerhalb der Zeitspanne, in der eine Unterhaltung erfolgt, äußerst schwer oder unmöglich. Mit TLS werden alle Parteien authentifiziert und der gesamte Datenverkehr wird verschlüsselt. Damit können Abhöraktionen nicht verhindert werden, aber Angreifer können den Datenverkehr nicht lesen, es sei denn, die Verschlüsselung geht verloren.
  
Das TURN-Protokoll (Traversal Using Relay NAT) setzt keine Verschlüsselung des Datenverkehrs voraus. Die Daten, die darüber versendet werden, unterliegen dem Schutz durch die Nachrichtenintegrität. Es ist rein theoretisch möglich, sie abzuhören, aber die Informationen, die über das TURN-Protokoll gesendet werden (d. h. die IP-Adressen und der Port), können direkt extrahiert werden, indem die Quell- und Zieladressen der Pakete angezeigt werden. Der A/V-Edgedienst stellt sicher, dass die Daten gültig sind, indem er die Nachrichtenintegrität der Nachricht mithilfe des Schlüssels überprüft, der von bestimmten Objekten abgeleitet wird. Dazu gehört auch ein TURN-Kennwort, das nie als Klartext gesendet wird. Wenn SRTP (Secure Real Time Protocol) verwendet wird, so wird auch der Mediendatenverkehr verschlüsselt.
  
## <a name="identity-spoofing-ip-address-spoofing"></a>Identitätsvortäuschung (Spoofing der IP-Adresse)

Spoofing liegt vor, wenn Angreifer unbefugt die IP-Adresse eines Netzwerks, Computers oder einer Netzwerkkomponente ermitteln und verwenden. Nach einem erfolgreichen Angriff können sich Angreifer als die normalerweise durch diese IP-Adresse identifizierte Entität ausgeben. Im Kontext des Skype für Business Server kommt diese Situation ins Spiel nur, wenn ein Administrator die folgenden beiden aufgewendet hat:
  
- Er hat Verbindungen konfiguriert, die nur TCP (Transmission Control Protocol) unterstützen. (Dies ist nicht zu empfehlen, da die TCP-Kommunikation unverschlüsselt ist.)
    
- Er hat die IP-Adressen dieser Verbindungen als vertrauenswürdige Hosts markiert.
    
Dies ist für TLS-Verbindungen (Transport Layer Security) weniger ein Problem, da TLS alle Parteien authentifiziert und den gesamten Datenverkehr verschlüsselt. Die Verwendung von TLS verhindert Spoofingangriffe auf bestimmte Verbindungen (Mutual TLS-Verbindungen). Aber ein Angreifer konnte Spoofing die Adresse des DNS-Servers, der Skype für Business Server verwendet. Allerdings, da die Authentifizierung in Skype für Unternehmen mit Zertifikaten durchgeführt wird, müssten ein Angreifer kein gültiges Zertifikat erforderlich, um Spoofing eines Beteiligten bei der Kommunikation.
  
## <a name="man-in-the-middle-attack"></a>Man-in-the-Middle-Angriff

Ein Man-in-the-Middle-Angriff tritt auf, wenn ein Angreifer die Kommunikation zwischen zwei Benutzern über seinen Computer ohne Wissen der zwei kommunizierenden Benutzer leitet. Die Angreifer können die übertragenen Daten überwachen und lesen, ehe sie an den eigentlichen Empfänger weitergeleitet werden. Beide Kommunikationspartner senden unwissentlich Daten an die Angreifer und empfangen von ihnen Daten, sind aber dabei in dem Glauben, ausschließlich mit der beabsichtigten Person zu kommunizieren. Dies kann passieren, wenn es Angreifern gelingt, die Active Directory-Domänendienste so zu ändern, dass ihr Server als vertrauenswürdiger Server hinzugefügt wird, oder wenn sie den DNS-Eintrag (Domain Name System) so ändern können, dass Clients auf ihrem Weg zum Server über den Computer der Angreifer geleitet werden. Ein Man-in-the-Middle-Angriff kann auch mit Mediendatenverkehr zwischen zwei Clients auftreten. Allerdings werden in Skype für Business Server Point Audio-, Video- und Anwendungsfreigabe, Datenströme verschlüsselt, mit SRTP, kryptografische Schlüssel, die zwischen den Peers ausgehandelt werden, die über TLS Session Initiation Protocol (SIP) verwenden. Server wie Gruppenchat nutzen HTTPS zur Erhöhung der Sicherheit des Webdatenverkehrs.
  
## <a name="rtp-replay-attack"></a>Angriff mit Aufzeichnungswiederholung (RTP-Datenverkehr)

Bei einem Angriff mit Aufzeichnungswiederholung wird in böswilliger Absicht eine gültige Medienübertragung zwischen zwei Parteien abgefangen und erneut übertragen. Durch die Verwendung von SRTP in Verbindung mit einem sicheren Signalübermittlungsprotokoll werden Übertragungen vor Angriffen mit Aufzeichnungswiederholung geschützt. Mit SRTP können Empfänger einen Index der bereits empfangenen RTP-Pakete erstellen und jedes neue Paket mit den bereits enthaltenen vergleichen.
  
## <a name="spim"></a>SPIM (Spam over Instant Messaging)

Unter SPIM sind unaufgeforderte Werbe-SMS oder Anwesenheitsabonnementanforderungen zu verstehen. Zwar wird das Netzwerk nicht unmittelbar beeinträchtigt, doch ist SPIM zumindest ärgerlich, kann die Ressourcenverfügbarkeit und die Produktivität reduzieren und möglicherweise zu einer Beeinträchtigung des Netzwerks führen. Ein Beispiel für Spimming sind Nutzer, die sich gegenseitig Anfragen zusenden. Nutzer können sich gegenseitig blockieren, um dies zu verhindern. Ein koordinierter Spimangriff im Partnerverbund kann jedoch schwer abzuwehren sein, wenn Sie den Verbund für den Partner nicht deaktivieren.
  
## <a name="viruses-and-worms"></a>Viren und Würmer

Ein Virus ist eine Codeeinheit, deren Zweck die Reproduktion zusätzlicher, ähnlicher Codeeinheiten ist. Ein Virus benötigt, um zu funktionieren, einen Host, z. B. eine Datei, eine E-Mail oder ein Programm. Aworm ist eine Codeeinheit, deren Zweck darin besteht, ähnliche Codeeinheiten zu reproduzieren, aber es ist nicht erforderlich, einen Host. Viren und Würmer treten vor allem bei Dateiübertragungen zwischen Clients oder beim Versenden von URLs von anderen Benutzern auf. Wenn sich ein Virus auf Ihrem Computer befindet, kann er beispielsweise Ihre Identität verwenden und Sofortnachrichten in Ihrem Namen versenden.
  
## <a name="personally-identifiable-information"></a>Informationen zur Identifikation von Personen

Skype für Business Server kann Informationen über ein öffentliches Netzwerk offengelegt werden, die möglicherweise mit einer einzelnen verknüpft werden können. Bei diesen Informationen kann es sich um zwei Kategorien von Angaben handeln:
  
- **Erweiterte Anwesenheitsdaten** Erweiterte Anwesenheitsdaten sind Informationen, die ein Benutzer freigeben oder nicht über einen Link zu einem Verbundpartner oder mit Kontakten innerhalb einer Organisation freigeben können. Diese Daten werden nicht an Benutzer in einem öffentlichen IM-Netzwerk weitergegeben. Client-Richtlinien und andere Client-Konfigurationen können dem Systemadministrator eine gewisse Kontrolle verschaffen. In Skype für Business Server kann datenschutzmodus für erweiterte Anwesenheitsinformationen für einen einzelnen Benutzer zu Skype für Unternehmensbenutzer nicht in der Kontaktliste des Benutzers verhindern der Anzeige von Anwesenheitsinformationen des Benutzers konfiguriert werden. Datenschutzmodus für erweiterte Anwesenheitsinformationen es wird nicht verhindert, dass Benutzer von Microsoft Office Communicator 2007 und Microsoft Office Communicator 2007 R2 Anzeige von Anwesenheitsinformationen des Benutzers. Weitere Informationen zur Bereitstellung der Anwesenheit und Client finden Sie unter [Bereitstellen von Clients für Skype für Business Server](../../deploy/deploy-clients/deploy-clients.md) und [Planen von instant messaging und Anwesenheit in Skype für Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).
    
- **Pflichtdaten** Pflichtdaten ist erforderlich für den ordnungsgemäßen Betrieb des Servers oder des Clients und ist nicht der Kontrolle der Client- oder systemverwaltung-Verwaltung. Es handelt sich um Informationen, die auf Server- oder Netzwerkebene für das Routing, die Statuspflege und die Signalübermittlung erforderlich sind.
    
In den folgenden Tabellen wird angegeben, welche Daten über ein öffentliches Netzwerk offengelegt werden.
  
**Erweiterte Anwesenheitsdaten**

|**Offengelegte Daten**|**Mögliche Einstellungen**|
|:-----|:-----|
|Persönliche Daten  <br/> |Name, Titel, Unternehmen, E-Mail-Adresse, Zeitzone  <br/> |
|Telefonnummern  <br/> |Geschäftlich, mobil, privat  <br/> |
|Kalenderdaten  <br/> |Frei/Gebucht, Abwesenheitsmitteilung, Besprechungsdetails (für Personen mit Zugriff auf Ihren Kalender)  <br/> |
|Anwesenheitsstatus  <br/> |Abwesend, verfügbar, gebucht, nicht stören, offline  <br/> |
   
**Pflichtdaten**

|**Offengelegte Daten**|**Beispieldaten**|
|:-----|:-----|
|IP-Adresse  <br/> |Tatsächliche Computer- oder NAT-Adresse  <br/> |
|SIP-URI  <br/> |jeremylos@litwareinc.com  <br/> |
   

