---
title: Cloud-Video-Interoperabilität für Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: naforer
f1.keywords:
- NOCSH
description: Verwenden Sie Cloud Video Interop als Zwischenlösung, um Besprechungsraumgeräten von Drittanbietern die Teilnahme an Besprechungen Microsoft Teams erlauben.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 39452a659f1a95d66aeac4a18a4d7801764437ae
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618641"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Cloud-Video-Interoperabilität für Microsoft Teams

Cloud Video Interop (CVI) ist eine von Microsoft qualifizierte Drittanbieterlösung, mit der Besprechungsräume von Drittanbietern (Telepresence) und persönliche Videogeräte (Personal Video Devices, VTCs) an Besprechungen Microsoft Teams können.
 
Dank Microsoft Teams können Sie in Besprechungen, die Audio, Video und Inhaltsfreigabe umfassen, umfangreiche Onlineinhalte zusammenarbeiten. Dies kann über den Desktop und den Webclient sowie über viele Partnergeräte, die nativ in die App integriert Microsoft Teams. Viele Kunden haben jedoch bereits in Videokonferenz- und persönliche Videokommunikationsgeräte investiert, was für ein Upgrade aufwendig sein kann. Cloud Video Interop bietet eine einfache Lösung, die es Ihnen ermöglicht, Ihre vorhandenen Lösungen weiter zu verwenden, bis Sie bereit für ein Upgrade sind.

Mit Cloud Video Interop bietet Microsoft Teams eine systemeigene Besprechungserfahrung für alle Teilnehmer – in Besprechungsräumen oder innerhalb Teams Clients.

### <a name="is-cloud-video-interop-for-me"></a>Ist Cloud Video Interop für mich?

Cloud Video Interop stellt einen Zwischendienst zur Verfügung, während Sie zu einer vollständigen systemeigenen Microsoft Teams über Teams-Endpunkte umstiegen. Der bereitgestellte Dienst sollte Teil Ihres Migrationspfads sein.

Cloud Video Interop ist für Kunden vorgesehen, die die folgenden Kriterien erfüllen:

- Eine große Bereitstellung von Besprechungsraumgeräten und Bereitstellung von persönlichen Videogeräten (mehr als 50 Geräte), die nicht für die direkte Integration in Besprechungsgeräte qualifiziert Microsoft Teams
- Werden von einem unserer Cloud Video Interop-Partner unterstützt
- Sie möchten den Wert ihrer Investition in ihre aktuellen Besprechungsraumgeräte und persönlichen Videogeräte während der Migration zu einer nativen Besprechungslösung Microsoft Teams beibehalten

Während Cloud Video Interop eine hervorragende Zwischenlösung bietet, empfehlen wir unseren Kunden, sich langfristig mit unseren nativen Teams Meeting-Lösungen wie Teams Room Systems zu unterhalten. 

### <a name="office-365-us-government-and-third-party-services"></a>Office 365 US Government and third-party services

Office 365 bietet die Möglichkeit, Anwendungen von Drittanbietern in SharePoint Online-Websites, Skype for Business-, Teams- und Office-Anwendungen zu integrieren, die in Microsoft 365 Apps for Enterprise enthalten sind (z. B. Word, Excel, PowerPoint und Outlook) und Outlook Web App. Darüber hinaus Office 365 die Integration in Drittanbieter-Dienstanbieter unterstützt. Diese Anwendungen und Dienste von Drittanbietern beinhalten möglicherweise das Speichern, Übertragen und Verarbeiten von Kundendaten Ihrer Organisation auf Drittanbietersystemen, die außerhalb der Office 365-Infrastruktur liegen und daher nicht von den Office 365-Compliance- und Datenschutzverpflichtungen abgedeckt sind. **Es wird empfohlen, die Datenschutz- und Compliancebestimmungen zu lesen, die von Dritten bei der Bewertung der geeigneten Nutzung dieser Dienste für Ihre Organisation bereitgestellt werden.**



### <a name="partners-certified-for-microsoft-teams"></a>Für Microsoft Teams

Die folgenden Partner verfügen über Lösungen für die Video-Inaktivität Microsoft Teams. Ihr Unternehmen kann sich für eine Zusammenarbeit mit einer beliebigen Kombination dieser Partner innerhalb Ihres Unternehmens entscheiden. 

|Partner|Partnerlösung|
|----|---|
|![Das Logo von Poly RealConnect](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Poly RealConnect Service</a> |
|![Das Logo, das Pexip Unendlichkeit darstellt](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Unendlichkeit in Pexip für Microsoft Teams</a> | 
|![Das Logo von BlueJeans Gateway](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">BlueJeans Gateway für Microsoft Teams</a> |
|![Das Logo für Cisco CVI](media/cisco.png)|<a href="https://aka.ms/CiscoCVI" target="_blank">Cisco Webex Video Integration für Microsoft Teams</a>|

### <a name="cloud-video-interop-overview"></a>Übersicht über Cloud Video Interop

Cloud Video Interop ist ein Drittanbieterdienst, der von unseren Partnern angeboten wird, um eine Interoperabilität zwischen vorhandenen Videokonferenz- und persönlichen Videogerätelösungen lokal zu Microsoft Teams.

Die von unseren Partnern angebotenen Lösungen bestehen aus Komponenten, die entweder vollständig cloudbasierte oder teilweise/vollständig lokal bereitgestellt werden können. 
     
Das folgende Diagramm zeigt die Architektur auf hoher Ebene unserer Partnerlösungen.

![Diagram describing a Teams Cloud Video Interop partner solution](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>Bereitstellen von Cloud Video Interop

Bei der Bereitstellung einer Cloud Video Interop-Lösung ist es wichtig zu verstehen, dass Sie eine Partnerlösung bereitstellen. Die allgemeinen Schritte zum Bereitstellen von Cloud Video Interop sind im folgenden Diagramm aufgeführt.

![Diagramm zur Beschreibung der Bereitstellung von CVI in Ihrer Organisation](media/deploying-cvi.png)

### <a name="plan"></a>Plan

Während der Planungsphase sollten Sie die Geräte identifizieren, die Sie nicht durch ein systemeigenes Teams-Gerät ersetzen, und einen Cloud Video Interop-Partner suchen, der diese Geräte unterstützen kann.  

Außerdem ist es wichtig zu verstehen, dass Sie eine Lizenz für jeden Benutzer benötigen, der Besprechungen plant, an denen ein Cloud Video Interop-fähiges Gerät teilnehmen soll. Beachten Sie, dass die genauen Lizenzierungsanforderungen beim Cloud Video Interop-Partner eingeholt werden können. Stellen Sie sicher, dass dies eindeutig ist, bevor Sie mit der Bereitstellung beginnen.

### <a name="configure"></a>Konfigurieren

Der Partner, den Sie für Ihre CVI-Bereitstellung ausgewählt haben, stellt Ihnen ein vollständiges Bereitstellungsdokument zur Verfügung, das alle erforderlichen Schritte für eine erfolgreiche Bereitstellung in Ihrer Organisation enthält. Dazu gehören Firewallports und IP-Bereiche, Konfigurationsänderungen für Ihre Geräte und weitere Einstellungen, die geändert werden müssen.

### <a name="provision"></a>Bereitstellung  

Während der Bereitstellungsphase weisen Sie den entsprechenden Benutzern lizenzen entsprechend dem Konfigurationshandbuch für Partner zu. Sie müssen auch den Azure-Zustimmungsprozess durchgehen, um dem Partner Zugriff auf Ihre Teams zu ermöglichen. Weitere [Informationen zum Azure-Zustimmungsprozess](/azure/active-directory/develop/v2-permissions-and-consent) finden Sie unter Microsoft Identity Platform und Zustimmung des Azure-Endpunkts.

### <a name="schedule"></a>Zeitplan

Nachdem ein Benutzer für Cloud Video Interop aktiviert wurde, werden jeder Besprechung, die mit dem Teams-Besprechungs-Add-In für Outlook oder dem Teams-Client geplant wird, die entsprechenden zusätzlichen Informationen automatisch zur Teams-Besprechung hinzugefügt, damit mit Cloud Video Interop kompatible Geräte an diesen Besprechungen teilnehmen können.

### <a name="join"></a>Join

Je nach Partnerlösung gibt es mehrere Möglichkeiten, an einer Besprechung mit Aktivierter Cloud Video Interop-Besprechung teilnehmen. Genaue Szenarien für die Teilnahme an Besprechungen werden von Ihrem Cloud Video Interop-Partner bereitgestellt. Nachfolgend sind einige Beispiele aufgeführt:

- IVR (Interactive Voice Response, interaktive Sprachantwort) 
  - Sie können sich über die -Wählscheibe bei der IVR des Partners tenantkey@domain.
  - Wenn Sie sich im Partner IVR befinden, werden Sie aufgefordert, die VTC-Konferenz-ID ein betreten, wodurch Sie dann mit der Besprechung Teams werden.
- Direktwahl 
  - Sie können sich direkt in die Teams-Besprechung einwählen, ohne mit dem IVR des Partners zu interagieren, indem Sie die vollständige Zeichenfolge des Mandantenschlüssels verwenden. VTC ConferenceId@domain.
- One-Touch Dial 
  - Wenn Sie über einen integrierten Teams verfügen, können Sie die von Ihrem Partner gebotenen Ein-Finger-Wählfunktionen verwenden (ohne eine Wählzeichenfolge eingeben zu müssen).

## <a name="manage-cloud-video-interop"></a>Verwalten von Cloud Video Interop

Nachdem Cloud Video Interop bereitgestellt wurde, können Sie die Geräte mit den Lösungen unserer Partner verwalten. Jeder Partner stellt Ihnen eine Verwaltungsschnittstelle zur Verfügung, die sowohl die Lizenz- als auch die Geräteverwaltung umfasst. 

Die Berichterstellung ist auch direkt über die administrative Oberfläche des Partners verfügbar. Weitere Informationen zu Berichtsfunktionen erhalten Sie beim Partner Ihrer Wahl. 

### <a name="troubleshooting-cloud-video-interop"></a>Problembehandlung bei Cloud Video Interop

Cloud Video Interop ist ein vom Partner bereitgestellter Dienst. Wenn Probleme auftreten, besteht der erste Schritt im Anschließen eines Geräts, auf dem der Teams-Client installiert ist, und demselben Segment wie das Cloud Video Interop-Gerät, das die Probleme verursacht. 

Wenn Teams in diesem Segment ordnungsgemäß funktioniert und Sie auch alle vom Partner bereitgestellten Netzwerk- und Konfigurationsrichtlinien befolgt haben, müssen Sie sich an den Partner wenden, um weitere Problembehandlungen zu erhalten. 

## <a name="powershell-for-cloud-video-interop"></a>PowerShell für Cloud Video Interop

Die folgenden PowerShell-Cmdlets stehen Ihnen zum (teilweisen) Automatisieren der Bereitstellung von Cloud Video Interop zur Verfügung.

- **Get-CsTeamsVideoInteropServicepolicy:** Microsoft stellt vorgefertigte Richtlinien für jeden unserer unterstützten Partner zur Verfügung, mit denen Sie festlegen können, welche Partner für Cloud Video Interop verwendet werden sollen.<br>Mit diesem Cmdlet können Sie die vorgefertigten Richtlinien identifizieren, die Sie in Ihrer Organisation verwenden können. Sie können diese Richtlinie einem oder mehreren Benutzern zuweisen, indem Sie das Grant-CsTeamsVideoInteropServicePolicy nutzen.
- **Grant-CsTeamsVideoInteropServicePolicy:** Mit diesem Cmdlet können Sie eine vordefinierte Richtlinie für die Verwendung in Ihrer Organisation zuweisen oder die Richtlinie bestimmten Benutzern zuweisen.
- **New-CsVideoInteropServiceProvider:** Verwenden Sie dieses Cmdlet, um Informationen zu einem unterstützten CVI-Partner anzugeben, den Ihre Organisation verwenden möchte.
- **Set-CsVideoInteropServiceProvider:** Verwenden Sie dieses Cmdlet, um Informationen zu einem unterstützten CVI-Partner zu aktualisieren, den Ihre Organisation verwendet.
- **Get-CsVideoInteropServiceProvider:** Verwenden Sie dieses Cmdlet, um alle Anbieter zu erhalten, die für die Verwendung innerhalb der Organisation konfiguriert wurden.
- **Remove-CsVideoInteropServiceProvider:** Verwenden Sie dieses Cmdlet, um alle Anbieterinformationen zu einem Anbieter zu entfernen, den Ihre Organisation nicht mehr verwendet.