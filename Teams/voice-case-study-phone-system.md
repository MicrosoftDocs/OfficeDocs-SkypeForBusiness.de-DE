---
title: 'Contoso-Fallstudie: Telefonsystem für ein multinationales Unternehmen'
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
description: 'Teams Voice Case Study für multinationale Unternehmen: Telefonsystem'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 95ba8e36948a3d61a2e81f9c1954919709eb3a77
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823666"
---
# <a name="contoso-case-study-phone-system-for-a-multi-national-corporation"></a>Contoso-Fallstudie: Telefonsystem für ein multinationales Unternehmen

Je nach geografischem Standort und anderen Faktoren verfügte Contoso über Büros mit den folgenden Telefonielösungen:

- Websitetyp A: Skype for Business Enterprise-VoIP

- Standorttyp B: Herkömmliche Legacy-Telefoniesysteme

- Standorttyp C: Eine Kombination aus Skype for Business Enterprise-VoIP und herkömmlichen Legacy-Telefoniesystemen


Um eine Microsoft-Telefon Systemlösung für die gesamte Organisation zu implementieren, musste Contoso für jeden Standorttyp&mdash;ermitteln&mdash;, welche der folgenden Optionen mit Telefonsystem zum Herstellen einer Verbindung mit dem Telefonfestnetz (Public Switched Telephone Network, PSTN) verwendet werden würde:

- Telefonsystem mit Anrufplan 

- Telefonsystem mit einem eigenen PSTN-Netzbetreiber über Direct Routing 

- Kombination von Telefonsystem mit Anrufplan und Telefonsystem mit eigenem PSTN-Netzbetreiber über Direct Routing
 
Um die richtige Lösung für ihre Organisation zu ermitteln, verwendete Contoso ["Plan your Teams Voice Solution](/microsoftteams/cloud-voice-landing-page)" und die Ignite 2019 Session [Calling in Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/what-s-new-for-calling-in-microsoft-teams-ignite-2019-edition/ba-p/974935).  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a>Websitetyp A: Skype for Business Enterprise-VoIP 

Contoso Skype for Business Enterprise-VoIP wurde als Hub und Speichen eingerichtet. Es gab einen zentralen Standort, an dem das PSTN-Gateway in der Region verwaltet wurde, das die Verbindung mit dem PSTN für die Skype for Business Enterprise-VoIP Benutzer im Land bereitstellte. Oft hatten diese Satellitenbüros keinen eigenen Internetausgang. Die Nummern für diese Benutzer befinden sich im SIP-Trunk, der eine Verbindung mit einem vorhandenen SBC herstellt. 

Um festzustellen, ob der bereits bereitgestellte SBC für Direct Routing und Medienumgehung zertifiziert ist, überprüfte Contoso die [Liste der session border controllers, die für Direct Routing zertifiziert sind](direct-routing-border-controllers.md).  

Die Wählgewohnheiten des Benutzers waren die Wahl eines Benutzers im älteren Telefoniesystem mithilfe einer Erweiterung, auch wenn der Benutzer über einen Skype for Business-Client für Peer-to-Peer-Audio verfügt. 

Contoso hat seine Entscheidung auf die folgenden Fragen gestützt:

- Q. Müssen wir die von unserer lokalen Bereitstellung bereitgestellte Funktionalität beibehalten?<br>
  Eine. Nein 

- Q. Müssen wir mit Nebenstellenanlagen von Drittanbietern und anderen Telefoniegeräten zusammenarbeiten?<br>
  Eine. Nein 

- Q. Müssen wir unseren derzeitigen Drittanbieter beibehalten?<br> Eine. Ja (geregelte Länder) und Nein 

- Q. Müssen wir den ROI auf SBCs bereitstellen?<br> Eine. Ja und Nein  

- Q. Sind Microsoft PSTN-Anrufpläne in dieser Region verfügbar?<br> Eine. Ja und Nein 

Basierend auf den Antworten auf ihre Fragen entschied sich Contoso für Folgendes:

- Verschieben Sie die Benutzer, die sich in einer Region befinden, in der PSTN-Anrufpläne für Telefonsystem mit Anrufplänen verfügbar sind. 

- Verschieben Sie die Benutzer, die sich nicht in einer Region befinden, in der PSTN-Anrufpläne verfügbar sind, Benutzer an einem Standort, an dem der ROI auf den SBCs noch nicht erreicht werden muss, und Benutzer, die sich in einem Land mit Telefonievorschriften befinden, um mit Direct Routing zu Telefonsystem. 

Das folgende Diagramm zeigt die anfängliche Skype for Business Enterprise-VoIP Bereitstellung und wie diese Bereitstellung sowohl zu Microsoft-Anrufplänen als auch zu Direct Routing migriert wurde:

![Diagramm zeigt Vor- und Nachher-Zustände.](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a>Standorttyp B: Herkömmliche Legacy-Telefoniesysteme

Contoso hatte viele Büros, die ältere Telefoniesysteme nutzten. Es gab eine Teilmenge von Benutzern, die eine E1.64-Telefonnummer hatten, während andere nur über eine Erweiterung verfügten. Diese Nummern befinden sich im TDM-Trunk zum PSTN-Gateway. Die Standortinterne Wählfunktion wurde konfiguriert, indem ein Standortcode vor der Erweiterung verwendet wurde, um zu bestimmen, wohin der Anruf weitergeleitet werden soll. Die Wählgewohnheiten der Benutzer waren, per Durchwahl zu wählen.   

Contoso hat seine Entscheidung auf die folgenden Fragen gestützt:

- Q. Müssen wir die von unserer lokalen Bereitstellung bereitgestellte Funktionalität beibehalten?<br>
  Eine. Nein 

- Q. Müssen wir mit Nebenstellenanlagen von Drittanbietern und anderen Telefoniegeräten zusammenarbeiten?<br> Eine. Ja

- Q. Müssen wir unseren derzeitigen Drittanbieter beibehalten?<br> Eine. Nein 

- Q. Ist der Anrufplan von Microsoft PSTN in unserer Region verfügbar?<br> Eine. Ja und Nein 

Basierend auf den Antworten auf ihre Fragen entschied sich Contoso für Folgendes: 

- Verschieben Sie die Benutzer, die sich in einer Region befinden, in der PSTN-Anrufpläne für Telefonsystem mit Anrufplänen verfügbar sind. 

- Verschieben Sie die Benutzer, die sich nicht in einer Region befinden, in der PSTN-Anrufpläne für Telefonsystem mit Direct Routing verfügbar sind. 

- Halten Sie eine PSTN-Verbindung mit unternehmenskritischen analogen Geräten aufrecht.

Die folgenden Diagramme zeigen die ursprüngliche Legacysystembereitstellung mit Remotestandorten und die Migration zu einer Direct Routing-Bereitstellung mit lokaler Medienoptimierung:

**Ursprüngliche Legacybereitstellung** 
![ Ein Diagramm zeigt vor und nach Zuständen.](media/voice-case-study-2.png)


**Bereitstellung mit Direct Routing**

![Ein Diagramm mit den Zuständen vor und nach.](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a>Standorttyp C: Kombination aus Skype for Business Enterprise-VoIP und herkömmlichen Legacy-Telefoniesystemen

Contoso Skype for Business Enterprise-VoIP Benutzernummern befinden sich im SIP-Trunk des Netzbetreibers an den SBC. Die Nummern für die herkömmlichen Telefoniesysteme befinden sich auf dem TDM-Trunk zum PSTN-Gateway.   

Contoso hat seine Entscheidung auf die folgenden Fragen gestützt:

- Q. Müssen wir die von unserer lokalen Bereitstellung bereitgestellte Funktionalität beibehalten?<br>
  Eine. Nein 

- Q. Müssen wir mit Nebenstellenanlagen von Drittanbietern und anderen Telefoniegeräten zusammenarbeiten?<br> Eine. Nein 

- Q. Müssen wir unseren derzeitigen Drittanbieter beibehalten?<br> Eine. Nein 

- Q. Müssen wir den ROI auf SBCs bereitstellen?<br> Eine. Ja und Nein  

- Q. Ist der PSTN-Anrufplan von Microsoft in dieser Region verfügbar?<br> Eine. Nein 

Basierend auf den Antworten auf ihre Fragen entschied Contoso Folgendes: 

- Für ältere Telefoniebenutzer, die für Direct Routing aktiviert werden, portierte Contoso die Nummern vom TDM-Trunk zum SIP-Trunk für den SBC, da der SBC für Direct Routing zertifiziert ist. 

- Um eine Teilmenge der Benutzer zu unterstützen, die zu Telefonsystem wechseln, und um das fortgesetzte Routing über das Legacysystem zu ermöglichen, wurde das ältere Telefoniesystem als nächster Hop zum SBC eingerichtet.   

- Um Änderungen am Benutzerverhalten zu fördern und die Abhängigkeit von standortübergreifenden Durchwahlnummern zu entfernen, hat Contoso außerdem Anleitungen zur Verwendung Teams für alle internen Anrufe bereitgestellt.  

Die folgenden Diagramme zeigen die ursprüngliche Skype for Business Enterprise-VoIP- und Legacybereitstellung des Telefoniesystems und die Migration zu einer gemischten Bereitstellung mit Direct Routing:

**Ursprüngliche gemischte Bereitstellung**
![ Diagramm 1 mit dem Zustand "Vorher".](media/voice-case-study-4.png)

**Gemischte Bereitstellung mit Direct Routing**
![ Diagramm 2 mit dem Zustand "Vorher".](media/voice-case-study-4a.png)


## <a name="calling-plans"></a>Anrufpläne

Um die Konfigurationsanforderungen für Anrufpläne zu ermitteln, überprüfte Contoso die [wichtigsten Bereitstellungsentscheidungen des Anrufplans](calling-plan-landing-page.md#core-deployment-decisions). Die daraus resultierenden Entscheidungen wurden getroffen: 

- Q. Benötigen meine Benutzer auslandsanrufe?<br> Eine. Ja 

- Q. Haben meine Benutzer jeweils eine direkt nach innen gerichtete DID-Telefonnummer?<br> A. Heute nicht. Alle aktivierten Benutzer erhalten eine DID.-Funktion. 

- Q. Möchte ich die Anrufer-ID maskieren oder deaktivieren?<br> Eine. Die Anrufer-ID für einen Benutzer wird mit der lokalen Nummer für Contoso maskiert. 


## <a name="direct-routing"></a>Direct Routing

Contoso besuchte Ignite, um über Office 365 Features auf dem Laufenden zu bleiben, einschließlich derjenigen, die mit Telefon System und Direct Routing verfügbar sind. Technische Führung und Architekten nutzten die Während der Ignite 2019 bereitgestellte Anleitung, um ihre Richtung zu bestimmen.  Wichtige Sitzungen, die verwendet wurden: 

- [Planen des Erfolgs mit Microsoft Teams Direct Routing](https://docs.shanehoey.com/videos/ignite/ignite19-planfor%20successwithteamsdirectrouting/)

- [Updates für Direct Routing](https://docs.shanehoey.com/videos/ignite/ignite19-planfor%20successwithteamsdirectrouting/)


## <a name="configuration"></a>Konfiguration

### <a name="calling-plans-sites"></a>Anrufpläne-Websites

Um Lizenzen zu erhalten und Benutzern Telefonnummern zuzuweisen, hat Contoso die Schritte unter ["Anrufpläne einrichten](set-up-calling-plans.md)" ausgeführt. 

Aufgrund der Anzahl der Benutzer, denen Telefonnummern zugewiesen werden mussten, entschied sich Contoso für die Verwendung von PowerShell zum Zuweisen der Telefonnummern. Um zu erfahren, wie Sie mithilfe von PowerShell&mdash;zusätzlich zu anderen Einstellungen&mdash;Zahlen zuweisen, hat Contoso die [Teams PowerShell-Übersicht](teams-powershell-overview.md) verwendet.  

### <a name="direct-routing-sites"></a>Direct Routing-Websites

Um die lokale Telefonieinfrastruktur von Contoso mit Microsoft Teams zu verbinden, hat der Contoso-Administrator die Schritte unter [Konfigurieren von Direct Routing](direct-routing-configure.md) ausgeführt und das Video [direct routing in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) als Anleitung überprüft.  Contoso hat auch auf die Bereitstellungsdokumentation für direct routing durch den zertifizierten SBC-Anbieter verwiesen. 

Nachdem Direct Routing zwischen dem SBC und Microsoft-Telefon System konfiguriert wurde, musste Contoso die Konfiguration testen. Zu diesem Zweck verwendeten Contoso-Administratoren den SIP-Tester-Client, der in der ["Updates für Direct Routing-Sitzung bei Ignite 2019](https://techcommunity.microsoft.com/t5/microsoft-teams-events-blog/ignite-live-blog-session-vce20-updates-for-direct-routing/ba-p/1025138)" erläutert wurde. Das Sip Tester-Clientskript und die Dokumentation wurden aus dem PowerShell-Skript heruntergeladen, um Direct Routing Session Border Controller-Verbindungen zu testen.   


### <a name="local-media-optimization"></a>Lokale Medienoptimierung

Contoso sah die Möglichkeit, die lokale Medienoptimierung in den verschiedenen Regionen auf der ganzen Welt zu nutzen. Die unterstützten Szenarien für Contoso werden in der [lokalen Medienoptimierung für Direct Routing](direct-routing-media-optimization.md) beschrieben. Die Konfiguration der lokalen Medienoptimierung wurde durch die Anleitung des SBC-Anbieters und von Microsoft abgeschlossen. Die Konfigurationsschritte für die lokale Medienoptimierung umfassen: 

- Konfigurieren der Benutzer- und SBC-Websites 

- Konfigurieren Sie den SBC gemäß der Spezifikation des SBC-Anbieters, 

- Hinzufügen externer vertrauenswürdiger IP-Adressen zu jeder Website, die für die lokale Medienoptimierung verwendet wird    

- Definieren der Netzwerktopologie 

- Definieren der Topologie des virtuellen Netzwerks 

- Bestimmen des Modus: Immer umgehen oder nur für lokale Benutzer 

## <a name="networking-considerations"></a>Überlegungen zum Netzwerk

Contoso hatte eine Reihe von Benutzern, die für einen längeren Zeitraum remote arbeiten mussten, nachdem sie für Telefonsystem aktiviert waren. Die Benutzer haben VPN verwendet, um auf bestimmte Branchenanwendungen zuzugreifen. Während der Vpn-Nutzung haben die Telefonsystem Benutzer eine Verschlechterung der Anrufqualität erlebt. 

Um das Qualitätsproblem zu beheben, implementierte Contoso vpn-geteiltes Tunneling, das es dem Office 365 Datenverkehr ermöglichte, das Internet zu durchlaufen, während die Verbindung zu den internen Apps über das VPN blieb. Zur Implementierung des geteilten VPN-Tunnels befolgte Contoso die Anleitung [bei der Implementierung des geteilten VPN-Tunnels für Office 365](/office365/enterprise/office-365-vpn-implement-split-tunnel).  

