---
title: Cloud-Video-Interoperabilität für Microsoft Teams
author: lolaj
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: srividhc
description: Cloud-Video-Interop können Drittanbieter-meeting Raum Geräte für die Microsoft-Teams, Besprechungen teilnehmen.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d18879bdc983ea245c491f4cfadb38c2e7bd5578
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "30569295"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Cloud-Video-Interoperabilität für Microsoft Teams

Cloud Video Interop (CVI) ist eine Microsoft Qualified Drittanbieter-Lösung, die von Drittanbietern Besprechungsräumen (teleanwesenheits-) und persönliche Videogeräte (VTCs) an Microsoft-Teams, Besprechungen teilnehmen kann.
 
Mit Microsoft-Teams erhalten Sie rich Content Onlinezusammenarbeit in Besprechungen, die Freigabe von audio und video sowie Inhalte enthalten. Dies kann gefallen hat sowohl über den Desktop und Web-Client als auch über viele Partner-Geräte, die Microsoft-Teams systemintern zu integrieren. Viele Kunden haben jedoch bereits investiert in Videokonferenzen und persönliche Videokommunikation Geräten, die upgrade kostspielig sein kann. Cloud-Video-Interop bietet eine einfache Lösung, sodass Sie Ihrer vorhandenen Lösungen weiterhin zu verwenden, bis Sie aktualisieren möchten.

Mit Cloud Video Interop bietet Microsoft-Teams, eine systemeigene besprechungsumgebung für alle Teilnehmer – in Besprechungsräumen oder innerhalb eines Teams Clients.

### <a name="is-cloud-video-interop-for-me"></a>Ist Cloud-Video-Interop für mich?

Cloud-Video-Interop bietet einen intermediate während Sie in eine vollständige systemeigene Microsoft Teams Lösung Übergang von Teams Endpunkte. Das Diensttyp sollte Ihre Migrationspfad angehören.

Cloud-Video-Interop ist für Kunden vorgesehen, die die folgenden Kriterien erfüllen:

- Eine große Bereitstellung von meeting Room Geräte und persönliche Videogeräte Bereitstellung (50 +-Geräte), die nicht für die direkte Integration mit Microsoft-Teams qualifiziert sind
- Von einem unserer Partner Cloud Video Interop unterstützt werden
- Den Wert der Investitionen in die aktuellen beibehalten möchten meeting Room Geräte und persönliche Videogeräte während der Migrations zu einer einheitlichen Lösung Microsoft-Teams

Cloud-Video-Interop bietet eine großartige Lösung intermediate empfehlen wir unsere Kunden in unseren systemeigenen Teams Besprechung-Lösungen, beispielsweise Teams Raum Betriebssysteme langfristig gesucht. 

### <a name="partners-certified-for-microsoft-teams"></a>Für Teams Microsoft Certified Partner

Die folgenden Partner haben video Interop-Lösungen für Microsoft-Teams. Ihr Unternehmen können mit einer beliebigen Kombination dieser Partner innerhalb des Unternehmens arbeiten. 

|Partner|Partner-Lösung|
|----|---|
|![Polycom RealConnect](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Polycom RealConnect Service</a> |
|![Pexip unendlich](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Pexip unendlich für Microsoft-Teams</a> | 
|![BlueJeans-Gateway](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">BlueJeans-Gateway für Microsoft-Teams</a> |

### <a name="cloud-video-interop-overview"></a>Übersicht über die Cloud-Video-Interop

Cloud-Video-Interop ist ein Drittanbieter-Dienst, der von unseren Partnern, die Interoperabilität zwischen vorhandenen Videokonferenzen und persönliche Videogerät Lösungen zu vor Ort und Microsoft-Teams bieten angeboten wird.

Die Lösungen, die von unseren Partnern angeboten bestehen aus Komponenten, die bereitgestellt werden können vollständig Cloud auf der Basis oder teilweise/vollständig lokal. 
     
Das folgende Diagramm zeigt die allgemeine Architektur des unsere Partner Solutions.

![Teams Cloud Video Interop Partner-Lösung](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>Bereitstellen von Cloud-Video-Interop

Wenn Sie eine Cloud-Video-Interop-Lösung bereitstellen, ist es wichtig zu verstehen, dass Sie eine Partner-Projektmappe bereitstellen. Im folgenden Diagramm sind die allgemeinen Schritte, die Sie, zum Bereitstellen von Cloud-Video-Interop ergreifen sollten aufgeführt.

![CVI in Ihrer Organisation bereitstellen.](media/deploying-cvi.png)

### <a name="plan"></a>Plan

In der Planungsphase sollten Sie die Geräte identifizieren, den Sie nicht mit einem systemeigenen Teams Gerät ersetzen, und finden Sie einen Cloud Video Interop Partner, der diese Geräte unterstützen kann.  

Es ist außerdem wichtig zu verstehen, dass Sie eine Lizenz für jeden Benutzer, die Besprechungstermine wird in dem ein Cloud-Video-Interop-aktivierten Gerät benötigen beitreten soll. Beachten Sie, dass die genauen lizenzierungsanforderungen aus der Cloud Video Interop Partner abgerufen werden können. Stellen Sie sicher, dass dies deaktiviert ist, bevor Sie mit die Bereitstellung beginnen.

### <a name="configure"></a>Konfigurieren

Der Partner, den Sie für Ihre Bereitstellung CVI ausgewählt haben, werden Ihnen mit einem vollständigen Bereitstellung Dokument bereitgestellt, der alle erforderlichen Schritte zum erfolgreichen Bereitstellung innerhalb Ihrer Organisation besteht. Dazu gehören Firewall-Ports und IP-Adressbereichen, Änderungen bei der Konfiguration für die Geräte und andere Einstellungen, die ändern müssen.

### <a name="provision"></a>Bereitstellung  

Während der Phase der Bereitstellung weisen Lizenzen an die entsprechenden Benutzer gemäß den Partner Konfigurationshandbuch Sie. Sie müssen auch über den Prozess Azure stimmen den Partner Zugriff auf Ihre Umgebung Teams ermöglicht geleitet. Weitere Informationen über den Vorgang des Azure stimmen finden Sie hier:https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-permissions-and-consent 

### <a name="schedule"></a>Zeitplan

Nachdem ein Benutzer für die Cloud Video Interop aktiviert ist, müssen jede Besprechung geplant mit entweder die Teams-Add-in für Outlook oder Teams Client die entsprechende zusätzliche Informationen, die automatisch in die Besprechung so Teams hinzugefügt, Cloud-Video Interop-kompatible Geräte können an diesen Besprechungen teilnehmen.

### <a name="join"></a>Join

Je nach der Lösung Partner haben verschiedene Möglichkeiten zur Teilnahme an einer Besprechung Cloud-Video-Interop-aktiviert. Eine exakte Teilnahme an einer Besprechung, die von Ihrem Partner Cloud Video Interop Szenarien bereitgestellt werden. Wir haben die Beispiele unten aufgeführt:

- IVR (Interactive Voice Response, IVR) 
  - Sie können mithilfe der tenantkey@domain des Partners IVR im einwählen.
  - Wenn Sie in den IVR-Partner sind, werden Sie aufgefordert, zur Eingabe der ConferenceId VTC dann Sie die Besprechung Teams eine Verbindung herstellt.
- Durchwahl 
  - Sie können direkt in die Teams Besprechung einwählen ohne Interaktion mit der Partner IVR mithilfe des Features Durchwahl unter Verwendung der vollständigen Zeichenfolge des Tenantkey. VTC ConferenceId@domain.
- One Touch-Wählplan 
  - Wenn Sie eine integrierte Teams Platz haben, können Sie einem Tastendruck Dial Funktionen von Ihrem Partner (ohne Geben Sie eine beliebige Zeichenfolge Dial) verwenden.

## <a name="manage-cloud-video-interop"></a>Verwalten von Cloud-Video-Interop

Nach dem Cloud-Video-Interop bereitgestellt wird, können Sie die Geräte, die von unseren Partnern bereitgestellte Lösungen mit verwalten. Jeder Partner wird eine administrative Schnittstelle bereitgestellt, die Lizenz und Gerät Management enthalten sein sollen. 

Reporting ist auch direkt über die Verwaltungsschnittstelle Partner verfügbar. Weitere Informationen auf Berichtsfunktionen wenden Sie sich an den Partner Ihrer Wahl. 

### <a name="troubleshooting-cloud-video-interop"></a>Problembehandlung bei Video Cloud-Interop

Cloud-Video-Interop ist ein Partner-Dienst. Wenn Sie Probleme haben, ist der erste Schritt verbinden ein Gerät, das der Teams-Client installiert ist, und verbinden Sie ihn mit der gleichen Segment als Cloud-Video-Interop-Gerät, das Probleme verursacht. 

Wenn Teams Funktionen ordnungsgemäß auf dieses Segment, und Sie auch alle Netzwerke und Konfigurationsrichtlinien durchgeführt haben, den, die der Partner bereitgestellt hat, müssen Sie den Partner fordern Sie eine zusätzliche Problembehandlung. 

## <a name="powershell-for-cloud-video-interop"></a>PowerShell für Cloud-Video-Interop

Die folgenden PowerShell-Cmdlets stehen Ihnen die Cloud Video Interop-Bereitstellung (teilweise) zu automatisieren.

- **Get-CsTeamsVideoInteropServicepolicy**: Microsoft bietet vorab erstellte Richtlinien für die einzelnen unserer unterstützte Partner, mit denen Sie festlegen, welche Partner für Cloud-Video-Interop verwenden können.<br>Mit diesem Cmdlet können Sie die Überprüfung vor dem erstellten Richtlinien zu identifizieren, die Sie in Ihrer Organisation verwenden können. Sie können eine oder mehrere Ihrer Benutzer durch das Cmdlet Grant-CsTeamsVideoInteropServicePolicy Nutzung dieser Richtlinie zuweisen.
- **Grant-CsTeamsVideoInteropServicePolicy**: mit diesem Cmdlet können Sie eine bereits erstellte Richtlinie für die Verwendung in Ihrer Organisation zuweisen oder weisen die Richtlinie auf bestimmte Benutzer.
- **New-CsVideoInteropServiceProvider**: Verwenden Sie dieses Cmdlet Informationen zu unterstützten CVI Partner angeben, die Ihre Organisation verwenden möchten.
- **Set-CsVideoInteropServiceProvider**: Verwenden Sie dieses Cmdlet, um Informationen zu unterstützten CVI Partner zu aktualisieren, die Ihre Organisation verwendet.
- **Get-CsVideoInteropServiceProvider**: Verwenden Sie dieses Cmdlet, um alle Anbieter, die konfiguriert wurden für die Verwendung innerhalb der Organisation abzurufen.
- **Remove-CsVideoInteropServiceProvider**: Verwenden Sie dieses Cmdlet, um alle für Anbieterinformationen zu einem Anbieter zu entfernen, die Ihre Organisation nicht mehr verwendet.
