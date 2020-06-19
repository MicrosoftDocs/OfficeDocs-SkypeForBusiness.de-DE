---
title: Teams Voice Contoso-Fallstudie
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams Voice Case Study für Multi-National Corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7431515d40550a3f731c34f97ed8c10586424901
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786025"
---
# <a name="contoso-case-study-phone-system"></a>Contoso-Fallstudie: Telefon System

Je nach geographischem Standort und anderen Faktoren hatte Contoso Offices mit den folgenden Telefonie-Lösungen:

- Websitetyp A: Skype for Business Enterprise-VoIP

- Website Typ B: herkömmliche Legacy-Telefoniesysteme

- Websitetyp C: eine Kombination aus Skype for Business Enterprise-VoIP und herkömmlichem Legacy-Telefoniesystem


Um eine Microsoft Phone-Systemlösung für Ihre gesamte Organisation zu implementieren, musste Contoso &mdash; für jeden Websitetyp ermitteln, &mdash; welche der folgenden Optionen für das Telefonsystem verwendet werden soll, um eine Verbindung mit dem öffentlichen Telefonnetz (PSTN) herzustellen:

- Telefon System mit Anrufplan 

- Telefon System mit eigenem PSTN-Netzbetreiber über direktes Routing 

- Kombination aus Telefonsystem mit Anrufplan und Telefonsystem mit eigenem PSTN-Netzbetreiber über direktes Routing
 
Um die richtige Lösung für Ihre Organisation zu ermitteln, verwendete Contoso [Microsoft-Telefonie-Lösungen](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) und die Ignite-2019-Session- [Anrufe in Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a>Websitetyp A: Skype for Business Enterprise-VoIP 

Contoso Skype for Business Enterprise-VoIP wurde als Hub eingerichtet und sprach. Es gab einen zentralen Standort, an dem das PSTN-Gateway in der Region verwaltet wurde, die die Verbindung mit dem PSTN für die Skype for Business Enterprise-VoIP-Benutzer in Land bereitgestellt hat. Oft hatten diese Satellitenbüros keinen eigenen Internet-Ausstieg. Die Nummern für diese Benutzer befanden sich im SIP-Stamm, der eine Verbindung mit einem vorhandenen SBC herstellt. 

Um festzustellen, ob der bereits bereitgestellte SBC für Direct Routing und medienumgehung zertifiziert ist, hat Contoso die [Liste der für die direkte Weiterleitung zertifizierten Session Border Controller](direct-routing-border-controllers.md)überprüft.  

Die Wählgewohnheiten des Benutzers waren die Wahl eines Benutzers im Legacy-Telefoniesystem mithilfe einer Durchwahl, auch wenn der Benutzer einen Skype for Business-Client für Peer-to-Peer-Audio zur Verfügung hat. 

Contoso hat ihre Entscheidung auf die folgenden Fragen gestützt:

- F. Müssen die von der lokalen Bereitstellung bereitgestellten Funktionen beibehalten werden?<br>
  Eine. Nein 

- F. Müssen wir mit PBX-Anlagen und anderen Telefonanlagen von Drittanbietern kooperieren?<br>
  Eine. Nein 

- F. Müssen wir unseren derzeitigen Drittanbieter behalten?<br> A. ja (regulierte Länder) und Nein 

- F. Muss der ROI für SBCS bereitgestellt werden?<br> A. ja und Nein  

- F. Steht Microsoft PSTN-Anrufpläne in dieser Region zur Verfügung?<br> A. ja und Nein 

Basierend auf den Antworten auf Ihre Fragen beschloss contoso, Folgendes zu tun:

- Verschieben Sie die Benutzer, die sich in einem Bereich befinden, in dem PSTN-Anrufpläne für das Telefon System mit Anrufplänen verfügbar sind. 

- Verschieben Sie die Benutzer, die sich nicht in einem Bereich befinden, in dem PSTN-Anrufpläne verfügbar sind, Benutzer, die sich auf einer Website befinden, auf der der ROI auf dem SBCS noch nicht erfüllt ist, und Benutzer, die in einem Land gewohnt sind, das Telefonanlagen mit direktem Routing für Telefonsysteme besitzt. 

Das folgende Diagramm zeigt die anfängliche Bereitstellung von Skype for Business Enterprise-VoIP und wie diese Bereitstellung sowohl in Microsoft-Anrufpläne als auch direktes Routing migriert wurde:

![Diagramm, das vor und nach Zuständen angezeigt wird](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a>Website Typ B: herkömmliche Legacy-Telefoniesysteme

Contoso hatte viele Offices, in denen Legacy-Telefoniesysteme genutzt wurden. Es gab eine Teilmenge der Benutzer, die eine e-1.64-Telefonnummer hatten, während andere nur eine Durchwahl hatten. Diese Nummern befanden sich auf dem TDM-Stamm des PSTN-Gateways. Die Intra-Site-Wählfunktion wurde durch Nutzung eines Website Codes vor der Erweiterung konfiguriert, um zu bestimmen, wohin der Anruf weitergeleitet werden soll. Die Wählgewohnheiten der Benutzer waren die Durchwahl.   

Contoso hat ihre Entscheidung auf die folgenden Fragen gestützt:

- F. Müssen die von der lokalen Bereitstellung bereitgestellten Funktionen beibehalten werden?<br>
  Eine. Nein 

- F. Müssen wir mit PBX-Anlagen und anderen Telefonanlagen von Drittanbietern kooperieren?<br> A. ja

- F. Müssen wir unseren derzeitigen Drittanbieter behalten?<br> A. Nein 

- F. Steht der Anrufplan von Microsoft PSTN in unserer Region zur Verfügung?<br> A. ja und Nein 

Basierend auf den Antworten auf Ihre Fragen beschloss contoso, Folgendes zu tun: 

- Verschieben Sie die Benutzer, die sich in einem Bereich befinden, in dem PSTN-Anrufpläne für das Telefon System mit Anrufplänen verfügbar sind. 

- Verschieben Sie die Benutzer, die sich nicht in einem Bereich befinden, in dem PSTN-Anrufpläne für das Telefon System mit direktem Routing verfügbar sind. 

- Verwalten Sie eine PSTN-Verbindung mit geschäftlichen kritischen analogen Geräten.

Die folgenden Diagramme zeigen die ursprüngliche Bereitstellung von Legacysystemen mit Remotestandorten und die Migration zu einer direkten Routing Bereitstellung mit lokaler Medienoptimierung:

**Ursprüngliche Legacy Bereitstellung**  
 ![ Diagramm, das vor und nach Zuständen angezeigt wird](media/voice-case-study-2.png)


**Bereitstellung mit direktem Routing**

![Diagramm, das vor und nach Zuständen angezeigt wird](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a>Website Typ C: Kombination von Skype for Business Enterprise-VoIP und herkömmlichem Legacy-Telefoniesystem

Die Nummern der Contoso-Skype for Business Enterprise-VoIP-Nutzer befinden sich auf dem SIP-Stamm im SBC vom Netzbetreiber. Die Nummern für die herkömmlichen Telefoniesysteme befanden sich auf dem TDM-Stamm für das PSTN-Gateway.   

Contoso hat ihre Entscheidung auf die folgenden Fragen gestützt:

- F. Müssen die von der lokalen Bereitstellung bereitgestellten Funktionen beibehalten werden?<br>
  Eine. Nein 

- F. Müssen wir mit PBX-Anlagen und anderen Telefonanlagen von Drittanbietern kooperieren?<br> A. Nein 

- F. Müssen wir unseren derzeitigen Drittanbieter behalten?<br> A. Nein 

- F. Muss der ROI für SBCS bereitgestellt werden?<br> A. ja und Nein  

- F. Steht der PSTN-Anrufplan von Microsoft in dieser Region zur Verfügung?<br> A. Nein 

Basierend auf den Antworten auf Ihre Fragen beschloss Contoso Folgendes: 

- Für die Legacy-Telefonie-Benutzer, die für die direkte Weiterleitung aktiviert werden, hat Contoso die Nummern aus dem TDM-Stamm an den SIP-Stamm für den SBC portiert, da der SBC für das direkte Routing zertifiziert ist. 

- Um eine Teilmenge der Benutzer zu unterstützen, die in das Telefonsystem wechseln, und um die fortgesetzte Weiterleitung über das Legacy System zu ermöglichen, wurde das Legacy-Telefoniesystem als nächster Hop zum SBC eingerichtet.   

- Darüber hinaus hat Contoso für die Verwendung von Teams für alle internen Anrufe Anleitungen bereitgestellt, um das Benutzerverhalten zu unterstützen und die Abhängigkeit von Wähleinstellungen für Inter-und Intra-Site-Erweiterungen zu entfernen.  

Die folgenden Diagramme zeigen die ursprüngliche Bereitstellung von Skype for Business Enterprise-VoIP und des Legacy-Telefonie-Systems sowie die Migration zu einer gemischten Bereitstellung mithilfe des direkten Routings:

**Ursprüngliche gemischte Bereitstellung** 
 ![ Diagramm, das vor dem Zustand angezeigt wird](media/voice-case-study-4.png)

**Gemischte Bereitstellung mit direktem Routing** 
 ![ Diagramm, das vor dem Zustand angezeigt wird](media/voice-case-study-4a.png)


## <a name="calling-plans"></a>Anrufpläne

Um die Konfigurationsanforderungen für Anrufpläne zu ermitteln, hat Contoso die [grundlegenden Bereitstellungsentscheidungen des Anruf Plans](calling-plan-landing-page.md#core-deployment-decisions)überprüft. Es wurden die folgenden Entscheidungen getroffen: 

- F. Benötigen meine Nutzer Auslandsanrufe?<br> A. ja 

- F. Haben meine Benutzer jeweils eine direkte nach innen Telefonnummer?<br> A. nicht heute. Alle aktivierten Benutzer erhalten eine did-Funktion. 

- F. Soll die Rufnummernanzeige maskiert oder deaktiviert werden?<br> A. die Rufnummernanzeige für einen Benutzer wird mit der lokalen Nummer für Contoso maskiert. 


## <a name="direct-routing"></a>Direktes Routing

Contoso hat Ignite besucht, um auf Office 365-Features, einschließlich verfügbarer Telefone und direktes Routing, auf dem Laufenden zu bleiben. Technische Leitung und Architekten verwendeten die Anleitungen, die während des Ignite 2019 zur Verfügung gestellt wurden, um deren Richtung festzulegen.  Wichtige Sitzungen, die verwendet wurden: 

- [Planen des Erfolgs mit Microsoft Teams Direct Routing](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [Updates für das direkte Routing](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a>Konfiguration

### <a name="calling-plans-sites"></a>Websites für Anrufpläne

Um Lizenzen zu erhalten und Benutzern Telefonnummern zuzuweisen, befolgte Contoso die Schritte unter [Einrichten von Anrufplänen](set-up-calling-plans.md). 

Aufgrund der Anzahl der Benutzer, denen Telefonnummern zugewiesen werden mussten, beschloss contoso, die Telefonnummern mithilfe von PowerShell zuzuweisen. Informationen zum Zuweisen von Zahlen mithilfe von PowerShell &mdash; sowie zu anderen Einstellungen, die von Contoso verwendet werden, finden Sie in &mdash; der [Übersicht über Teams PowerShell](teams-powershell-overview.md).  

### <a name="direct-routing-sites"></a>Direktes Routing von Websites

Um die lokale Telefonie-Infrastruktur von Contoso mit Microsoft Teams zu verbinden, befolgte der Contoso-Administrator die Schritte unter [Konfigurieren des direkten Routings](direct-routing-configure.md) und überprüfte das Video- [Direct-Routing in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) , um Anleitungen zu erhalten.  Contoso bezog sich auch auf die Dokumentation zur direkten Routing Bereitstellung durch den Certified SBC-Anbieter. 

Nachdem das direkte Routing zwischen dem SBC-und dem Microsoft Phone-System konfiguriert wurde, musste Contoso die Konfiguration testen. Zu diesem Zweck haben Contoso-Administratoren den SIP-Tester-Client verwendet, der in der [Sitzung Updates für Direct Routing bei Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions)besprochen wurde. Das SIP-Tester-Clientskript und die Dokumentation wurden aus dem PowerShell-Skript heruntergeladen, um die Verbindungen des direkten Routing Sitzung-Grenz Controllers zu testen.   


### <a name="local-media-optimization"></a>Lokale Medienoptimierung

Contoso erkannte die Möglichkeit, die lokale Medienoptimierung in den verschiedenen Regionen weltweit zu nutzen. Die unterstützten Szenarien für Contoso werden in der [lokalen Medienoptimierung für das direkte Routing](direct-routing-media-optimization.md)beschrieben. Die Konfiguration der lokalen Medienoptimierung erfolgte durch die folgenden Anleitungen sowohl des SBC-Anbieters als auch von Microsoft. Zu den Konfigurationsschritten für die lokale Medienoptimierung gehören: 

- Konfigurieren der Benutzer-und SBC-Websites 

- Konfigurieren Sie den SBC gemäß der SBC-Lieferanten Spezifikation, 

- Hinzufügen externer vertrauenswürdiger IP-Adressen zu jeder Website, die für die lokale Medienoptimierung verwendet wird    

- Definieren der Netzwerktopologie 

- Definieren der virtuellen Netzwerktopologie 

- Ermitteln des Modus: immer umgehen oder nur für lokale Benutzer 

## <a name="networking-considerations"></a>Netzwerküberlegungen

Contoso hatte eine Reihe von Benutzern, die über einen längeren Zeitraum Remote arbeiten mussten, nachdem Sie für das Telefon System aktiviert wurden. Die Benutzer haben VPN für den Zugriff auf bestimmte Branchenanwendungen verwendet. Während Sie sich im VPN befanden, erfuhren die Benutzer des Telefonsystems eine Verschlechterung der Anrufqualität. 

Um das Qualitätsproblem zu beheben, hat Contoso VPN-Split-Tunneling implementiert, wodurch der Office 365-Datenverkehr das Internet durchlaufen konnte, während die Verbindung zu den internen apps auf dem VPN verblieb. Um VPN-Split-Tunneling zu implementieren, folgte Contoso den Anleitungen [für die Implementierung von VPN-Split-Tunneling für Office 365](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel).  

 





