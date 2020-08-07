---
title: Einrichten von Cloud-Video-Interoperabilität für Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
f1.keywords:
- NOCSH
description: In diesem Artikel wird erläutert, wie Sie Cloud-Video-Interop für Benutzer in Ihrer Organisation planen und einrichten können.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a1f45967b3e2737f6e2df74c505932ea69afe37f
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582632"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>Einrichten von Cloud-Video-Interoperabilität für Microsoft Teams

Nachdem Sie [Ihre Brightcove-Video-Interop-Partner (n) ausgewählt](cloud-video-interop.md)haben, müssen Sie Ihre Bereitstellung planen, mit Bereitstellungsdetails und dem Partner Mandanten Schlüssel einrichten und der Video-Interop-app in Ihrer Organisation zustimmen. Das folgende Diagramm beschreibt den Prozess. 

![Bereitstellen von CVI in Ihrer Organisation](media/deploying-cvi.png)

## <a name="plan"></a>Plan

Informationen dazu, wie Sie einen Partner oder Partner identifizieren können, der in Ihrer Organisation verwendet werden soll, finden Sie unter [Cloud Video-Interop für Microsoft Teams](cloud-video-interop.md) . 

So planen Sie die benutzerbasierte/Concurrent/Site Wide-Aktivierung: 

- Wählen Sie ein Bereitstellungsmodell/gehostetes Modell für ihre Verwendung aus.
- Wählen Sie den Lizenzplan aus, der ideal für Ihre Organisation ist. 
- Plan für die Kapazität von VMS ist, dass Sie Ihre Video Infrastruktur hosten.

## <a name="configure"></a>Konfigurieren 

Führen Sie die folgenden Schritte aus, um Brightcove-Video Interop zu konfigurieren. 

1. Besorgen Sie sich Konfigurationsinformationen von den von Ihnen ausgewählten Partnern/Partnern (Mandanten Schlüssel, Daten-und-dann...). Sie können einen oder mehrere Video-Interop-Partner in Ihrer Organisation verwenden. 

2. Stellen Sie sicher, dass Ihr Netzwerk ordnungsgemäß konfiguriert ist. Konfigurieren Sie Ihre standardbasierte Video Firewall für den Umkreisnetzwerk Durchlauf, um Sie zu unterstützen. Beispiel: 
    - Cisco VCS-e                  
    - Polycom RPAD

3. Konfigurieren Sie integrierte Räume mit Exchange und OTD. In den meisten Fällen müssten zusätzliche Relays in Ihrer Umgebung eingerichtet und konfiguriert werden.


## <a name="provision"></a>Bereitstellung
 
Der Mandanten Schlüssel ist die Wählfunktion des Partner Diensts. Im folgenden Beispiel ist 813878896@t.PLCM.VC der Mandanten Schlüssel. 

![Beispiel für Mandanten Schlüssel](media/tenant-key-example.png) 

Sie müssen die folgenden Cmdlets ausführen, um den Mandanten Schlüssel bereitzustellen, und Sie können auch SELECT-Benutzer oder Ihre gesamte Organisation aktivieren, um Besprechungen mit Video-Interop-Koordinaten zu erstellen.

 
- ** [Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft stellt für jeden unserer unterstützten Partner vorgefertigte Richtlinien bereit, mit denen Sie festlegen können, welche Partner für die Cloud-Video-Interop verwendet werden.

    Mit diesem Cmdlet können Sie die vorab erstellten Richtlinien identifizieren, die Sie in Ihrer Organisation verwenden können. Sie können diese Richtlinie einem oder mehreren Benutzern zuweisen, indem Sie das Cmdlet Grant-CsTeamsVideoInteropServicePolicy nutzen.
 
- ** [Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** Mit dem Cmdlet Grant-CsTeamsVideoInteropServicePolicy können Sie eine vordefinierte Richtlinie für die Verwendung in Ihrer Organisation zuweisen oder die Richtlinie bestimmten Benutzern zuweisen.
 
- ** [Neu-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):** Verwenden Sie die CsVideoInteropServiceProvider, um Informationen zu einem unterstützten CVI-Partner anzugeben, den Ihre Organisation verwenden möchte.
 
- ** [Satz-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):** Verwenden Sie das CsVideoInteropServiceProvider, um Informationen zu einem unterstützten CVI-Partner zu aktualisieren, der in Ihrer Organisation verwendet wird.
 
- ** [Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):** Rufen Sie alle Anbieter ab, die für die Verwendung innerhalb der Organisation konfiguriert wurden.
 
- ** [Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):** Verwenden Sie Remove-CsVideoInteropServiceProvider, um alle Anbieter Informationen zu einem Anbieter zu entfernen, den Ihre Organisation nicht mehr verwendet.  
 
## <a name="consent"></a>Zustimmung

Sie müssen die Genehmigungs Genehmigung für Video Teleconferencing Devices (VTCs) bereitstellen, um über den Partnerdienst an ihren Organisationen teilzunehmen. Dieser Link zur Zustimmung wird auch von Ihrem Partner zur Verfügung gestellt.  
 
Wenn diese Schritte abgeschlossen sind, werden die Benutzer, die über das Grant-Cmdlet oben einzeln aktiviert sind, oder alle Benutzer in der Organisation, wenn der Mandant aktiviert ist, VTC-Koordinaten in allen von Ihnen geplanten Teams-Besprechungen haben. Alle VTC können über diese Koordinaten an diesen Besprechungen teilnehmen.


|Name|Kurzbeschreibung der Anwendungsberechtigung| Beschreibung|
|--|--|---|
|Calls. JoinGroupCall. all|Teilnehmen an Gruppen anrufen und Besprechungen als app (Preview)|Ermöglicht der APP die Teilnahme an Gruppen anrufen und geplanten Besprechungen in Ihrer Organisation, ohne dass ein Benutzer angemeldet ist.  Die APP wird mit den Berechtigungen eines Verzeichnis Benutzers für Besprechungen in Ihrem Mandanten verbunden.|
|Calls. JoinGroupCallasGuest. all|Teilnehmen an Gruppen anrufen und Besprechungen als Gastbenutzer (Preview)|Ermöglicht der APP, anonym an Gruppen anrufen und geplanten Besprechungen in Ihrer Organisation teilzunehmen, ohne dass ein Benutzer angemeldet ist.  Die APP wird als Gast zu Besprechungen in Ihrem Mandanten verbunden.|
|Calls. AccessMedia. all|Zugreifen auf Mediendatenströme in einem Anruf als app (Preview)|Ermöglicht der APP den direkten Zugriff auf Mediendatenströme in einem Anruf ohne einen angemeldeten Benutzer.|
|OnlineMeetings. Read. all|Online Besprechungsdetails lesen (Preview)|Ermöglicht der APP, Online Besprechungsdetails in Ihrer Organisation zu lesen, ohne dass ein Benutzer angemeldet ist.|

## <a name="schedule"></a>Zeitplan

Als nächstes planen Sie Teams-Besprechung mit Video-Interop-Koordinaten. Der aktivierte Benutzer kann Teams-Besprechungen über Folgendes planen:
- [Teambesprechung-Add-in für Outlook](teams-add-in-for-outlook.md)
- Teams Clientdesktop und Mobiltelefon


## <a name="join"></a>Join

Sie können mit ihren VTC-Geräten mit den folgenden Methoden an Teams-Besprechungen teilnehmen:
 
- IVR (Interaktive Sprachantwort)
    - Sie können sich über die tenantkey@Domain in die IVR des Partners einwählen. 
    - Sobald Sie in der Partner-IVR sind, werden Sie aufgefordert, die VTC-Konferenz-Nr einzugeben, die Sie dann mit der Teams-Besprechung verbindet.
- Direktwahl
    - Sie können sich direkt in die Teambesprechung einwählen, ohne mit der IVR des Partners zu interagieren, indem Sie die direkte Wählfunktion verwenden, indem Sie die vollständige Zeichenfolge von tenantkey verwenden. VTC ConferenceId@Domain.
- One-Touch-Dial
    - Wenn Sie über einen integrierten TeamRoom verfügen, können Sie die von Ihrem Partner angebotenen One-Touch-Wählfunktionen nutzen (ohne eine Wählzeichenfolge eingeben zu müssen).

Und schließlich können Sie sich mithilfe von Audio, Video und Inhaltsfreigabe in ihren Besprechungen mit Teams besprechen. 
