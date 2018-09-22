---
title: Einrichten von Cloud-Video-Interop für Microsoft-Teams
author: lolaj
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: srividhc
description: In diesem Artikel wird erläutert, wie Sie planen und Einrichten von Cloud-Video-Interop für Benutzer in Ihrer Organisation können.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: ff969701b9e0641ef09810f00a7aa34410e32b45
ms.sourcegitcommit: 69d1cea64425f03e562b5fb930493e27b61db96b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/21/2018
ms.locfileid: "24968283"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>Einrichten von Cloud-Video-Interop für Microsoft-Teams

Nachdem Sie [auf Ihren Partnern Cloud Video Interop ausgewählt](cloud-video-interop.md)haben, müssen Sie der Planung Ihrer Bereitstellung, Get mit provisioning Details und Partner mandantenschlüssel und Zustimmung der video Interop-App in Ihrer Organisation einrichten. Im folgende Diagramm wird das Verfahren erläutert. 

![CVI in Ihrer Organisation bereitstellen.](media/deploying-cvi.png)

## <a name="plan"></a>Planen

Informationen zum Identifizieren eines Partners oder Partner für die Verwendung in Ihrer Organisation finden Sie unter [Cloud-Video-Interop für Microsoft-Teams](cloud-video-interop.md) . 

Planen der Benutzer basierte/gleichzeitigen/Site breit-Aktivierung: 

- Wählen Sie für die Verwendung ein Bereitstellungsmodells Modell/gehostet
- Wählen Sie den Lizenz Plan ideal für Ihre Organisation. 
- Planen der Kapazität von virtuellen Maschinen ist, dass Sie Ihr video-Infrastruktur gehostet werden.

## <a name="configure"></a>Konfigurieren 

Gehen Sie folgendermaßen vor, um Cloud Video Interop zu konfigurieren. 

1. Abrufen von Konfigurationsinformationen von Partner/Partner haben Sie ausgewählte (mandantenschlüssel, AppIds...). Sie können eine oder mehrere Interop-videopartnern in Ihrer Organisation verwenden. 

2. Stellen Sie sicher, dass das Netzwerk ordnungsgemäß konfiguriert ist. Konfigurieren Sie Ihrer Standards basierende video Firewall für Perimeter Network durchqueren unterstützen. Beispiel: 
    - Cisco VCS-e                  
    - Polycom RPAD

3. Konfigurieren von integrierten Räumen mit Exchange und OTD. In den meisten Fällen zusätzliche Relay eingerichtet werden müssen und in Ihrer Umgebung konfiguriert.


## <a name="provision"></a>Bereitstellung
 
Die Mandanten-Taste wird der Client mit dem Dienst Partner sein. Im folgenden Beispiel wird die 813878896@t.plcm.vc die Mandanten-Taste. 

![Beispiel zu einem Mandanten](media/tenant-key-example.png) 

Sie müssen zum Ausführen der folgenden Cmdlets zum Bereitstellen des Mandanten-Schlüssels, und auch die Auswahl von Benutzern oder der gesamten Organisation Besprechungen mit video interop Koordinaten erstellen aktivieren.

 
- ** [Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/en-us/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft stellt vorab erstellte Richtlinien für alle unsere unterstützte Partner, mit denen Sie die Partner für video Interop Cloud zu verwendenden festlegt.

    Mit diesem Cmdlet können Sie die Überprüfung vor dem erstellten Richtlinien zu identifizieren, die Sie in Ihrer Organisation verwenden können. Sie können eine oder mehrere Benutzer mit dem Cmdlet Grant-CsTeamsVideoInteropServicePolicy nutzen diese Richtlinie zuweisen.
 
- ** [Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** Das Cmdlet Grant-CsTeamsVideoInteropServicePolicy können Sie eine vorab erstellte Richtlinie für die Verwendung in Ihrer Organisation zuweisen, oder weisen die Richtlinie auf bestimmte Benutzer.
 
- ** [Neue CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/new-csvideointeropserviceprovider):** Verwenden Sie das New-CsVideoInteropServiceProvider zum Angeben von Informationen zu unterstützten CVI Partner, dass Ihre Organisation verwenden möchten.
 
- ** [Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/set-csvideointeropserviceprovider):** Verwenden Sie das Set-CsVideoInteropServiceProvider, um Informationen zu unterstützten CVI Partner zu aktualisieren, die Ihrer Organisation verwendet werden.
 
- ** [Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/get-csvideointeropserviceprovider):** Rufen Sie alle Anbieter, die konfiguriert wurden, für die Verwendung innerhalb der Organisation.
 
- ** [Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/remove-csvideointeropserviceprovider):** Verwenden Sie Remove-CsVideoInteropServiceProvider, um alle für Anbieterinformationen zu einem Anbieter zu entfernen, die Ihre Organisation nicht mehr verwendet.  
 
## <a name="consent"></a>Zustimmung

Sie benötigen die Berechtigung Zustimmung für die Geräte für Videokonferenzen (VTCs) zur Teilnahme an Ihre Organisationen Besprechungen über die Partner-Dienst bereitstellen. Dieses Consent Link wird auch von Ihrem Partner bereitgestellt.  
 
Wenn diese Schritte abgeschlossen haben, müssen die Benutzer einzeln über das Cmdlet Grant oberhalb oder alle Benutzer in der Organisation aktiviert sind, wenn Sie der Mandanten aktiviert ist, VTC Koordinaten in alle Teams Besprechungen, die sie planen. Alle VTC kann diese über den entsprechenden Koordinaten Besprechungen teilnehmen.


|Name|Kurzbeschreibung der Anwendung die Berechtigung| Beschreibung|
|--|--|---|
|Calls.JoinGroupCall.All|Besuchen Sie Gruppe Anrufe und Besprechungen als einer app (Preview)|Die app in Ihrer Organisation, ohne dass ein angemeldeten Benutzer Gruppe Anrufe und geplante Besprechungen beitreten können.  Die app wird mit den Berechtigungen eines Benutzers Directory bei Besprechungen in Ihrem Mandanten verknüpft werden.|
|Calls.JoinGroupCallasGuest.All|Besuchen Sie Gruppe Anrufe und Besprechungen als Gast (Preview)|Die app anonym Gruppe Anrufe und geplante Besprechungen in Ihrer Organisation, ohne dass ein angemeldeten Benutzer beitreten können.  Die app wird als Gast bei Besprechungen in Ihrem Mandanten verknüpft werden.|
|Calls.AccessMedia.All|Access Mediendatenströme im Gespräch als einer app (Preview)|Ermöglicht die direkten Zugriff auf Mediendatenströme im Gespräch, ohne dass ein angemeldeten Benutzer erhalten-app.|
|OnlineMeetings.Read.All|Lesen Online-Besprechungsdetails (Preview)|Die app in Ihrer Organisation, ohne dass ein angemeldeten Benutzer Online Besprechungsdetails lesen können.|

## <a name="schedule"></a>Zeitplan

Im nächsten Schritt planen Sie Teams-Besprechung mit video interop Koordinaten. Der aktivierte Benutzer kann Teams Besprechungen über planen:
- Outlook-Client-add-in
- Teams Client Desktop- und mobilen


## <a name="join"></a>Join

Sie können Teams Besprechungen mit Ihren Geräten VTC teilnehmen, wie folgt:
 
- IVR (Interactive Voice Response)
    - Sie können mithilfe der tenantkey@domain des Partners IVR im einwählen. 
    - Sobald Sie den IVR-Partner sind, werden Sie aufgefordert, zur Eingabe der ConferenceId VTC dann Sie die Besprechung Teams eine Verbindung herstellt.
- Durchwahl
    - Sie können direkt in die Besprechung Teams einwählen, ohne Interaktion mit der Partner IVR mit der Durchwahl-Funktion unter Verwendung der vollständigen Zeichenfolge des Tenantkey. VTC ConferenceId@domain.
- One Touch-Wählplan
    - Wenn Sie eine integrierte Teams Platz haben, können Sie einem Tastendruck Dial Funktionen von Ihrem Partner (ohne Geben Sie eine beliebige Zeichenfolge Dial) verwenden.

Schließlich Engaeg mit Benutzern in Ihre Besprechungen mit der Freigabe von audio und video sowie von Teams. 