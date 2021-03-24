---
title: Fallstudie "Teams voice Contoso"
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
description: Sprachfallstudie zu Teams für multinationale Unternehmen
appliesto:
- Microsoft Teams
ms.openlocfilehash: 995b4ddf9c07dea57c8d4de9940776d5137c2d02
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101031"
---
# <a name="contoso-case-study-phone-system"></a>Contoso-Fallstudie: Telefonsystem

Je nach geografischem Standort und anderen Faktoren hatte Contoso Niederlassungen mit den folgenden Telefonielösungen:

- Websitetyp A: Skype for Business Enterprise-VoIP

- Websitetyp B: Herkömmliche ältere Telefoniesysteme

- Websitetyp C: Eine Kombination aus Skype for Business Enterprise-VoIP herkömmlichen älteren Telefoniesystemen


Um eine Microsoft Phone System-Lösung für die gesamte Organisation zu implementieren, musste Contoso für jeden Websitetyp ermitteln, welche der folgenden Optionen mit Telefonsystem verwendet werden würde, um eine Verbindung mit dem öffentlichen Telefonnetz &mdash; &mdash; (PstN) herzustellen:

- Telefonsystem mit Anrufplan 

- Telefonsystem mit eigenem PSTN-Netzbetreiber über Direct Routing 

- Kombination aus Telefonsystem mit Anrufplan und Telefonsystem mit eigenem PSTN-Netzbetreiber durch Direktes Routing
 
Um die richtige Lösung für ihre [](/SkypeForBusiness/hybrid/msft-telephony-solutions) Organisation zu ermitteln, verwendet Contoso Microsoft-Telefonielösungen und die Ignite 2019-Sitzungsanrufe [in Microsoft Teams.](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions)  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a>Websitetyp A: Skype for Business Enterprise-VoIP 

Contoso Skype for Business Enterprise-VoIP als Hub eingerichtet und sprach. Es gab einen zentralen Ort, an dem das PSTN-Gateway in der Region verwaltet wurde, die die Verbindung zum PSTN für die Skype for Business-Enterprise-VoIP benutzer im Land bereitgestellt hat. Häufig hatten diese Satellitenbüros keinen eigenen Internetanschluss. Die Nummern für diese Benutzer befinden sich im SIP-Trunk, der mit einem vorhandenen SBC verbunden ist. 

Um festzustellen, ob der bereits bereitgestellte SBC für Direct Routing und Medienumgehung zertifiziert ist, hat Contoso die Liste der Sitzungsgrenzcontroller überprüft, die für [Direct Routing zertifiziert sind.](direct-routing-border-controllers.md)  

Die Wählgewohnheiten des Benutzers waren, einen Benutzer im älteren Telefoniesystem mithilfe einer Erweiterung zu wählen, auch wenn der Benutzer über einen Skype for Business-Client für Peer-zu-Peer-Audio verfügt. 

Contoso basiert auf den folgenden Fragen:

- F. Müssen wir die funktionen beibehalten, die von unserer lokalen Bereitstellung bereitgestellt werden?<br>
  A. Nein 

- F. Müssen wir mit PbX-Systemen von Drittanbietern und anderen Telefoniegeräten zusammenarbeiten?<br>
  A. Nein 

- F. Müssen wir unseren aktuellen Drittanbieter erhalten?<br> A. Ja (regulierte Länder) und Nein 

- F. Müssen wir den ROI für bereitgestellte SBCs erhalten?<br> A. Ja und Nein  

- F. Ist Microsoft PSTN-Anrufpläne in dieser Region verfügbar?<br> A. Ja und Nein 

Basierend auf den Antworten auf ihre Fragen hat Contoso entschieden:

- Verschieben Sie die Benutzer, die sich in einer Region befinden, in der PSTN-Anrufpläne für Telefonsystem mit Anrufplänen verfügbar sind. 

- Verschieben Sie die Benutzer, die sich nicht in einer Region befinden, in der PSTN-Anrufpläne verfügbar sind, Benutzer auf einer Website, auf der der ROI auf den SBCs noch nicht erfüllt werden muss, und Benutzer, die sich in einem Land mit Telefoniebestimmungen für Telefonsystem mit Direct Routing befanden. 

Das folgende Diagramm zeigt die erste Skype for Business Enterprise-VoIP Bereitstellung und die Migration dieser Bereitstellung zu Microsoft Calling Plans und Direct Routing:

![Diagramm mit Vor- und Nachzuständen](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a>Websitetyp B: Herkömmliche ältere Telefoniesysteme

Contoso hatte viele Niederlassungen, die ältere Telefoniesysteme nutzten. Es gab eine Teilmenge von Benutzern, die eine E1,64-Telefonnummer hatten, während andere nur eine Erweiterung hatten. Diese Nummern befinden sich im TDM-Trunk zum PSTN-Gateway. Die standortinterne Wählung wurde konfiguriert, indem ein Websitecode vor der Erweiterung verwendet wurde, um zu ermitteln, wohin der Anruf weiterleite. Die Wählgewohnheiten der Benutzer waren die Durchwahl.   

Contoso basiert auf den folgenden Fragen:

- F. Müssen wir die funktionen beibehalten, die von unserer lokalen Bereitstellung bereitgestellt werden?<br>
  A. Nein 

- F. Müssen wir mit PbX-Systemen von Drittanbietern und anderen Telefoniegeräten zusammenarbeiten?<br> A. Ja

- F. Müssen wir unseren aktuellen Drittanbieter erhalten?<br> A. Nein 

- F. Ist der Anrufplan von Microsoft PSTN in unserer Region verfügbar?<br> A. Ja und Nein 

Basierend auf den Antworten auf ihre Fragen hat Contoso entschieden: 

- Verschieben Sie die Benutzer, die sich in einer Region befinden, in der PSTN-Anrufpläne für Telefonsystem mit Anrufplänen verfügbar sind. 

- Verschieben Sie die Benutzer, die sich nicht in einer Region befinden, in der PSTN-Anrufpläne für Telefonsystem mit Direct Routing verfügbar sind. 

- Verwalten Sie eine PSTN-Verbindung mit geschäftskritischen analogen Geräten.

Die folgenden Diagramme zeigen die ursprüngliche Legacysystembereitstellung mit Remotewebsites und die Migration zu einer Direct Routing-Bereitstellung mit Optimierung lokaler Medien:

**Ursprüngliche Legacybereitstellung**  
 ![ Diagramm mit Vor- und Nachzuständen](media/voice-case-study-2.png)


**Bereitstellung mit Direct Routing**

![Diagramm mit Vor- und Nachzuständen](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a>Websitetyp C: Kombination aus Skype for Business Enterprise-VoIP herkömmlichen älteren Telefoniesystemen

Contoso Skype for Business Enterprise-VoIP benutzernummern befinden sich im SIP-Trunk zum SBC vom Netzbetreiber. Die Nummern für die herkömmlichen Telefoniesysteme befinden sich im TDM-Trunk zum PSTN-Gateway.   

Contoso basiert auf den folgenden Fragen:

- F. Müssen wir die funktionen beibehalten, die von unserer lokalen Bereitstellung bereitgestellt werden?<br>
  A. Nein 

- F. Müssen wir mit PbX-Systemen von Drittanbietern und anderen Telefoniegeräten zusammenarbeiten?<br> A. Nein 

- F. Müssen wir unseren aktuellen Drittanbieter erhalten?<br> A. Nein 

- F. Müssen wir den ROI für bereitgestellte SBCs erhalten?<br> A. Ja und Nein  

- F. Ist der PstN-Anrufplan von Microsoft in dieser Region verfügbar?<br> A. Nein 

Basierend auf den Antworten auf ihre Fragen hat Contoso folgendes entschieden: 

- Für die älteren Telefoniebenutzer, die für Direct Routing aktiviert werden, portierte Contoso die Nummern aus dem TDM-Trunk zum SIP-Trunk für den SBC, da der SBC für Direct Routing zertifiziert ist. 

- Um eine Teilmenge der Benutzer zu unterstützen, die zu Telefonsystem umsenden, und um die Fortsetzung des Routings über das ältere System zu ermöglichen, wurde das ältere Telefoniesystem als nächster Hop zum SBC eingerichtet.   

- Darüber hinaus hat Contoso Anleitungen zur Verwendung von Teams für alle internen Anrufe bereitgestellt, um die Änderung des Benutzerverhaltens zu fördern und die Abhängigkeit von zwischen- und websiteinternen Durchwahlen zu entfernen.  

Die folgenden Diagramme zeigen die ursprüngliche Bereitstellung von Skype for Business Enterprise-VoIP und älteren Telefoniesystem sowie die Migration zu einer gemischten Bereitstellung mithilfe von Direct Routing:

**Ursprüngliche gemischte Bereitstellung** 
 ![ Diagramm, das vor dem Zustand angezeigt wird](media/voice-case-study-4.png)

**Gemischte Bereitstellung mit Direct Routing** 
 ![ Diagramm, das vor dem Zustand angezeigt wird](media/voice-case-study-4a.png)


## <a name="calling-plans"></a>Anrufpläne

Um die Konfigurationsanforderungen für Anrufpläne zu ermitteln, hat Contoso die Grundlegenden Bereitstellungsentscheidungen für den [Anrufplan überprüft.](calling-plan-landing-page.md#core-deployment-decisions) Die daraus resultierenden Entscheidungen wurden getroffen: 

- F. Benötigen meine Benutzer Auslandsrufe?<br> A. Ja 

- F. Verfügen meine Benutzer jeweils über eine direkte nach innen gerichtete DID-Telefonnummer?<br> A. Heute nicht. Alle aktivierten Benutzer erhalten eine DID. 

- F. Möchte ich die Anrufer-ID maskieren oder deaktivieren?<br> A. Die Anrufer-ID für einen Benutzer wird in der lokalen Rufnummer für Contoso maskiert. 


## <a name="direct-routing"></a>Direktes Routing

Contoso besuchte Ignite, um über Office 365-Features auf dem laufenden zu bleiben, einschließlich der features, die mit Telefonsystem und Direct Routing verfügbar sind. Die technische Führung und Architekten haben die während der Ignite 2019 bereitgestellten Anleitungen verwendet, um ihre Richtung zu bestimmen.  Verwendete Schlüsselsitzungen: 

- [Planen des Erfolgs mit Microsoft Teams Direct Routing](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [Updates für Direct Routing](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a>Konfiguration

### <a name="calling-plans-sites"></a>Aufrufen von Planwebsites

Um Lizenzen zu erhalten und Benutzern Telefonnummern zuzuordnen, hat Contoso die Schritte unter [Einrichten von Anrufplänen befolgt.](set-up-calling-plans.md) 

Aufgrund der Anzahl der Benutzer, denen Telefonnummern zugewiesen werden mussten, entschloss sich Contoso, PowerShell zum Zuweisen der Telefonnummern zu verwenden. Um zu erfahren, wie Zahlen mithilfe von PowerShell zusätzlich zu anderen Einstellungen zugewiesen werden, verwendet &mdash; Contoso die Übersicht über Teams &mdash; [PowerShell.](teams-powershell-overview.md)  

### <a name="direct-routing-sites"></a>Direct Routing-Websites

Um die lokale Telefonieinfrastruktur von Contoso mit Microsoft Teams zu verbinden, hat der Administrator von Contoso die Schritte unter [Konfigurieren](direct-routing-configure.md) des direkten Routings befolgt und das Video [Direct Routing in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) zur Anleitung überprüft.  Contoso hat sich auch auf die Dokumentation zur Direct-Routing-Bereitstellung durch den zertifizierten SBC-Anbieter verwiesen. 

Nach der Konfiguration von Direct Routing zwischen SBC und Microsoft Phone System musste Contoso die Konfiguration testen. Dazu verwendeten Contoso-Administratoren den SIP-Tester-Client, der in der Sitzung Updates für Direct Routing bei [Ignite 2019 besprochen wurde.](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions) Das SIP Tester-Clientskript und die Dokumentation wurden aus dem PowerShell-Skript heruntergeladen, um Die Direct Routing Session Border Controller-Verbindungen zu testen.   


### <a name="local-media-optimization"></a>Optimierung lokaler Medien

Contoso hat die Möglichkeit gesehen, die Optimierung lokaler Medien in den verschiedenen Regionen auf der ganzen Welt zu nutzen. Die unterstützten Szenarien für Contoso werden unter [Local Media Optimization for Direct Routing beschrieben.](direct-routing-media-optimization.md) Die Konfiguration der Optimierung lokaler Medien wurde durch die Anleitung des SBC-Anbieters und von Microsoft abgeschlossen. Zu den Konfigurationsschritten für die Optimierung lokaler Medien gehören: 

- Konfigurieren der Benutzer- und SBC-Websites 

- Konfigurieren Sie den SBC gemäß der SBC-Lieferantenspezifikation, 

- Hinzufügen externer vertrauenswürdiger IP-Adressen zu jeder Website, die für die Optimierung lokaler Medien verwendet wird    

- Definieren der Netzwerktopologie 

- Definieren der Topologie des virtuellen Netzwerks 

- Bestimmen des Modus: Immer umgehen oder nur für lokale Benutzer 

## <a name="networking-considerations"></a>Überlegungen zum Netzwerken

Contoso hatte eine Reihe von Benutzern, die für einen längeren Zeitraum remote arbeiten mussten, nachdem sie für das Telefonsystem aktiviert wurden. Die Benutzer verwendeten VPN, um auf bestimmte Line of Business-Anwendungen zu zugreifen. Während der Verwendung von VPN haben die Benutzer des Telefonsystems eine Verschlechterung der Anrufqualität erfahren. 

Um das Qualitätsproblem zu beheben, implementierte Contoso vpn split tunneling, wodurch der Office 365-Datenverkehr das Internet durchlaufen konnte, während die Verbindung mit den internen Apps über das VPN weiterhin besteht. Zum Implementieren des geteilten VPN-Tunnelings hat Contoso die Anleitung unter Implementieren von [geteilten VPN-Tunneln für Office 365 befolgt.](/office365/enterprise/office-365-vpn-implement-split-tunnel)  

