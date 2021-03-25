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
description: Verwenden Sie Cloud Video Interop als Zwischenlösung, um Geräten von Drittanbietern die Teilnahme an Microsoft Teams-Besprechungen zu ermöglichen.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a8d657e2cbc12695453e26ef0e4bf9ad55070bf
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122359"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Cloud-Video-Interoperabilität für Microsoft Teams

Cloud Video Interop (CVI) ist eine Microsoft-qualifizierte Drittanbieterlösung, mit der Besprechungsräume von Drittanbietern (Telepresence) und persönliche Videogeräte (VTCs) an Microsoft #A0 teilnehmen können.
 
Mit Microsoft Teams erhalten Sie umfassende Onlineinhaltszusammenarbeit in Besprechungen, die Audio, Video und Inhaltsfreigabe umfassen. Dies kann über den Desktop und den Webclient sowie über viele Partnergeräte, die nativ in Microsoft Teams integriert werden, verwendet werden. Viele Kunden haben jedoch bereits in Video-Telekonferenz- und persönliche Videokommunikationsgeräte investiert, was für ein Upgrade teuer werden kann. Cloud Video Interop stellt eine einfache Lösung bereit, mit der Sie ihre vorhandenen Lösungen weiterhin verwenden können, bis Sie zum Upgrade bereit sind.

Mit Cloud Video Interop bietet Microsoft Teams eine native Besprechungserfahrung für alle Teilnehmer – in Besprechungsräumen oder innerhalb von Teams-Clients.

### <a name="is-cloud-video-interop-for-me"></a>Ist Cloud Video Interop für mich?

Cloud Video Interop stellt einen Zwischendienst zur Verfügung, während Sie mithilfe von Teams-Endpunkten zu einer vollständig nativen Microsoft Teams-Lösung überwechseln. Der bereitgestellte Dienst sollte Teil Ihres Migrationspfads sein.

Cloud Video Interop richtet sich an Kunden, die die folgenden Kriterien erfüllen:

- Große Bereitstellung von Besprechungsraumgeräten und Bereitstellung persönlicher Videogeräte (mehr als 50 Geräte), die nicht für die direkte Integration in Microsoft Teams qualifiziert sind
- Werden von einem unserer Cloud Video Interop-Partner unterstützt
- Möchten Sie den Wert ihrer Investition auf ihren aktuellen Besprechungsraumgeräten und persönlichen Videogeräten während der Migration zu einer nativen Microsoft Teams-Lösung beibehalten

Obwohl Cloud Video Interop eine hervorragende Zwischenlösung bietet, empfehlen wir unseren Kunden, sich langfristig mit unseren systemeigenen Teams-Besprechungslösungen wie Teams Room Systems zu unterhalten. 

### <a name="office-365-us-government-and-third-party-services"></a>Office 365 US Government und Drittanbieterdienste

Office 365 bietet die Möglichkeit, Anwendungen von Drittanbietern in SharePoint Online-Websites, Skype for Business, Teams, Office-Anwendungen in Microsoft 365-Apps für Unternehmen (wie Word, Excel, PowerPoint und Outlook) und Outlook Web App zu integrieren. Darüber hinaus unterstützt Office 365 die Integration mit Drittanbieterdienstanbietern. Diese Anwendungen und Dienste von Drittanbietern umfassen möglicherweise das Speichern, Übertragen und Verarbeiten der Kundendaten Ihrer Organisation auf Systemen von Drittanbietern, die sich außerhalb der Office 365-Infrastruktur befinden und daher nicht von den Office 365-Compliance- und Datenschutzverpflichtungen abgedeckt sind. **Es wird empfohlen, die Datenschutz- und Compliancebestimmungen, die von Dritten bereitgestellt werden, zu überprüfen, wenn Sie die geeignete Nutzung dieser Dienste für Ihre Organisation bewerten.**



### <a name="partners-certified-for-microsoft-teams"></a>Für Microsoft Teams zertifizierte Partner

Die folgenden Partner verfügen über Video-In-Interop-Lösungen für Microsoft Teams. Ihr Unternehmen kann sich entscheiden, mit einer beliebigen Kombination dieser Partner in Ihrem Unternehmen zusammen zu arbeiten. 

|Partner|Partnerlösung|
|----|---|
|![Das Logo von Poly RealConnect](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Poly RealConnect Service</a> |
|![Das Logo für Pexip Infinity](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Pexip Infinity für Microsoft Teams</a> | 
|![Das Logo für das BlueJeans Gateway](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">BlueJeans Gateway für Microsoft Teams</a> |
|![Das Logo, das Cisco CVI darstellt](media/cisco.png)|<a href="https://aka.ms/CiscoCVI" target="_blank">Cisco Webex Video Integration für Microsoft Teams</a>|

### <a name="cloud-video-interop-overview"></a>Übersicht über Cloud Video Interop

Cloud Video Interop ist ein Drittanbieterdienst, der von unseren Partnern angeboten wird, um die Interoperabilität zwischen vorhandenen Videokonferenzen und lokalen Lösungen für persönliche Videogeräte und Microsoft Teams zu gewährleisten.

Die von unseren Partnern angebotenen Lösungen bestehen aus Komponenten, die entweder vollständig cloudbasierte oder teilweise/vollständig lokal bereitgestellt werden können. 
     
Die folgende Abbildung zeigt die Architektur unserer Partnerlösungen auf hoher Ebene.

![Diagramm zur Beschreibung einer Team Cloud Video Interop-Partnerlösung](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>Bereitstellen von Cloud Video Interop

Bei der Bereitstellung einer Cloud Video Interop-Lösung ist es wichtig zu verstehen, dass Sie eine Partnerlösung bereitstellen. Die allgemeinen Schritte zum Bereitstellen von Cloud Video Interop sind im folgenden Diagramm aufgeführt.

![Diagramm zur Beschreibung der Bereitstellung von CVI in Ihrer Organisation](media/deploying-cvi.png)

### <a name="plan"></a>Plan

Während der Planphase sollten Sie die Geräte identifizieren, die Sie nicht durch ein systemeigenes Teams-Gerät ersetzen, und einen Cloud Video Interop-Partner finden, der diese Geräte unterstützen kann.  

Es ist auch wichtig zu verstehen, dass Sie eine Lizenz für jeden Benutzer benötigen, der Besprechungen plant, an denen Ein Cloud Video Interop-fähiges Gerät teilnehmen soll. Beachten Sie, dass genaue Lizenzierungsanforderungen beim Cloud Video Interop-Partner eingeholt werden können. Stellen Sie sicher, dass dies vor dem Starten der Bereitstellung klar ist.

### <a name="configure"></a>Konfigurieren

Der Partner, den Sie für Ihre #A0 ausgewählt haben, stellt Ihnen ein vollständiges Bereitstellungsdokument zur Verfügung, das aus allen Schritten besteht, die zur erfolgreichen Bereitstellung innerhalb Ihrer Organisation erforderlich sind. Dies umfasst Firewallports und IP-Bereiche, Konfigurationsänderungen für Ihre Geräte und andere Einstellungen, die geändert werden müssen.

### <a name="provision"></a>Bereitstellung  

Während der Bereitstellungsphase weisen Sie den entsprechenden Benutzern Gemäß dem Konfigurationshandbuch für Partner Lizenzen zu. Sie müssen auch den Azure-Zustimmungsprozess durchgehen, um dem Partner Zugriff auf Ihre Teams-Umgebung zu ermöglichen. Weitere [Informationen zum Azure-Zustimmungsprozess finden](/azure/active-directory/develop/v2-permissions-and-consent) Sie unter Berechtigungen und Zustimmung im Endpunkt der Microsoft-Identitätsplattform.

### <a name="schedule"></a>Zeitplan

Nachdem ein Benutzer für Cloud Video Interop aktiviert wurde, werden jeder Besprechung, die mit dem Teams Meeting-Add-In für Outlook oder dem Teams-Client geplant ist, automatisch die entsprechenden zusätzlichen Informationen zur Teams-Besprechung hinzugefügt, damit Cloud Video Interop-kompatible Geräte an diesen Besprechungen teilnehmen können.

### <a name="join"></a>Join

Je nach Partnerlösung gibt es mehrere Möglichkeiten, an einer Cloud Video Interop-fähigen Besprechung teil zu nehmen. Genaue Szenarien für die Teilnahme an Besprechungen werden von Ihrem Cloud Video Interop-Partner bereitgestellt. Nachfolgend sind einige Beispiele aufgeführt:

- IVR (Interaktive Sprachantwort) 
  - Sie können sich über die -Tenantkey@domain.
  - Wenn Sie sich im Partner-IVR befinden, werden Sie aufgefordert, die VTC-konferenz-Id ein- und ein-/ zu geben, über die Sie dann mit der Teams-Besprechung in Verbindung treten.
- Direktwahl 
  - Sie können sich direkt in die Teams-Besprechung einwählen, ohne mit der IVR des Partners zu interagieren, indem Sie das Feature für Direktwahl verwenden, indem Sie die vollständige Zeichenfolge des Mandantenschlüssels verwenden. VTC ConferenceId@domain.
- One-Touch-Wähltaste 
  - Wenn Sie über einen integrierten Teams-Raum verfügen, können Sie die von Ihrem Partner angebotenen One-Touch-Wählfunktionen verwenden (ohne eine Wählzeichenfolge eingeben zu müssen).

## <a name="manage-cloud-video-interop"></a>Verwalten von Cloud Video Interop

Nachdem Cloud Video Interop bereitgestellt wurde, können Sie die Geräte mithilfe der von unseren Partnern bereitgestellten Lösungen verwalten. Jeder Partner stellt Ihnen eine verwaltungstechnische Schnittstelle bereit, die sowohl die Lizenz- als auch die Geräteverwaltung umfasst. 

Die Berichterstellung ist auch direkt über die administrative Partnerschnittstelle verfügbar. Weitere Informationen zu Berichtsfunktionen erhalten Sie beim Partner Ihrer Wahl. 

### <a name="troubleshooting-cloud-video-interop"></a>Problembehandlung bei Cloud Video Interop

Cloud Video Interop ist ein vom Partner bereitgestellter Dienst. Wenn Probleme auftreten, besteht der erste Schritt im Verbinden eines Geräts, auf dem der Teams-Client installiert ist, und verbinden Sie es mit demselben Segment wie das Cloud Video Interop-Gerät, das Probleme verursacht. 

Wenn Teams in diesem Segment ordnungsgemäß funktioniert und Sie auch alle vom Partner bereitgestellten Netzwerk- und Konfigurationsrichtlinien befolgt haben, müssen Sie sich zur weiteren Problembehandlung an den Partner wenden. 

## <a name="powershell-for-cloud-video-interop"></a>PowerShell für Cloud Video Interop

Die folgenden PowerShell-Cmdlets stehen Ihnen zur (teilweisen) Automatisierung der Cloud Video Interop-Bereitstellung zur Verfügung.

- **Get-CsTeamsVideoInteropServicepolicy:** Microsoft stellt vordefinierte Richtlinien für jeden unserer unterstützten Partner zur Verfügung, mit denen Sie festlegen können, welche Partner für Cloud Video Interop verwendet werden sollen.<br>Mit diesem Cmdlet können Sie die vordefinierten Richtlinien identifizieren, die Sie in Ihrer Organisation verwenden können. Sie können diese Richtlinie einem oder mehreren Benutzern zuweisen, indem Sie das cmdlet Grant-CsTeamsVideoInteropServicePolicy nutzen.
- **Grant-CsTeamsVideoInteropServicePolicy:** Mit diesem Cmdlet können Sie eine vordefinierte Richtlinie für die Verwendung in Ihrer Organisation zuweisen oder die Richtlinie bestimmten Benutzern zuweisen.
- **New-CsVideoInteropServiceProvider**: Verwenden Sie dieses Cmdlet, um Informationen zu einem unterstützten #A0 anzugeben, den Ihre Organisation verwenden möchte.
- **Set-CsVideoInteropServiceProvider**: Verwenden Sie dieses Cmdlet, um Informationen zu einem unterstützten #A0 zu aktualisieren, den Ihre Organisation verwendet.
- **Get-CsVideoInteropServiceProvider:** Verwenden Sie dieses Cmdlet, um alle Anbieter zu erhalten, die für die Verwendung innerhalb der Organisation konfiguriert wurden.
- **Remove-CsVideoInteropServiceProvider**: Verwenden Sie dieses Cmdlet, um alle Anbieterinformationen zu einem Anbieter zu entfernen, den Ihre Organisation nicht mehr verwendet.