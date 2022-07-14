---
title: Cloud-Video-Interoperabilität für Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: naforer
f1.keywords:
- NOCSH
description: Verwenden Sie Cloud Video Interop als Zwischenlösung, um Besprechungsraumgeräten von Drittanbietern die Teilnahme an Microsoft Teams-Besprechungen zu ermöglichen.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91ec337ad94341e20b07cd376be5156a526d8cd0
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789360"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Cloud-Video-Interoperabilität für Microsoft Teams

Cloud Video Interop (CVI) ist eine microsoftqualifizierte Drittanbieterlösung, die es Drittanbieter-Besprechungsräumen (Telepresence) und persönlichen Videogeräten (VTCs) ermöglicht, an Microsoft Teams-Besprechungen teilzunehmen.
 
Mit Microsoft Teams erhalten Sie eine umfassende Zusammenarbeit an Onlineinhalten in Besprechungen, die Audio-, Video- und Inhaltsfreigaben umfassen. Dies kann über den Desktop- und Webclient sowie über viele Partnergeräte, die nativ in Microsoft Teams integriert sind, genossen werden. Viele Kunden haben jedoch bereits in Videotelekonferenzen und persönliche Videokommunikationsgeräte investiert, was für ein Upgrade teuer sein kann. Cloud Video Interop bietet eine einfache Lösung, mit der Sie Ihre vorhandenen Lösungen weiterhin verwenden können, bis Sie zum Upgrade bereit sind.

Mit Cloud Video Interop bietet Microsoft Teams eine native Besprechungserfahrung für alle Teilnehmer – in Besprechungsräumen oder innerhalb von Teams-Clients.

### <a name="is-cloud-video-interop-for-me"></a>Ist Cloud Video Interop für mich?

Cloud Video Interop bietet einen Zwischendienst, während Sie mithilfe von Teams-Endpunkten zu einer vollständigen systemeigenen Microsoft Teams-Lösung wechseln. Der bereitgestellte Dienst sollte Teil Ihres Migrationspfads sein.

Cloud Video Interop richtet sich an Kunden, die die folgenden Kriterien erfüllen:

- Verfügen Über eine große Bereitstellung von Geräten für Besprechungsräume und persönliche Videogeräte (mehr als 50 Geräte), die nicht für die direkte Integration in Microsoft Teams qualifiziert sind
- Werden von einem unserer Cloud Video Interop-Partner unterstützt
- Sie möchten den Wert ihrer Investition in ihre aktuellen Besprechungsraumgeräte und persönlichen Videogeräte während der Migration zu einer nativen Microsoft Teams-Lösung beibehalten.

Cloud Video Interop bietet zwar eine großartige Zwischenlösung, aber wir empfehlen unseren Kunden, sich langfristig mit unseren nativen Teams-Besprechungslösungen wie Teams Room Systems zu befassen. 

### <a name="office-365-us-government-and-third-party-services"></a>Office 365 US-Regierung und Dienste von Drittanbietern

Office 365 bietet die Möglichkeit, Anwendungen von Drittanbietern in SharePoint Online-Websites, Skype for Business, Teams, Office-Anwendungen in Microsoft 365 Apps for Enterprise (z. B. Word, Excel, PowerPoint und Outlook) zu integrieren und Outlook Web App. Darüber hinaus unterstützt Office 365 die Integration mit Drittanbietern. Diese Anwendungen und Dienste von Drittanbietern umfassen möglicherweise das Speichern, Übertragen und Verarbeiten der Kundendaten Ihrer Organisation auf Drittanbietersystemen, die sich außerhalb der Office 365 Infrastruktur befinden und daher nicht unter die Office 365 Compliance- und Datenschutzverpflichtungen fallen. **Es wird empfohlen, dass Sie die Datenschutz- und Complianceerklärungen der Drittanbieter überprüfen, wenn Sie die angemessene Nutzung dieser Dienste für Ihre Organisation bewerten.**



### <a name="partners-certified-for-microsoft-teams"></a>Partner, die für Microsoft Teams zertifiziert sind

Die folgenden Partner verfügen über Video-Interoperabilitätslösungen für Microsoft Teams. Ihr Unternehmen kann sich entscheiden, mit einer beliebigen Kombination dieser Partner in Ihrem Unternehmen zusammenzuarbeiten. 

|Partner|Partnerlösung|
|----|---|
|![Das Logo, das Poly RealConnect darstellt.](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Poly RealConnect-Dienst</a> |
|![Das Logo, das Pexip Infinity darstellt.](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Pexip Infinity für Microsoft Teams</a> | 
|![Das Logo, das das BlueJeans-Gateway darstellt.](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">BlueJeans-Gateway für Microsoft Teams</a> |
|![Das Logo, das Cisco CVI darstellt.](media/cisco.png)|<a href="https://aka.ms/CiscoCVI" target="_blank">Cisco Webex Video Integration für Microsoft Teams</a>|

### <a name="cloud-video-interop-overview"></a>Übersicht über Cloud Video Interop

Cloud Video Interop ist ein Drittanbieterdienst, der von unseren Partnern angeboten wird, um die Interoperabilität zwischen vorhandenen Videokonferenzen und lokalen Lösungen für persönliche Videogeräte und Microsoft Teams bereitzustellen.

Die von unseren Partnern angebotenen Lösungen bestehen aus Komponenten, die entweder vollständig cloudbasiert oder teilweise/vollständig lokal bereitgestellt werden können. 
     
Das folgende Diagramm zeigt die allgemeine Architektur unserer Partnerlösungen.

![Diagramm, das eine Microsoft Teams Cloud Video Interop-Partnerlösung beschreibt.](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>Bereitstellen von Cloud Video Interop

Bei der Bereitstellung einer Cloud Video Interop-Lösung ist es wichtig zu verstehen, dass Sie eine Partnerlösung bereitstellen. Die allgemeinen Schritte, die Sie zum Bereitstellen von Cloud Video Interop ausführen sollten, sind im folgenden Diagramm aufgeführt.

![Diagramm, das die Bereitstellung von CVI in Ihrer Organisation beschreibt.](media/deploying-cvi.png)

### <a name="plan"></a>Plan

Während der Planungsphase sollten Sie die Geräte identifizieren, die Sie nicht durch ein systemeigenes Teams-Gerät ersetzen werden, und einen Cloud Video Interop-Partner finden, der diese Geräte unterstützen kann.  

Es ist auch wichtig zu wissen, dass Sie eine Lizenz für jeden Benutzer benötigen, der Besprechungen plant, an denen ein Cloud Video Interop-fähiges Gerät teilnehmen soll. Beachten Sie, dass genaue Lizenzierungsanforderungen vom Cloud Video Interop-Partner abgerufen werden können. Stellen Sie sicher, dass dies klar ist, bevor Sie die Bereitstellung starten.

### <a name="configure"></a>Konfigurieren

Der Partner, den Sie für Ihre CVI-Bereitstellung ausgewählt haben, stellt Ihnen ein vollständiges Bereitstellungsdokument bereit, das aus allen Schritten besteht, die für eine erfolgreiche Bereitstellung in Ihrer Organisation erforderlich sind. Dazu gehören Firewallports und IP-Bereiche, Konfigurationsänderungen für Ihre Geräte und andere Einstellungen, die geändert werden müssen.

### <a name="provision"></a>Bereitstellung  

Während der Bereitstellungsphase weisen Sie den entsprechenden Benutzern gemäß dem Partnerkonfigurationshandbuch Lizenzen zu. Sie müssen auch den Azure-Zustimmungsprozess durchlaufen, um dem Partner Zugriff auf Ihre Teams-Umgebung zu gewähren. Weitere Informationen zum Azure-Zustimmungsprozess finden Sie [unter Berechtigungen und Zustimmung im Microsoft Identity Platform Endpunkt](/azure/active-directory/develop/v2-permissions-and-consent).

### <a name="schedule"></a>Zeitplan

Nachdem ein Benutzer für die Cloud-Video-Interoperabilität aktiviert wurde, werden jeder Besprechung, die entweder mit dem Teams-Besprechungs-Add-In für Outlook oder dem Teams-Client geplant ist, automatisch die entsprechenden zusätzlichen Informationen zur Teams-Besprechung hinzugefügt, sodass Cloud Video Interop-kompatible Geräte an diesen Besprechungen teilnehmen können.

### <a name="join"></a>Join

Je nach Partnerlösung gibt es mehrere Möglichkeiten, an einer Cloud Video Interop-fähigen Besprechung teilzunehmen. Genaue Szenarien für die Teilnahme an Besprechungen werden von Ihrem Cloud Video Interop-Partner bereitgestellt. Nachfolgend sind einige Beispiele aufgeführt:

- IVR (Interaktive Sprachantwort) 
  - Sie können sich mithilfe der tenantkey@domain beim IVR des Partners einwählen.
  - Wenn Sie sich im Partner-IVR befinden, werden Sie aufgefordert, die VTC conferenceId einzugeben, die Sie dann mit der Teams-Besprechung verbindet.
- Direktwahl 
  - Sie können sich direkt in die Teams-Besprechung einwählen, ohne mit dem IVR des Partners zu interagieren, indem Sie die Direktwahlfunktion verwenden und dabei die vollständige Zeichenfolge des Mandantenschlüssels verwenden. VTC-ConferenceId@domain.
- 1-Touch-Wählhilfe 
  - Wenn Sie über einen integrierten Teams-Raum verfügen, können Sie die 1-Finger-Wählfunktionen Ihres Partners verwenden (ohne eine Wählzeichenfolge eingeben zu müssen).

## <a name="manage-cloud-video-interop"></a>Verwalten der Cloud-Video-Interoperabilität

Nachdem Cloud Video Interop bereitgestellt wurde, können Sie die Geräte mithilfe der von unseren Partnern bereitgestellten Lösungen verwalten. Jeder Partner stellt Ihnen eine Verwaltungsschnittstelle zur Verfügung, die sowohl die Lizenz- als auch die Geräteverwaltung umfasst. 

Die Berichterstellung ist auch direkt über die Verwaltungsschnittstelle des Partners verfügbar. Für weitere Informationen zu Berichtsfunktionen wenden Sie sich an den Partner Ihrer Wahl. 

### <a name="troubleshooting-cloud-video-interop"></a>Problembehandlung bei Cloud Video Interop

Cloud Video Interop ist ein von Partnern bereitgestellter Dienst. Wenn Probleme auftreten, besteht der erste Schritt darin, ein Gerät zu verbinden, auf dem der Teams-Client installiert ist, und es mit demselben Segment wie das Cloud Video Interop-Gerät zu verbinden, das Probleme verursacht. 

Wenn Teams in diesem Segment ordnungsgemäß funktioniert und Sie auch alle vom Partner bereitgestellten Netzwerk- und Konfigurationsrichtlinien befolgt haben, müssen Sie sich zur weiteren Problembehandlung an den Partner wenden. 

## <a name="powershell-for-cloud-video-interop"></a>PowerShell für Cloud Video Interop

Die folgenden PowerShell-Cmdlets stehen Ihnen zur (teilweisen) Automatisierung der Cloud Video Interop-Bereitstellung zur Verfügung.

- **Get-CsTeamsVideoInteropServicepolicy**: Microsoft stellt vordefinierte Richtlinien für jeden unserer unterstützten Partner bereit, mit denen Sie festlegen können, welche Partner für Cloud Video Interop verwendet werden sollen.<br>Mit diesem Cmdlet können Sie die vordefinierten Richtlinien identifizieren, die Sie in Ihrer Organisation verwenden können. Sie können diese Richtlinie einem oder mehreren Ihrer Benutzer zuweisen, indem Sie das cmdlet Grant-CsTeamsVideoInteropServicePolicy verwenden.
- **Grant-CsTeamsVideoInteropServicePolicy**: Mit diesem Cmdlet können Sie eine vordefinierte Richtlinie für die Verwendung in Ihrer Organisation zuweisen oder die Richtlinie bestimmten Benutzern zuweisen.
- **New-CsVideoInteropServiceProvider**: Verwenden Sie dieses Cmdlet, um Informationen zu einem unterstützten CVI-Partner anzugeben, den Ihre Organisation verwenden möchte.
- **Set-CsVideoInteropServiceProvider**: Verwenden Sie dieses Cmdlet, um Informationen zu einem unterstützten CVI-Partner zu aktualisieren, den Ihre Organisation verwendet.
- **Get-CsVideoInteropServiceProvider**: Verwenden Sie dieses Cmdlet, um alle Anbieter abzurufen, die für die Verwendung innerhalb der Organisation konfiguriert wurden.
- **Remove-CsVideoInteropServiceProvider**: Verwenden Sie dieses Cmdlet, um alle Anbieterinformationen zu einem Anbieter zu entfernen, den Ihre Organisation nicht mehr verwendet.