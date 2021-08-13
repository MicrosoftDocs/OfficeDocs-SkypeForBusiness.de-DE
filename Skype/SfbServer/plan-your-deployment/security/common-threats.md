---
title: Allgemeine Sicherheitsbedrohungen im modernen Computing
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Da es sich bei Skype for Business Server um ein Kommunikationssystem der Unternehmensklasse handelt, sollten Sie allgemeine Sicherheitsangriffe kennen, die sich auf die Infrastruktur und Kommunikation auswirken können.
ms.openlocfilehash: 20f8ee917141d56ef1d775afe9868b0f4bb68d5e2aa016487528c8a39bb1ab4d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54297092"
---
# <a name="common-security-threats-in-modern-day-computing"></a>Allgemeine Sicherheitsbedrohungen im modernen Computing
 
Da es sich bei Skype for Business Server um ein Kommunikationssystem der Unternehmensklasse handelt, sollten Sie allgemeine Sicherheitsangriffe kennen, die sich auf die Infrastruktur und Kommunikation auswirken können.
  
## <a name="compromised-key-attack"></a>Angriff mit kompromittierten Schlüsseln

Ein Schlüssel ist ein geheimer Code oder eine geheime Nummer zur Verschlüsselung, Entschlüsselung oder Überprüfung geheimer Informationen. In der Public Key-Infrastruktur (PKI) werden zwei vertrauliche Schlüssel verwendet, die berücksichtigt werden müssen: 
  
- Der private Schlüssel, über den jeder Zertifikatinhaber verfügt
    
- Der Sitzungsschlüssel, der nach einer erfolgreichen Identifizierung und dem Austausch von Sitzungsschlüsseln durch die kommunizierenden Partner verwendet wird
    
Ein Angriff mit kompromittierten Schlüsseln liegt vor, wenn der Angreifer den privaten Schlüssel oder den Sitzungsschlüssel ermittelt. Gelingt dem Angreifer die Ermittlung des Schlüssels, kann er den Schlüssel zum Entschlüsseln verschlüsselter Daten ohne Wissen des Absenders verwenden.
  
Skype for Business Server verwendet die PKI-Features im Betriebssystem Windows Server, um die Schlüsseldaten zu schützen, die für die Verschlüsselung für TLS-Verbindungen (Transport Layer Security) verwendet werden. Die für die Medienverschlüsselung verwendeten Schlüssel werden über TLS-Verbindungen ausgetauscht.
  
## <a name="network-denial-of-service-attack"></a>Denial-of-Service-Angriff auf das Netzwerk

Ein Denial-of-Service-Angriff liegt vor, wenn der Angreifer die normale Netzwerknutzung durch gültige Benutzer verhindert. Dies geschieht, wenn der Angreifer den Dienst mit legitimen Anforderungen überschwemmt, die die Nutzung des Diensts durch legitime Benutzer überfordern. Mithilfe eines Denial-of-Service-Angriffs kann der Angreifer Folgendes tun:
  
- Er kann ungültige Daten an Anwendungen und Dienste senden, die in dem angegriffenen Netzwerk ausgeführt werden, um ihre Funktionsweise zu beeinträchtigen.
    
- Er kann große Datenmengen senden, um das System zu überlasten, bis es nicht mehr oder nur noch verzögert auf legitime Anforderungen reagiert.
    
- Er kann die Spuren seines Angriffs vertuschen.
    
- Er kann Benutzer vom Zugriff auf die Netzwerkressourcen abhalten.
    
## <a name="eavesdropping-sniffing-snooping"></a>Abhören (Sniffing, Snooping)

Abhöraktionen sind Aktionen, bei denen ein Angreifer Zugriff auf den Datenpfad in einem Netzwerk erlangt und anschließend den Datenverkehr überwachen und lesen kann. Dies wird auch als "Schnüffeln" (auch Lauschangriff, englisch "Sniffing" oder "Snooping") bezeichnet. Wenn der Datenverkehr aus reinem Text besteht, kann der Angreifer ihn lesen, sobald er Zugriff auf den Pfad hat. Ein Beispiel wäre ein Angriff, bei dem ein Router auf dem Datenpfad kontrolliert wird. 
  
Die Standardempfehlung und -einstellung für Datenverkehr innerhalb Skype for Business Server ist die Verwendung von mutual TLS (MTLS) zwischen vertrauenswürdigen Servern und TLS von Client zu Server. Diese Schutzmaßnahme würde einen Angriff innerhalb des Zeitraums, in dem eine bestimmte Unterhaltung stattfindet, sehr schwierig oder unmöglich machen. TLS authentifiziert alle Parteien und verschlüsselt den gesamten Datenverkehr. Dies verhindert keine Lauschangriffe, aber der Angreifer kann den Datenverkehr nur lesen, wenn die Verschlüsselung unterbrochen ist.
  
Das TURN-Protokoll (Traversal Using Relay NAT) schreibt nicht vor, dass der Datenverkehr verschlüsselt wird, und die gesendeten Informationen werden durch die Nachrichtenintegrität geschützt. Obwohl es für Lauschangriffe geöffnet ist, können die gesendeten Informationen (d. h. die IP-Adressen und der Port) direkt extrahiert werden, indem Sie einfach die Quell- und Zieladressen der Pakete betrachten. Der A/V-Edgedienst stellt sicher, dass die Daten gültig sind, indem die Nachrichtenintegrität der Nachricht mithilfe des schlüssels überprüft wird, der von einigen Elementen abgeleitet wurde, einschließlich eines TURN-Kennworts, das nie in Klartext gesendet wird. Wenn SRTP (Secure Real Time Protocol) verwendet wird, wird auch der Mediendatenverkehr verschlüsselt.
  
## <a name="identity-spoofing-ip-address-and-caller-id-spoofing"></a>Identitätsspoofing (IP-Adresse und Spoofing der Anrufer-ID)

Identitätsspoofing tritt auf, wenn der Angreifer eine Telefonnummer eines gültigen Benutzers (Anrufer-ID) oder eine IP-Adresse eines Netzwerks, Computers oder einer Netzwerkkomponente ermittelt und verwendet, ohne dazu autorisiert zu sein. Ein erfolgreicher Angriff ermöglicht es dem Angreifer, so zu arbeiten, als wäre der Angreifer die Entität, die normalerweise durch die Telefonnummer (Anrufer-ID) oder die IP-Adresse identifiziert wird.

Im Kontext von Skype for Business Server kommt IP-Adressspoofing nur ins Spiel, wenn ein Administrator die folgenden beiden Aktionen ausgeführt hat:
  
- Konfigurierte Verbindungen, die nur TCP (Transmission Control Protocol) unterstützen (was nicht empfohlen wird, da die TCP-Kommunikation unverschlüsselt ist).
    
- Die IP-Adressen dieser Verbindungen wurden als vertrauenswürdige Hosts gekennzeichnet.
    
Dies ist weniger ein Problem für TLS-Verbindungen (Transport Layer Security), da TLS alle Parteien authentifiziert und den gesamten Datenverkehr verschlüsselt. Die Verwendung von TLS verhindert, dass ein Angreifer IP-Adressspoofing für eine bestimmte Verbindung durchführt (z. B. gegenseitige TLS-Verbindungen). Ein Angreifer könnte jedoch weiterhin die Adresse des DNS-Servers spoofen, der Skype for Business Server verwendet. Da die Authentifizierung in Skype for Business jedoch mit Zertifikaten durchgeführt wird, verfügt ein Angreifer nicht über ein gültiges Zertifikat, das zum Spoofing einer der Parteien in der Kommunikation erforderlich ist.

Andererseits kommt das Spoofing von Anrufer-IDs ins Spiel, wenn Sie einen SIP-Trunk zwischen einem Anbieter, einem PSTN-Gateway oder einer anderen Nebenstellenanlage und Skype for Business Server eingerichtet haben. In diesen Fällen bietet Skype for Business Server keinen Schutz, um Spoofing von Anrufer-IDs zu verhindern. Dies bedeutet, dass ein Skype for Business Benutzer einen Anruf vom SIP-Trunk mit einer gefälschten Anrufer-ID empfangen kann, die die Telefonnummer oder den Anzeigenamen eines anderen Skype for Business Benutzers anzeigt (wenn eine umgekehrte Nummernsuche gilt). Der Schutz hierfür sollte auf anbieterseitigem PSTN- oder PBX-Gateway angewendet werden.
  
## <a name="man-in-the-middle-attack"></a>Man-in-the-Middle-Angriff

Ein Man-in-the-Middle-Angriff tritt auf, wenn ein Angreifer die Kommunikation zwischen zwei Benutzern ohne wissen der beiden kommunizierenden Benutzer über den Computer des Angreifers umleitet. Der Angreifer kann den Datenverkehr überwachen und lesen, bevor er an den gewünschten Empfänger gesendet wird. Jeder Benutzer in der Kommunikation sendet unwissentlich Datenverkehr an den Angreifer und empfängt Datenverkehr vom Angreifer und geht dabei davon aus, dass er nur mit dem beabsichtigten Benutzer kommuniziert. Dies kann passieren, wenn ein Angreifer Active Directory-Domänendienste so ändern kann, dass er seinen Server als vertrauenswürdigen Server hinzufüge, oder domain Name System (DNS) so ändern kann, dass Clients über den Angreifer auf dem Weg zum Server eine Verbindung herstellen können. Ein Man-in-the-Middle-Angriff kann auch bei Mediendatenverkehr zwischen zwei Clients auftreten. In Skype for Business Server Punkt-zu-Punkt-Audio-, Video- und Anwendungsfreigabe werden Datenströme jedoch mit SRTP verschlüsselt, wobei kryptografische Schlüssel verwendet werden, die zwischen den Peers ausgehandelt werden, die SIP (Session Initiation Protocol) über TLS verwenden. Server wie Gruppenchat verwenden HTTPS, um die Sicherheit des Webdatenverkehrs zu erhöhen.
  
## <a name="rtp-replay-attack"></a>Angriff mit Aufzeichnungswiederholung (RTP-Datenverkehr)

Bei einem Angriff mit Aufzeichnungswiederholung wird in böswilliger Absicht eine gültige Medienübertragung zwischen zwei Parteien abgefangen und erneut übertragen. Durch die Verwendung von SRTP in Verbindung mit einem sicheren Signalübermittlungsprotokoll werden Übertragungen vor Angriffen mit Aufzeichnungswiederholung geschützt. Mit SRTP kann der Empfänger einen Index der bereits empfangenen RTP-Pakete erstellen und jedes neue Paket mit den bereits enthaltenen vergleichen.
  
## <a name="spim"></a>Spim

Spim ist unerwünschte kommerzielle Chatnachrichten oder Anwesenheitsabonnementanforderungen. Obwohl es sich nicht allein um eine Kompromittierung des Netzwerks handelt, ist es am wenigsten lästig, kann die Ressourcenverfügbarkeit und -produktion reduzieren und möglicherweise zu einer Gefährdung des Netzwerks führen. Ein Beispiel hierfür sind Benutzer, die sich gegenseitig überlisten, indem sie Anforderungen senden. Benutzer können sich gegenseitig blockieren, um dies zu verhindern. Wenn jedoch ein koordinierter Spim-Angriff hergestellt wird, kann dies schwierig sein, es sei denn, Sie deaktivieren den Partnerverbund.
  
## <a name="viruses-and-worms"></a>Viren und Würmer

Ein Virus ist eine Codeeinheit, deren Zweck darin besteht, zusätzliche, ähnliche Codeeinheiten zu reproduzieren. Um zu funktionieren, benötigt ein Virus einen Host, z. B. eine Datei, eine E-Mail oder ein Programm. A barcode ist eine Codeeinheit, deren Zweck darin besteht, zusätzliche, ähnliche Codeeinheiten zu reproduzieren, benötigt jedoch keinen Host. Viren und Wurme werden in erster Linie bei Dateiübertragungen zwischen Clients oder beim Senden von URLs von anderen Benutzern angezeigt. Wenn sich ein Virus auf Ihrem Computer befindet, kann er beispielsweise Ihre Identität verwenden und Chatnachrichten in Ihrem Namen senden.
  
## <a name="personally-identifiable-information"></a>Informationen zur Identifikation von Personen

Skype for Business Server hat das Potenzial, Informationen über ein öffentliches Netzwerk offenzulegen, die möglicherweise mit einer Einzelperson verknüpft werden können. Bei diesen Informationen kann es sich um zwei Kategorien von Angaben handeln:
  
- **Erweiterte Anwesenheitsdaten** Erweiterte Anwesenheitsdaten sind Informationen, die ein Benutzer über einen Link zu einem Verbundpartner oder mit Kontakten innerhalb einer Organisation freigeben oder nicht freigeben kann. Diese Daten werden nicht für Benutzer in einem öffentlichen Chatnetzwerk freigegeben. Clientrichtlinien und andere Clientkonfigurationen können dem Systemadministrator eine gewisse Kontrolle geben. In Skype for Business Server kann der erweiterte Anwesenheitsdatenschutzmodus für einen einzelnen Benutzer konfiguriert werden, um zu verhindern, dass Skype for Business Benutzer, die sich nicht in der Kontaktliste des Benutzers befinden, die Anwesenheitsinformationen des Benutzers sehen. Der erweiterte Datenschutzmodus für Anwesenheitsinformationen verhindert nicht, dass Benutzer von Microsoft Office Communicator 2007 und Microsoft Office Communicator 2007 R2 die Anwesenheitsinformationen eines Benutzers sehen. Ausführliche Informationen zum Bereitstellen des Clients und der Anwesenheit finden Sie unter [Bereitstellen von Clients für Skype for Business Server](../../deploy/deploy-clients/deploy-clients.md) und Planen der [Chat- und Anwesenheitsinformationen in Skype for Business Server.](../../plan-your-deployment/instant-messaging-and-presence.md)
    
- **Obligatorische Daten** Obligatorische Daten sind für den ordnungsgemäßen Betrieb des Servers oder des Clients erforderlich und unterliegen NICHT der Kontrolle des Clients oder der Systemverwaltung. Es handelt sich um Informationen, die auf Server- oder Netzwerkebene für das Routing, die Statuspflege und die Signalübermittlung erforderlich sind.
    
In den folgenden Tabellen sind die Daten aufgeführt, die über ein öffentliches Netzwerk verfügbar gemacht werden.
  
**Erweiterte Anwesenheitsdaten**

|**Offengelegte Daten**|**Mögliche Einstellungen**|
|:-----|:-----|
|Persönliche Daten  <br/> |Name, Titel, Unternehmen, E-Mail-Adresse, Zeitzone  <br/> |
|Telefonnummern  <br/> |Geschäftlich, mobil, privat  <br/> |
|Kalenderdaten  <br/> |Frei/Gebucht, Abwesenheitshinweis, Besprechungsdetails (für Personen, die Zugriff auf Ihren Kalender haben)  <br/> |
|Anwesenheitsstatus  <br/> |Abwesend, verfügbar, gebucht, nicht stören, offline  <br/> |
   
**Pflichtdaten**


| **Offengelegte Daten** | **Beispielinformationen**                            |
|:-------------------|:---------------------------------------------------|
| IP-Adresse  <br/>  | Tatsächliche Computer- oder NAT-Adresse  <br/> |
| SIP-URI  <br/>     | jeremylos@litwareinc.com  <br/>                    |

