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
ms.openlocfilehash: 64d790e775ac0d76de48a71de8d165656f2e6927
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102601"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>Einrichten von Cloud-Video-Interoperabilität für Microsoft Teams

Nachdem Sie Ihre [Cloud Video Interop-Partner ausgewählt](cloud-video-interop.md)haben, müssen Sie Ihre Bereitstellung planen, sich mit Bereitstellungsdetails und Partner-Mandantenschlüssel einrichten und der App für Videointeops in Ihrer Organisation zustimmen. Im folgenden Diagramm wird der Prozess dargestellt. 

![Bereitstellen von CVI in Ihrer Organisation](media/deploying-cvi.png)

## <a name="plan"></a>Plan

Informationen zum Identifizieren eines Partners oder partners, der in Ihrer Organisation verwendet werden soll, finden Sie unter [Cloud Video Interop für Microsoft Teams.](cloud-video-interop.md) 

So planen Sie die benutzerbasierte/gleichzeitige/websiteweite Aktivierung: 

- Wählen Sie ein Bereitstellungsmodell/gehostetes Modell für Ihre Verwendung aus.
- Wählen Sie den Lizenzplan aus, der ideal für Ihre Organisation ist. 
- Planen Sie die Kapazität von VMs, wenn Sie Ihre Videoinfrastruktur hosten.

## <a name="configure"></a>Konfigurieren 

Führen Sie die folgenden Schritte aus, um Cloud Video Interop zu konfigurieren. 

1. Rufen Sie Konfigurationsinformationen von den ausgewählten Partnern (Mandantenschlüssel, appIds...) ab. Sie können einen oder mehrere Videopartner in Ihrer Organisation verwenden 

2. Stellen Sie sicher, dass Ihr Netzwerk ordnungsgemäß konfiguriert ist. Konfigurieren Sie Ihre standardbasierte Videofirewall für den Umkreisnetzwerkverkehr zur Unterstützung. Beispiel: 
    - Cisco VCS-e                  
    - Polycom RPAD

3. Konfigurieren Sie integrierte Räume mit Exchange und OTD. In den meisten Fällen müssten zusätzliche Relays in Ihrer Umgebung eingerichtet und konfiguriert werden.


## <a name="provision"></a>Bereitstellung
 
Der Mandantenschlüssel ist das Auswählen zum Partnerdienst. Im folgenden Beispiel ist 813878896@t.plcm.vc Mandantenschlüssel. 

![Beispiel für Mandantenschlüssel](media/tenant-key-example.png) 

Sie müssen die folgenden Cmdlets ausführen, um den Mandantenschlüssel bereitstellen zu können, und außerdem ausgewählten Benutzern oder Ihrer gesamten Organisation das Erstellen von Besprechungen mit Videokoordinaten ermöglichen.

 
- **[Get-CsTeamsVideoInteropServicepolicy](/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft stellt vordefinierte Richtlinien für jeden unserer unterstützten Partner zur Verfügung, mit denen Sie festlegen können, welche Partner für die In-Interops für Cloudvideos verwendet werden sollen.

    Mit diesem Cmdlet können Sie die vordefinierten Richtlinien identifizieren, die Sie in Ihrer Organisation verwenden können. Sie können diese Richtlinie einem oder mehreren Benutzern zuweisen, indem Sie das cmdlet Grant-CsTeamsVideoInteropServicePolicy nutzen.
 
- **[Grant-CsTeamsVideoInteropServicePolicy](/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** Das Grant-CsTeamsVideoInteropServicePolicy-Cmdlet ermöglicht es Ihnen, eine vordefinierte Richtlinie für die Verwendung in Ihrer Organisation zuzuordnen oder die Richtlinie bestimmten Benutzern zuzuordnen.
 
- **[New-CsVideoInteropServiceProvider](/powershell/module/skype/new-csvideointeropserviceprovider):** Verwenden Sie New-CsVideoInteropServiceProvider, um Informationen zu einem unterstützten New-CsVideoInteropServiceProvider anzugeben, den Ihre Organisation verwenden möchte.
 
- **[Set-CsVideoInteropServiceProvider](/powershell/module/skype/set-csvideointeropserviceprovider):** Verwenden Sie Set-CsVideoInteropServiceProvider, um Informationen zu einem unterstützten Set-CsVideoInteropServiceProvider zu aktualisieren, den Ihre Organisation verwendet.
 
- **[Get-CsVideoInteropServiceProvider](/powershell/module/skype/get-csvideointeropserviceprovider):** Holen Sie sich alle Anbieter, die für die Verwendung innerhalb der Organisation konfiguriert wurden.
 
- **[Remove-CsVideoInteropServiceProvider](/powershell/module/skype/remove-csvideointeropserviceprovider):** Verwenden Remove-CsVideoInteropServiceProvider, um alle Anbieterinformationen zu einem Anbieter zu entfernen, den Ihre Organisation nicht mehr verwendet.  
 
## <a name="consent"></a>Zustimmung

Sie müssen die Zustimmung für die Video-Telekonferenzgeräte (VTCs) erteilen, um über den Partnerdienst an Besprechungen in Ihren Organisationen teilnehmen zu können. Dieser Zustimmungslink wird auch von Ihrem Partner bereitgestellt.  
 
Wenn diese Schritte abgeschlossen sind, verfügen die Benutzer, die über das oben beschriebene Cmdlet "Gewähren" einzeln aktiviert sind, oder alle Benutzer in der Organisation, wenn der Mandant aktiviert ist, in allen von ihnen geplanten Teams-Besprechungen über VTC-Koordinaten. Jeder VTC kann über diese Koordinaten an diesen Besprechungen teilnehmen.


|Name|Kurzbeschreibung für Anwendungsberechtigungen| Beschreibung|
|--|--|---|
|Calls.JoinGroupCall.All|Teilnehmen an Gruppenanrufen und Besprechungen als App (Vorschau)|Ermöglicht der App die Teilnahme an Gruppenanrufen und geplanten Besprechungen in Ihrer Organisation ohne angemeldeten Benutzer.  Die App wird mit den Berechtigungen eines Verzeichnisbenutzers für Besprechungen in Ihrem Mandanten verbunden.|
|Calls.JoinGroupCallasGuest.All|Teilnehmen an Gruppenanrufen und Besprechungen als Gastbenutzer (Vorschau)|Ermöglicht der App die anonyme Teilnahme an Gruppenanrufen und geplanten Besprechungen in Ihrer Organisation ohne angemeldeten Benutzer.  Die App wird als Gast an Besprechungen in Ihrem Mandanten teilnehmen.|
|Calls.AccessMedia.All|Zugreifen auf Medienströme in einem Anruf als App (Vorschau)|Ermöglicht der App den direkten Zugriff auf Medienströme in einem Anruf ohne angemeldeten Benutzer.|
|OnlineMeetings.Read.All|Lesen von Onlinebetreffdetails (Vorschau)|Ermöglicht der App das Lesen von Online-Besprechungsdetails in Ihrer Organisation ohne angemeldeten Benutzer.|

## <a name="schedule"></a>Zeitplan

Als Nächstes planen Sie die Teams-Besprechung mit Videokoordinaten. Der aktivierte Benutzer kann Teambesprechungen über:
- [Teams Meeting Add-In für Outlook](teams-add-in-for-outlook.md)
- Desktop und Mobile des Teams-Clients


## <a name="join"></a>Join

Sie können auf folgende Weise an Teams-Besprechungen mit Ihren VTC-Geräten teilnehmen:
 
- IVR (Interaktive Sprachantwort)
    - Sie können sich über die -Tenantkey@domain. 
    - Sobald Sie sich im Partner-IVR befinden, werden Sie aufgefordert, die VTC-konferenz-Id ein- und ein-/ zu geben, über die Sie dann mit der Teams-Besprechung in Verbindung treten.
- Direktwahl
    - Sie können sich direkt in die Teams-Besprechung einwählen, ohne mit der IVR des Partners zu interagieren, indem Sie das Feature für Direktwahl verwenden, indem Sie die vollständige Zeichenfolge des Mandantenschlüssels verwenden. VTC ConferenceId@domain.
- One-Touch-Wähltaste
    - Wenn Sie über einen integrierten Teams-Raum verfügen, können Sie die von Ihrem Partner angebotenen One-Touch-Wählfunktionen verwenden (ohne eine Wählzeichenfolge eingeben zu müssen).

Schließlich können Sie sich mithilfe von Audio, Video und Inhaltsfreigabe mit Teams-Benutzern an Ihren Besprechungen beteiligen.