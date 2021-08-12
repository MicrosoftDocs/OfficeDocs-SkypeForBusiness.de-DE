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
description: In diesem Artikel wird erläutert, wie Sie Cloud Video Interop für Benutzer in Ihrer Organisation planen und einrichten können.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bea2f250e91b8a02cefea70db0b80fcd8cc35cce6ecb079c6417c0a6c31bc55c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322757"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>Einrichten von Cloud-Video-Interoperabilität für Microsoft Teams

Nachdem Sie Ihre [Cloud Video Interop-Partner](cloud-video-interop.md)ausgewählt haben, müssen Sie die Bereitstellung planen, die Einrichtung mit Bereitstellungsdetails und dem Mandantenschlüssel des Partners einrichten und der Video-Inaktivitäts-App in Ihrer Organisation zustimmen. Das folgende Diagramm beschreibt den Prozess. 

![Bereitstellen von CVI in Ihrer Organisation](media/deploying-cvi.png)

## <a name="plan"></a>Plan

Informationen zum Identifizieren von Partnern, die in Ihrer Microsoft Teams verwendet werden müssen, finden Sie unter [Cloud Video Interop](cloud-video-interop.md) für weitere Informationen. 

So planen Sie die benutzerbasierte/gleichzeitige/websiteweite Aktivierung: 

- Wählen Sie ein Bereitstellungsmodell/gehostetes Modell für Ihre Verwendung aus.
- Wählen Sie den Lizenzplan aus, der ideal für Ihre Organisation geeignet ist. 
- Planen Sie die Kapazität von VMs, wenn Sie Ihre Videoinfrastruktur hosten.

## <a name="configure"></a>Konfigurieren 

Führen Sie die folgenden Schritte aus, um Cloud Video Interop zu konfigurieren. 

1. Rufen Sie Konfigurationsinformationen von den ausgewählten Partnern ab (Mandantenschlüssel, appIds ...). Sie können einen oder mehrere Video interop-Partner in Ihrer Organisation verwenden. 

2. Stellen Sie sicher, dass Ihr Netzwerk ordnungsgemäß konfiguriert ist. Konfigurieren Sie Ihre standardbasierte Videofirewall für die Umkreisnetzwerktraversalung zur Unterstützung. Zum Beispiel: 
    - Cisco VCS-e                  
    - Polycom RPAD

3. Konfigurieren Sie integrierte Räume mit Exchange und OTD. In den meisten Fällen muss zusätzliches Relay in Ihrer Umgebung eingerichtet und konfiguriert werden.


## <a name="provision"></a>Bereitstellung
 
Der Mandantschlüssel ist der Auswähler des Partnerdiensts. Im folgenden Beispiel ist 813878896@t.plcm.vc der Mandantschlüssel. 

![Beispiel für einen Mandantenschlüssel](media/tenant-key-example.png) 

Sie müssen die folgenden Cmdlets ausführen, um den Mandantenschlüssel bereitstellen zu können, und außerdem ausgewählten Benutzern oder ihrer gesamten Organisation ermöglichen, Besprechungen mit Video-Inaktivitätskoordinaten zu erstellen.

 
- **[Get-CsTeamsVideoInteropServicepolicy](/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft stellt vorgefertigte Richtlinien für jeden unserer unterstützten Partner zur Verfügung, mit denen Sie festlegen können, welche Partner für die Inaktivität bei Cloud-Video verwendet werden sollen.

    Mit diesem Cmdlet können Sie die vorgefertigten Richtlinien identifizieren, die Sie in Ihrer Organisation verwenden können. Sie können diese Richtlinie einem oder mehreren Benutzern zuweisen, die das cmdlet Grant-CsTeamsVideoInteropServicePolicy nutzen.
 
- **[Grant-CsTeamsVideoInteropServicePolicy:](/powershell/module/skype/grant-csteamsvideointeropservicepolicy)** Das Grant-CsTeamsVideoInteropServicePolicy-Cmdlet ermöglicht es Ihnen, eine vorgefertigte Richtlinie zur Verwendung in Ihrer Organisation oder die Richtlinie bestimmten Benutzern zuzuordnen.
 
- **[New-CsVideoInteropServiceProvider](/powershell/module/skype/new-csvideointeropserviceprovider):** Verwenden Sie New-CsVideoInteropServiceProvider, um Informationen zu einem unterstützten CVI-Partner anzugeben, den Ihre Organisation verwenden möchte.
 
- **[Set-CsVideoInteropServiceProvider](/powershell/module/skype/set-csvideointeropserviceprovider):** Verwenden Sie Set-CsVideoInteropServiceProvider, um Informationen zu einem unterstützten CVI-Partner zu aktualisieren, den Ihre Organisation verwendet.
 
- **[Get-CsVideoInteropServiceProvider](/powershell/module/skype/get-csvideointeropserviceprovider):** Hier erhalten Sie alle Anbieter, die für die Verwendung innerhalb der Organisation konfiguriert wurden.
 
- **[Remove-CsVideoInteropServiceProvider:](/powershell/module/skype/remove-csvideointeropserviceprovider)** Verwenden Remove-CsVideoInteropServiceProvider, um alle Anbieterinformationen zu einem Anbieter zu entfernen, den Ihre Organisation nicht mehr verwendet.  
 
## <a name="consent"></a>Zustimmung

Sie müssen die Zustimmung der VTCs (Video Teleconferencing Devices) erteilen, um über den Partnerdienst an Besprechungen in Ihrem Unternehmen teilnehmen zu können. Dieser Zustimmungslink wird auch von Ihrem Partner bereitgestellt.  
 
Nach Abschluss dieser Schritte verfügen die Benutzer, die über das oben beschriebene Cmdlet Grant einzeln aktiviert werden, oder alle Benutzer in der Organisation, wenn der Mandant aktiviert ist, über VTC-Koordinaten in allen Teams-Besprechungen, die sie planen. Jeder VTC kann über diese Koordinaten an diesen Besprechungen teilnehmen.


|Name|Kurzbeschreibung für Anwendungsberechtigungen| Beschreibung|
|--|--|---|
|Calls.JoinGroupCall.All|Teilnehmen an Gruppenanrufen und -besprechungen als App (Vorschau)|Ermöglicht der App, ohne angemeldeten Benutzer an Gruppenanrufen und geplanten Besprechungen in Ihrer Organisation teilzunehmen.  Die App wird mit den Berechtigungen eines Verzeichnisbenutzers für Besprechungen in Ihrem Mandanten verbunden.|
|Calls.JoinGroupCallasGuest.All|Teilnehmen an Gruppenanrufen und -besprechungen als Gastbenutzer (Vorschau)|Ermöglicht der App die anonyme Teilnahme an Gruppenanrufen und geplanten Besprechungen in Ihrer Organisation ohne angemeldeten Benutzer.  Die App wird als Gast an Besprechungen in Ihrem Mandanten teilnehmen.|
|Calls.AccessMedia.All|Zugreifen auf Medienstreams während eines Aufrufs als App (Vorschau)|Ermöglicht der App den direkten Zugriff auf Medienstreams in einem -Aufruf, ohne dass ein angemeldeter Benutzer angemeldet ist.|
|OnlineMeetings.Read.All|Details zur Onlinebe besprechung lesen (Vorschau)|Ermöglicht der App das Lesen von Online-Besprechungsdetails in Ihrer Organisation, ohne dass ein angemeldeter Benutzer angemeldet ist.|

## <a name="schedule"></a>Zeitplan

Als Nächstes planen Teams Besprechung mit Video-Inopkoordinaten. Der aktivierte Benutzer kann Teambesprechungen über dies planen:
- [Teams Besprechungs-Add-In für Outlook](teams-add-in-for-outlook.md)
- Teams Clientdesktop und mobile Geräte


## <a name="join"></a>Join

Sie können an Teams mit Ihren VTC-Geräten auf folgende Weise teilnehmen:
 
- IVR (Interactive Voice Response, interaktive Sprachantwort)
    - Sie können sich über die -Wählscheibe bei der IVR des Partners tenantkey@domain. 
    - Sobald Sie sich im Partner IVR befinden, werden Sie zur Eingabe der VTC conferenceId aufgefordert, über die Sie dann mit der Besprechung Teams werden.
- Direktwahl
    - Sie können sich direkt in die Teams-Besprechung einwählen, ohne mit dem IVR des Partners zu interagieren, indem Sie die vollständige Zeichenfolge des Mandantenschlüssels verwenden. VTC ConferenceId@domain.
- One-Touch Dial
    - Wenn Sie über einen integrierten Teams verfügen, können Sie die von Ihrem Partner gebotenen Ein-Finger-Wählfunktionen verwenden (ohne eine Wählzeichenfolge eingeben zu müssen).

Und schließlich: Beteiligen Sie Teams an Ihren Besprechungen mithilfe von Audio, Video und Inhaltsfreigabe.