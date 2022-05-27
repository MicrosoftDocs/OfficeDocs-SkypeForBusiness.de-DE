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
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1b76e7c5e79b3928c7fb19ad9c5f5fb8f241b29a
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674737"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>Einrichten von Cloud-Video-Interoperabilität für Microsoft Teams

Nachdem Sie [Ihre Cloud Video Interop-Partner ausgewählt](cloud-video-interop.md) haben, müssen Sie Ihre Bereitstellung planen, sich mit Bereitstellungsdetails und Partnermandantenschlüsseln einrichten und der Video-Interoperabilitäts-App in Ihrer Organisation zustimmen. Das folgende Diagramm beschreibt den Prozess.

![Bereitstellen von CVI in Ihrer Organisation.](media/deploying-cvi.png)

## <a name="plan"></a>Plan

Unter [Cloud Video Interop finden Sie Microsoft Teams](cloud-video-interop.md), um Informationen zum Identifizieren eines partners oder eines Partners zu finden, der in Ihrer Organisation verwendet werden soll.

So planen Sie die benutzerbasierte/gleichzeitige/standortweite Aktivierung:

- Wählen Sie ein Bereitstellungsmodell/gehostetes Modell für Ihre Verwendung aus.
- Wählen Sie den idealen Lizenzplan für Ihre Organisation aus.
- Planen Sie die Kapazität von VMs, wenn Sie Ihre Videoinfrastruktur hosten.

## <a name="configure"></a>Konfigurieren

Führen Sie die folgenden Schritte aus, um Cloud Video Interop zu konfigurieren.

1. Rufen Sie Konfigurationsinformationen von den ausgewählten Partnern ab (Mandantenschlüssel, appIds...). Sie können einen oder mehrere Video-Interoperabilitätspartner in Ihrer Organisation verwenden.

2. Stellen Sie sicher, dass Ihr Netzwerk ordnungsgemäß konfiguriert ist. Konfigurieren Sie Ihre standardbasierte Videofirewall für die Umkreisnetzwerk-Traversal, um sie zu unterstützen. Zum Beispiel: 
    - Cisco VCS-e
    - Polycom RPAD

3. Konfigurieren sie integrierte Räume mit Exchange und OTD. In den meisten Fällen müsste zusätzliches Relay in Ihrer Umgebung eingerichtet und konfiguriert werden.

## <a name="provision"></a>Bereitstellung

Der Mandantenschlüssel ist die Auswahl an den Partnerdienst. Im folgenden Beispiel ist 813878896@t.plcm.vc der Mandantenschlüssel.

![Mandantenschlüsselbeispiel.](media/tenant-key-example.png)

Sie müssen die folgenden Cmdlets ausführen, um den Mandantenschlüssel bereitzustellen, und auch ausgewählte Benutzer oder Ihre gesamte Organisation zum Erstellen von Besprechungen mit Video-Interoperabilitätskoordinaten aktivieren.

- **[Get-CsTeamsVideoInteropServicepolicy](/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft stellt vordefinierte Richtlinien für jeden unserer unterstützten Partner bereit, mit denen Sie festlegen können, welche Partner für die Cloud-Video-Interoperabilität verwendet werden sollen.

    Mit diesem Cmdlet können Sie die vordefinierten Richtlinien identifizieren, die Sie in Ihrer Organisation verwenden können. Sie können diese Richtlinie einem oder mehreren Ihrer Benutzer zuweisen, die das cmdlet Grant-CsTeamsVideoInteropServicePolicy verwenden.

- **[Grant-CsTeamsVideoInteropServicePolicy](/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** Mit dem cmdlet Grant-CsTeamsVideoInteropServicePolicy können Sie eine vordefinierte Richtlinie für die Verwendung in Ihrer Organisation zuweisen oder die Richtlinie bestimmten Benutzern zuweisen.

- **[New-CsVideoInteropServiceProvider](/powershell/module/skype/new-csvideointeropserviceprovider):** Verwenden Sie die New-CsVideoInteropServiceProvider, um Informationen zu einem unterstützten CVI-Partner anzugeben, den Ihre Organisation verwenden möchte.

- **[Set-CsVideoInteropServiceProvider](/powershell/module/skype/set-csvideointeropserviceprovider):** Verwenden Sie die Set-CsVideoInteropServiceProvider, um Informationen zu einem unterstützten CVI-Partner zu aktualisieren, den Ihre Organisation verwendet.

- **[Get-CsVideoInteropServiceProvider](/powershell/module/skype/get-csvideointeropserviceprovider):** Rufen Sie alle Anbieter ab, die für die Verwendung innerhalb der Organisation konfiguriert wurden.

- **[Remove-CsVideoInteropServiceProvider](/powershell/module/skype/remove-csvideointeropserviceprovider):** Verwenden Sie Remove-CsVideoInteropServiceProvider, um alle Anbieterinformationen zu einem Anbieter zu entfernen, den Ihre Organisation nicht mehr verwendet.

## <a name="consent"></a>Zustimmung

Sie müssen die Zustimmung für die Videotelekonferenzgeräte (Video Teleconferencing Devices, VTCs) erteilen, um über den Partnerdienst an Besprechungen Ihrer Organisation teilzunehmen. Dieser Einwilligungslink wird auch von Ihrem Partner bereitgestellt.

Wenn diese Schritte abgeschlossen sind, verfügen die Benutzer, die über das oben genannte Cmdlet "Gewähren" einzeln aktiviert sind, oder alle Benutzer in der Organisation, wenn der Mandant aktiviert ist, über VTC-Koordinaten in allen Teams Besprechungen, die sie planen. Jeder VTC kann über diese Koordinaten an diesen Besprechungen teilnehmen.

|Name|Kurzbeschreibung der Anwendungsberechtigung| Beschreibung|
|---|---|---|
|Calls.JoinGroupCall.All|Teilnehmen an Gruppenanrufen und Besprechungen als App (Vorschau)|Ermöglicht der App, an Gruppenanrufen und geplanten Besprechungen in Ihrer Organisation teilzunehmen, ohne dass ein Benutzer angemeldet ist.  Die App wird mit den Berechtigungen eines Verzeichnisbenutzers zu Besprechungen in Ihrem Mandanten hinzugefügt.|
|Calls.JoinGroupCallasGuest.All|Teilnehmen an Gruppenanrufen und Besprechungen als Gastbenutzer (Vorschau)|Ermöglicht der App, anonym an Gruppenanrufen und geplanten Besprechungen in Ihrer Organisation teilzunehmen, ohne dass ein Benutzer angemeldet ist.  Die App wird als Gast zu Besprechungen in Ihrem Mandanten hinzugefügt.|
|Calls.AccessMedia.All|Zugreifen auf Mediendatenströme in einem Anruf als App (Vorschau)|Ermöglicht der App, direkten Zugriff auf Mediendatenströme in einem Anruf zu erhalten, ohne dass ein Benutzer angemeldet ist.|
|OnlineMeetings.Read.All|Lesen von Onlinebesprechungsdetails (Vorschau)|Ermöglicht der App, Onlinebesprechungsdetails in Ihrer Organisation zu lesen, ohne dass ein Benutzer angemeldet ist.|

## <a name="schedule"></a>Zeitplan

Planen Sie als Nächstes Teams Besprechung mit Video-Interoperabilitätskoordinaten. Der aktivierte Benutzer kann Teams-Besprechungen planen über:

- [Teams Besprechungs-Add-In für Outlook](teams-add-in-for-outlook.md)
- Teams clientdesktop und mobil

## <a name="join"></a>Join

Sie können auf folgende Weise an Teams Besprechungen mit Ihren VTC-Geräten teilnehmen:

- IVR (Interaktive Sprachantwort)
  - Sie können sich mithilfe der tenantkey@domain beim IVR des Partners einwählen.
  - Sobald Sie sich im Partner-IVR befinden, werden Sie aufgefordert, die VTC conferenceId einzugeben, die Sie dann mit der Teams Besprechung verbindet.
- Direktwahl
  - Sie können sich direkt in die Teams Besprechung einwählen, ohne mit dem IVR des Partners zu interagieren, indem Sie die Direktwahlfunktion mithilfe der vollständigen Mandantenschlüsselzeichenfolge verwenden. VTC-ConferenceId@domain.
- 1-Touch-Wählhilfe
  - Wenn Sie über einen integrierten Teams Raum verfügen, können Sie die 1-Finger-Wählfunktionen Ihres Partners verwenden (ohne eine Wählzeichenfolge eingeben zu müssen).

Wenden Sie sich schließlich mit Teams Benutzern in Ihren Besprechungen über Audio-, Video- und Inhaltsfreigaben an.
