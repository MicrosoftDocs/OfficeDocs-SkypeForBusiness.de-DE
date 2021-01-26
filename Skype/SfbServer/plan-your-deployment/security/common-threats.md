---
title: Häufige Sicherheitsbedrohungen in modernen Computern
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
description: Da Skype for Business Server ein Kommunikationssystem der Unternehmensklasse ist, sollten Sie sich der allgemeinen Sicherheitsangriffe bewusst sein, die sich auf die Infrastruktur und Kommunikation auswirken könnten.
ms.openlocfilehash: d2eff9346c1c2d00af9fb0789f652dfe072702f0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832225"
---
# <a name="common-security-threats-in-modern-day-computing"></a>Häufige Sicherheitsbedrohungen in modernen Computern
 
Da Skype for Business Server ein Kommunikationssystem der Unternehmensklasse ist, sollten Sie sich der allgemeinen Sicherheitsangriffe bewusst sein, die sich auf die Infrastruktur und Kommunikation auswirken könnten.
  
## <a name="compromised-key-attack"></a>Angriff mit kompromittierten Schlüsseln

Ein Schlüssel ist ein geheimer Code oder eine geheime Nummer zur Verschlüsselung, Entschlüsselung oder Überprüfung geheimer Informationen. In der Public Key Infrastructure (PKI) werden zwei vertrauliche Schlüssel verwendet, die berücksichtigt werden müssen: 
  
- Der private Schlüssel, über den jeder Zertifikatinhaber verfügt
    
- Der Sitzungsschlüssel, der nach einem erfolgreichen Austausch von Identifikations- und Sitzungsschlüsseln durch die kommunizierenden Partner verwendet wird
    
Ein Angriff mit kompromittierten Schlüsseln liegt vor, wenn der Angreifer den privaten Schlüssel oder den Sitzungsschlüssel ermittelt. Gelingt dem Angreifer die Ermittlung des Schlüssels, kann er den Schlüssel zum Entschlüsseln verschlüsselter Daten ohne Wissen des Absenders verwenden.
  
Skype for Business Server verwendet die PKI-Funktionen im Windows Server-Betriebssystem, um die Schlüsseldaten zu schützen, die für die Verschlüsselung für die Transport Layer Security (TLS)-Verbindungen verwendet werden. Die für die Medienverschlüsselung verwendeten Schlüssel werden über TLS-Verbindungen ausgetauscht.
  
## <a name="network-denial-of-service-attack"></a>Denial-of-Service-Angriff auf das Netzwerk

Ein Denial-of-Service-Angriff liegt vor, wenn der Angreifer die normale Netzwerknutzung durch gültige Benutzer verhindert. Dies geschieht, wenn der Angreifer den Dienst mit legitimen Anforderungen überflutet, die die Nutzung des Diensts durch legitime Benutzer überfordern. Mithilfe eines Denial-of-Service-Angriffs kann der Angreifer folgendes tun:
  
- Er kann ungültige Daten an Anwendungen und Dienste senden, die in dem angegriffenen Netzwerk ausgeführt werden, um ihre Funktionsweise zu beeinträchtigen.
    
- Er kann große Datenmengen senden, um das System zu überlasten, bis es nicht mehr oder nur noch verzögert auf legitime Anforderungen reagiert.
    
- Er kann die Spuren seines Angriffs vertuschen.
    
- Er kann Benutzer vom Zugriff auf die Netzwerkressourcen abhalten.
    
## <a name="eavesdropping-sniffing-snooping"></a>Abhören (Sniffing, Snooping)

Abhöraktionen sind Aktionen, bei denen ein Angreifer Zugriff auf den Datenpfad in einem Netzwerk erlangt und anschließend den Datenverkehr überwachen und lesen kann. Dies wird auch als "Schnüffeln" (auch Lauschangriff, englisch "Sniffing" oder "Snooping") bezeichnet. Wenn der Datenverkehr aus reinem Text besteht, kann der Angreifer ihn lesen, sobald er Zugriff auf den Pfad hat. Ein Beispiel wäre ein Angriff, bei dem ein Router auf dem Datenpfad kontrolliert wird. 
  
Die Standardempfehlung und -einstellung für Datenverkehr in Skype for Business Server ist die Verwendung von MTLS (Mutual TLS) zwischen vertrauenswürdigen Servern und TLS von Client zu Server. Diese Schutzmaßnahme würde einen Angriff innerhalb des Zeitraums, in dem eine bestimmte Unterhaltung stattfindet, sehr schwierig oder unmöglich machen. TLS authentifiziert alle Parteien und verschlüsselt den datenverkehr. Dies verhindert keine Lauschangriffe, aber der Angreifer kann den Datenverkehr nur lesen, wenn die Verschlüsselung unterbrochen ist.
  
Das Traversal Using Relay NAT (TURN)-Protokoll sieht nicht vor, dass der Datenverkehr verschlüsselt wird und die gesendeten Informationen durch die Nachrichtenintegrität geschützt werden. Obwohl es für Lauschangriffe offen ist, können die gesendeten Informationen (d. h. die IP-Adressen und der Port) direkt extrahiert werden, indem einfach die Quell- und Zieladressen der Pakete betrachtet werden. Der A/V-Edgedienst stellt sicher, dass die Daten gültig sind, indem er die Nachrichtenintegrität der Nachricht mithilfe des schlüssels überprüft, der von einigen wenigen Elementen abgeleitet wurde, einschließlich eines TURN-Kennworts, das nie als Klartext gesendet wird. Wenn SRTP (Secure Real Time Protocol) verwendet wird, wird auch der Mediendatenverkehr verschlüsselt.
  
## <a name="identity-spoofing-ip-address-and-caller-id-spoofing"></a>Identitätss spoofing (IP-Adresse und Spoofing der Anrufer-ID)

Identitätss spoofing tritt auf, wenn der Angreifer eine Telefonnummer eines gültigen Benutzers (Anrufer-ID) oder eine IP-Adresse eines Netzwerks, Computers oder einer Netzwerkkomponente ermittelt und verwendet, ohne dazu autorisiert zu sein. Bei einem erfolgreichen Angriff kann der Angreifer so arbeiten, als ob es sich bei dem Angreifer um die Entität handelt, die normalerweise durch die Telefonnummer (Anrufer-ID) oder die IP-Adresse identifiziert wird.

Im Kontext von Skype for Business Server kommt spoofing von IP-Adressen nur ins Spiel, wenn ein Administrator beide der folgenden Aufgaben ausgeführt hat:
  
- Konfigurierte Verbindungen, die nur TCP (Transmission Control Protocol) unterstützen (dies wird nicht empfohlen, da die TCP-Kommunikation unverschlüsselt ist).
    
- Die IP-Adressen dieser Verbindungen wurden als vertrauenswürdige Hosts gekennzeichnet.
    
Dies ist weniger ein Problem für Transport Layer Security (TLS)-Verbindungen, da TLS alle Parteien authentifiziert und den datenverkehr verschlüsselt. Die Verwendung von TLS verhindert, dass ein Angreifer das Spoofing von IP-Adressen für eine bestimmte Verbindung (z. B. gegenseitige TLS-Verbindungen) ausführen kann. Ein Angreifer könnte aber dennoch die Adresse des von Skype for Business Server verwendeten DNS-Servers spoofing. Da die Authentifizierung in Skype for Business jedoch mit Zertifikaten erfolgt, hat ein Angreifer kein gültiges Zertifikat, das erforderlich ist, um eine der Kommunikationsparteien zu spoofieren.

Andererseits kommt Spoofing der Anrufer-ID ins Spiel, wenn Sie einen SIP-Trunk zwischen einem Anbieter, einem PSTN-Gateway oder einem anderen Nebenstellensystem und Skype for Business Server eingerichtet haben. In diesen Fällen bietet Skype for Business Server keinen Schutz gegen Spoofing von Anrufer-IDs. Dies bedeutet, dass ein Skype for Business-Benutzer einen Anruf vom SIP-Trunk mit einer gefälschten Anrufer-ID empfangen kann, die die Telefonnummer oder den Anzeigenamen eines anderen Skype for Business-Benutzers (falls eine umgekehrte Nummern-Suche vorkommt) angezeigt wird. Dieser Schutz sollte auf Anbieterseite, PSTN- oder Nebenstellenanlagengateway angewendet werden.
  
## <a name="man-in-the-middle-attack"></a>Man-in-the-Middle-Angriff

Ein Man-in-the-Middle-Angriff tritt auf, wenn ein Angreifer die Kommunikation zwischen zwei Benutzern ohne Wissen der beiden kommunizierenden Benutzer über den Computer des Angreifers umgeleitet. Der Angreifer kann den Datenverkehr überwachen und lesen, bevor er an den vorgesehenen Empfänger gesendet wird. Jeder Benutzer in der Kommunikation sendet unwissentlich Datenverkehr an den Angreifer und empfängt ihn, während er davon aus ist, dass er nur mit dem beabsichtigten Benutzer kommuniziert. Dies kann passieren, wenn ein Angreifer Active Directory Domain Services ändern kann, um seinen Server als vertrauenswürdigen Server hinzuzufügen, oder dns (Domain Name System) so ändern kann, dass Clients über den Angreifer auf dem Weg zum Server eine Verbindung herstellen können. Ein Man-in-the-Middle-Angriff kann auch mit Mediendatenverkehr zwischen zwei Clients auftreten. In Skype for Business Server werden Datenströme in Punkt-zu-Punkt-Audio-, Video- und Anwendungsfreigaben jedoch mit SRTP verschlüsselt. Dabei werden kryptografische Schlüssel verwendet, die zwischen den Peers ausgehandelt werden, die SIP (Session Initiation Protocol) über TLS verwenden. Server wie Gruppenchat nutzen HTTPS, um die Sicherheit des Webdatenverkehrs zu erhöhen.
  
## <a name="rtp-replay-attack"></a>Angriff mit Aufzeichnungswiederholung (RTP-Datenverkehr)

Bei einem Angriff mit Aufzeichnungswiederholung wird in böswilliger Absicht eine gültige Medienübertragung zwischen zwei Parteien abgefangen und erneut übertragen. Durch die Verwendung von SRTP in Verbindung mit einem sicheren Signalübermittlungsprotokoll werden Übertragungen vor Angriffen mit Aufzeichnungswiederholung geschützt. Mit SRTP kann der Empfänger einen Index der bereits empfangenen RTP-Pakete erstellen und jedes neue Paket mit den bereits enthaltenen vergleichen.
  
## <a name="spim"></a>Spim

Spim sind unerwünschte kommerzielle Chatnachrichten oder Anwesenheitsabonnements. Obwohl es sich nicht allein um eine Lästerung des Netzwerks handelt, ist es zumindest lästig, kann die Ressourcenverfügbarkeit und die Produktion reduzieren und möglicherweise zu einer Romittierung des Netzwerks führen. Ein Beispiel hierin sind Benutzer, die sich gegenseitig durch Senden von Anforderungen ausspionieren. Benutzer können sich gegenseitig blockieren, um dies zu verhindern. Wenn jedoch ein koordinierter Spimangriff eingerichtet wird, kann dies schwierig zu überwinden sein, es sei denn, Sie deaktivieren den Partnerverbund.
  
## <a name="viruses-and-worms"></a>Viren und Würmer

Ein Virus ist eine Codeeinheit, deren Zweck die Reproduzieren zusätzlicher, ähnlicher Codeeinheiten ist. Damit ein Virus funktioniert, benötigt er einen Host, z. B. eine Datei, eine E-Mail oder ein Programm. Ein Wurm ist eine Codeeinheit, deren Zweck es ist, zusätzliche, ähnliche Codeeinheiten zu reproduzieren, benötigt jedoch keinen Host. Viren und Würmer werden in erster Linie bei Dateiübertragungen zwischen Clients oder beim Versand von URLs von anderen Benutzern angezeigt. Wenn sich ein Virus auf Ihrem Computer befindet, kann er beispielsweise Ihre Identität verwenden und Chatnachrichten in Ihrem Auftrag senden.
  
## <a name="personally-identifiable-information"></a>Informationen zur Identifikation von Personen

Skype for Business Server kann Informationen über ein öffentliches Netzwerk offenlegen, die möglicherweise mit einer Einzelperson verknüpft werden können. Bei diesen Informationen kann es sich um zwei Kategorien von Angaben handeln:
  
- **Erweiterte Anwesenheitsdaten** Erweiterte Anwesenheitsdaten sind Informationen, die ein Benutzer über einen Link zu einem Verbundpartner oder mit Kontakten innerhalb einer Organisation freigeben kann. Diese Daten werden nicht für Benutzer in einem öffentlichen Impernetz freigegeben. Clientrichtlinien und andere Clientkonfigurationen können eine gewisse Kontrolle über den Systemadministrator haben. In Skype for Business Server kann der erweiterte Datenschutzmodus für Anwesenheitsinformationen für einen einzelnen Benutzer konfiguriert werden, um zu verhindern, dass Skype for Business-Benutzer, die nicht in der Kontaktliste des Benutzers enthalten sind, die Anwesenheitsinformationen des Benutzers sehen. Der erweiterte Datenschutzmodus für Anwesenheitsinformationen verhindert nicht, dass Benutzer von Microsoft Office Communicator 2007 und Microsoft Office Communicator 2007 R2 die Anwesenheitsinformationen eines Benutzers sehen. Weitere Informationen zum Bereitstellen des Clients und der Anwesenheit finden Sie unter "Bereitstellen von Clients für [Skype for Business Server"](../../deploy/deploy-clients/deploy-clients.md) und "Planen von Chat und Anwesenheit [in Skype for Business Server".](../../plan-your-deployment/instant-messaging-and-presence.md)
    
- **Pflichtdaten** Erforderliche Daten sind für den ordnungsgemäßen Betrieb des Servers oder Clients erforderlich und werden nicht von der Client- oder Systemverwaltung kontrolliert. Es handelt sich um Informationen, die auf Server- oder Netzwerkebene für das Routing, die Statuspflege und die Signalübermittlung erforderlich sind.
    
In den folgenden Tabellen sind die Daten aufgeführt, die über ein öffentliches Netzwerk verfügbar gemacht werden.
  
**Erweiterte Anwesenheitsdaten**

|**Offengelegte Daten**|**Mögliche Einstellungen**|
|:-----|:-----|
|Persönliche Daten  <br/> |Name, Titel, Unternehmen, E-Mail-Adresse, Zeitzone  <br/> |
|Telefonnummern  <br/> |Geschäftlich, mobil, privat  <br/> |
|Kalenderdaten  <br/> |Frei/Gebucht-Informationen, Benachrichtigungen zu Nicht-Ortsinformationen, Besprechungsdetails (für Personen, die Zugriff auf Ihren Kalender haben)  <br/> |
|Anwesenheitsstatus  <br/> |Abwesend, verfügbar, gebucht, nicht stören, offline  <br/> |
   
**Pflichtdaten**


| **Offengelegte Daten** | **Beispielinformationen**                            |
|:-------------------|:---------------------------------------------------|
| IP-Adresse  <br/>  | Tatsächliche Computer- oder NAT-Adresse  <br/> |
| SIP-URI  <br/>     | jeremylos@litwareinc.com  <br/>                    |

