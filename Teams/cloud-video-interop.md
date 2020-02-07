---
title: Cloud-Video-Interoperabilität für Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
f1.keywords:
- NOCSH
description: Mit der Cloud-Video Interoperabilität können Besprechungsraum Geräte von Drittanbietern an Microsoft Teams-Besprechungen teilnehmen.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3a8d3d41d974e78a708fdf91ee6aac13beb6b7b
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825063"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Cloud-Video-Interoperabilität für Microsoft Teams

Cloud Video-Interop (CVI) ist eine von Microsoft qualifizierte Drittanbieterlösung, mit der Drittanbieter-Besprechungsräume (Telepresence) und Personal Video Devices (VTCs) an Microsoft Teams-Besprechungen teilnehmen können.
 
Mit Microsoft Teams erhalten Sie eine umfangreiche Zusammenarbeit an Onlineinhalten in Besprechungen, die Audio, Video und Inhaltsfreigabe beinhalten. Dies kann über den Desktop-und Web-Client sowie über viele Partner Geräte genossen werden, die sich nativ in Microsoft Teams integrieren. Viele Kunden haben jedoch bereits in Video Teleconferencing und persönliche Video Kommunikationsgeräte investiert, was ein Upgrade kostspielig sein kann. Cloud Video-Interop bietet eine einfache Lösung, die es Ihnen ermöglicht, Ihre vorhandenen Lösungen so lange zu verwenden, bis Sie ein Upgrade durchführen können.

Mit Cloud Video-Interop bietet Microsoft Teams eine native Besprechungs Erfahrung für alle Teilnehmer – in Besprechungsräumen oder innerhalb von Teams-Clients.

### <a name="is-cloud-video-interop-for-me"></a>Ist Cloud-Video-Interop für mich?

Cloud Video-Interop bietet einen zwischen Dienst, während Sie zu einer vollständigen Microsoft Teams-Lösung mithilfe von Team Endpunkten wechseln. Der bereitgestellte Dienst sollte Teil des Migrationspfads sein.

Brightcove-Video Interoperabilität richtet sich an Kunden, die die folgenden Kriterien erfüllen:

- Eine große Bereitstellung von Besprechungsraum Geräten und die Bereitstellung persönlicher Videogeräte (50 + Geräte), die nicht für die direkte Integration in Microsoft Teams qualifiziert sind
- Werden von einem unserer Cloud Video-Interop-Partner unterstützt
- Sie möchten während der Migration zu einer nativen Microsoft Teams-Lösung den Wert Ihrer Investition in Ihre aktuellen Besprechungsraum Geräte und persönlichen Videogeräte behalten.

Während Cloud-Video-Interop eine hervorragende Zwischenlösung bietet, ermutigen wir unsere Kunden dazu, unsere nativen Teams zu untersuchen, die Lösungen wie Teams Room Systems langfristig anbieten. 

### <a name="partners-certified-for-microsoft-teams"></a>Partner, die für Microsoft Teams zertifiziert sind

Die folgenden Partner verfügen über Video-Interop-Lösungen für Microsoft Teams. Ihr Unternehmen kann beschließen, mit einer beliebigen Kombination dieser Partner innerhalb Ihres Unternehmens zu arbeiten. 

|Partner|Partner Lösung|
|----|---|
|![Das Logo, das Polycom RealConnect](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Polycom-RealConnect-Dienst</a> |
|![Das Logo, das Pexip Unendlichkeit darstellt](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Pexip unendlich für Microsoft Teams</a> | 
|![Das Logo, das Bluejeans-Gateway darstellt](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">Bluejeans-Gateway für Microsoft Teams</a> |

### <a name="cloud-video-interop-overview"></a>Übersicht über die Cloud-Video Interoperabilität

Cloud Video-Interop ist ein Drittanbieterdienst, der von unseren Partnern bereitgestellt wird, um Interoperabilität zwischen vorhandenen Videokonferenz-und persönlichen Videogeräte Lösungen auf dem Gelände und in Microsoft Teams bereitzustellen.

Die Lösungen, die unsere Partner anbieten, bestehen aus Komponenten, die entweder komplett Cloud-basiert oder teilweise oder vollständig auf dem Gelände bereitgestellt werden können. 
     
Das folgende Diagramm zeigt die allgemeine Architektur unserer Partnerlösungen.

![Diagramm, in dem eine Team-Cloud Video Interop-Partnerlösung beschrieben wird](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>Bereitstellen von Cloud-Video-Interop

Beim Bereitstelleneiner Cloud-Video-Interop-Lösung ist es wichtig zu verstehen, dass Sie eine Partnerlösung bereitstellen. Die allgemeinen Schritte, die Sie für die Bereitstellung von Brightcove-Video Interop ausführen sollten, finden Sie im folgenden Diagramm.

![Diagramm, das die Bereitstellung von CVI in Ihrer Organisation beschreibt](media/deploying-cvi.png)

### <a name="plan"></a>Plan

Während der Planungsphase sollten Sie die Geräte identifizieren, die nicht durch ein systemeigener Teams ersetzt werden sollen, und einen Cloud Video-Interop-Partner finden, der diese Geräte unterstützenkann.  

Es ist auch wichtig zu wissen, dass Sie für jeden Benutzer, der Besprechungen planen soll, eine Lizenz benötigen, in der Sie ein Cloud-Video-Interop-fähiges Gerät beitreten möchten. Beachten Sie, dass die genauen Lizenzierungsanforderungen vom Cloud Video-Interop-Partner abgerufen werden können. Stellen Sie sicher, dass dies klar ist, bevor Sie mit der Bereitstellung beginnen.

### <a name="configure"></a>Konfigurieren

Der Partner, den Sie für Ihre CVI-Bereitstellung ausgewählt haben, stellt ein vollständiges Bereitstellungs Dokument bereit, das alle erforderlichen Schritte für die erfolgreiche Bereitstellung innerhalb Ihrer Organisation umfasst. Dazu gehören Firewall-Ports und IP-Bereiche, Konfigurationsänderungen für Ihre Geräte und andere Einstellungen, die geändert werden müssen.

### <a name="provision"></a>Bereitstellung  

Während der Bereitstellungsphase weisen Sie den entsprechenden Benutzern Lizenzen entsprechend dem Partner-Konfigurationshandbuch zu. Darüber hinaus müssen Sie den Azure-Genehmigungsprozess durchlaufen, um dem Partner den Zugriff auf Ihre Teams-Umgebung zu ermöglichen. Weitere Informationen zum Azure-Genehmigungsprozess finden Sie hier:https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-permissions-and-consent 

### <a name="schedule"></a>Zeitplan

Nachdem ein Benutzer für die Cloud-Video-Interop aktiviert wurde, werden alle Besprechungen, die mit dem Teambesprechung-Add-in für Outlook oder dem Team-Client geplant sind, die entsprechenden zusätzlichen Informationen automatisch in die Teambesprechung aufgenommen, damit Cloud-Video Interop-kompatible Geräte können an diesen Besprechungen teilnehmen.

### <a name="join"></a>Join

Je nach Partnerlösung gibt es mehrere Möglichkeiten, an einer Cloud-Video-Interop-fähigen Besprechung teilzunehmen. Die genauen Szenarien für Besprechungen werden von Ihrem Brightcove-Video-Interop-Partner bereitgestellt. Nachfolgend sind einige Beispiele aufgeführt:

- IVR (Interaktive Sprachantwort) 
  - Sie können sich über die tenantkey@Domain in die IVR des Partners einwählen.
  - Wenn Sie sich im Partner-IVR befinden, werden Sie aufgefordert, die VTC-Konferenz-Nr einzugeben, die Sie dann mit der Teams-Besprechung verbindet.
- Direktwahl 
  - Sie können sich direkt in die Teambesprechung einwählen, ohne mit der IVR des Partners zu interagieren, indem Sie die direkte Wählfunktion verwenden, indem Sie die vollständige Zeichenfolge von tenantkey verwenden. VTC ConferenceId@Domain.
- One-Touch-Dial 
  - Wenn Sie über einen integrierten TeamRoom verfügen, können Sie die von Ihrem Partner angebotenen One-Touch-Wählfunktionen nutzen (ohne eine Wählzeichenfolge eingeben zu müssen).

## <a name="manage-cloud-video-interop"></a>Verwalten von Cloud-Video-Interop

Nachdem Cloud Video-Interop bereitgestellt wurde, können Sie die Geräte mithilfe der von unseren Partnern bereitgestellten Lösungen verwalten. Jeder Partner stellt Ihnen eine Verwaltungsschnittstelle zur Verfügung, die sowohl die Lizenz-als auch die Geräteverwaltung umfasst. 

Die Berichterstattung steht auch direkt über die Verwaltungsoberfläche des Partners zur Verfügung. Wenn Sie weitere Informationen zu den Berichterstellungsfunktionen wünschen, wenden Sie sich an den Partner Ihrer Wahl. 

### <a name="troubleshooting-cloud-video-interop"></a>Problembehandlung bei der Cloud-Video Interoperabilität

Cloud Video-Interop ist ein vom Partner bereitgestellter Dienst. Wenn Probleme auftreten, besteht der erste Schritt darin, ein Gerät zu verbinden, auf dem der Microsoft Teams-Client installiert ist, und es mit dem gleichen Segment wie dem Brightcove-Video-Interop-Gerät zu verbinden, das Probleme verursacht. 

Wenn Teams in diesem Segment ordnungsgemäß funktionieren und Sie auch alle Netzwerk-und Konfigurationsrichtlinien befolgt haben, die der Partner bereitgestellt hat, müssen Sie sich an den Partner wenden, um weitere Informationen zur Problembehandlung zu erhalten. 

## <a name="powershell-for-cloud-video-interop"></a>PowerShell für Cloud-Video-Interop

Die folgenden PowerShell-Cmdlets stehen Ihnen zur (teilweise) Automatisierung der Cloud-Video Interop-Bereitstellung zur Verfügung.

- **Get-CsTeamsVideoInteropServicepolicy**: Microsoft stellt vorgefertigte Richtlinien für jeden unserer unterstützten Partner zur Verfügung, mit denen Sie festlegen können, welche Partner für die Cloud-Video-Interop verwendet werden sollen.<br>Mit diesem Cmdlet können Sie die vorab erstellten Richtlinien identifizieren, die Sie in Ihrer Organisation verwenden können. Sie können diese Richtlinie einem oder mehreren Benutzern zuweisen, indem Sie das Cmdlet Grant-CsTeamsVideoInteropServicePolicy nutzen.
- **Grant-CsTeamsVideoInteropServicePolicy**: mit diesem Cmdlet können Sie eine vordefinierte Richtlinie für die Verwendung in Ihrer Organisation zuweisen oder die Richtlinie bestimmten Benutzern zuweisen.
- **New-CsVideoInteropServiceProvider**: Verwenden Sie dieses Cmdlet, um Informationen zu einem unterstützten CVI-Partner anzugeben, den Ihre Organisation verwenden möchte.
- **Festlegen-CsVideoInteropServiceProvider**: Verwenden Sie dieses Cmdlet, um Informationen zu einem von Ihrer Organisation verwendeten unterstützten CVI-Partner zu aktualisieren.
- **Get-CsVideoInteropServiceProvider**: Verwenden Sie dieses Cmdlet, um alle Anbieter abzurufen, die für die Verwendung innerhalb der Organisation konfiguriert wurden.
- **Remove-CsVideoInteropServiceProvider**: Verwenden Sie dieses Cmdlet, um alle Anbieter Informationen zu einem Anbieter zu entfernen, den Ihre Organisation nicht mehr verwendet.
