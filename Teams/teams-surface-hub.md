---
title: Bereitstellen von Microsoft-Teams für die Fläche Hub
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/04/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: Konfigurieren von Admin-Einstellungen für Microsoft-Teams für Fläche Hub.
localization_priority: Normal
search.appverid: MET150
ms.custom:
- Devices
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 485e4063c523608421955b86e0be680d5dc10b9a
ms.sourcegitcommit: 5742301cdd28e5e26107920f18e70f41b0f67cfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2018
ms.locfileid: "27132003"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a>Bereitstellen von Microsoft-Teams für die Fläche Hub
======================================

Vor der Bereitstellung von Microsoft-Teams für Microsoft Surface Hub Achten Sie darauf, dass Sie die Hardware, Betriebssystem und andere Voraussetzungen erfüllt sind. Weitere Informationen finden Sie im [Administratorhandbuch zu Microsoft Surface Hub](https://docs.microsoft.com/surface-hub/).

> [!NOTE]
> Wenn Übergang von Skype für Business Online müssen Sie bestätigen, dass eine Lizenz Microsoft-Teams, die dem Benutzer zugeordnet ist.

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>Installieren von Teams für Fläche Hub aus dem Microsoft-Speicher 

Diese Anweisungen sind für die Installation von Teams für Fläche Hub aus dem Microsoft Store. 
 
1. Starten Sie den Microsoft-Speicher:<br>
   a. Tippen Sie auf **Start** > **Alle Apps** > **Settings**.<br> b. Tippen Sie auf **Konto Fläche Hub-Gerät, Management**.<br>
   c. Tippen Sie auf der linken Seite auf der Registerkarte **Apps und -Features** .<br> d. Tippen Sie auf der rechten Seite auf die Schaltfläche **Öffnen Store** . 
2. Suchen Sie nach *Microsoft-Teams*, aus dem Microsoft Store. Die **Microsoft-Teams Fläche Hub** wird angezeigt. Tippen Sie auf die Schaltfläche **rufen Sie die app** zu installieren.  
3. Wenn die Installation abgeschlossen ist, starten Sie Fläche Hub neu. 

> [!NOTE]
> Führen Sie nicht tippen Sie auf aus dem Angebot Seite Speicher **zu starten** .

## <a name="make-teams-the-default-calling-and-meetings-application"></a>Stellen Sie die Standardeinstellung Anruf- und Besprechungen Anwendung Teams
 
Es gibt zwei Optionen für die Anruf- und Besprechungen Anwendung Standardrichtlinie konfigurieren: 

- **Option 1**: Konfigurieren von über USB-Schlüssel. 
- **Option 2**: über MDM wie Intune konfigurieren.
 
### <a name="option-1-configure-via-usb-key"></a>Option 1: Konfigurieren von über USB-Schlüssel 
 
Die Pakete finden Sie auf dieser [Seite herunterladen](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g). Wählen Sie die entsprechenden für das Paket, das Sie planen, installieren und kopieren Sie ihn in einen USB-Schlüssel. Die richtigen .ppkg-Datei verwenden, hängt die Standardrichtlinie für die Anwendung wie folgt anwenden möchten: 

|Zahl  |Beschreibung  |
|---------|---------|
|0     | Bevorzugter Skype-app auf der Startseite, Teams Besprechungen verfügbar        |
|1     | Teams bevorzugte app auf der Startseite, Skype Besprechungen verfügbar        |
|2     | Teams exklusive app auf der Startseite (Skype-app nicht verfügbar)        |
 
1. Fügen Sie den USB-Schlüssel an die Fläche Hub-Gerät. 
2. Öffnen Sie die **Einstellungen** app auf einem Gerät Fläche Hub. 
3. Öffnen Sie die **Fläche Hub Gerätemanagement Konto**.
4. Öffnen Sie die **Verwaltung von Geräten**. 
5. Klicken Sie auf **Hinzufügen oder Entfernen einer Bereitstellung Paket**. 
6. Klicken Sie auf **Paket hinzufügen**.
7. Wählen Sie aus dem Dropdown-Menü die Option **Wechselmedium** aus. 
8. Fügen Sie das entsprechende <strong>TeamsRTMMode*.ppkg</strong> -Paket, das zuvor an den USB-Schlüssel kopiert wurde. 
9. Starten Sie das Fläche Hub-Gerät neu. 
10. Nach dem Neustart des Geräts, sollten Sie möglicherweise die Teams app aus dem Bildschirm Start starten und teilnehmen an einer Besprechung aus dem Kalender. 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>Option 2: Konfigurieren von über MDM wie Intune 

Verwenden Sie Folgendes, um die Anruf- und Besprechungen Anwendung Standardrichtlinie über Intune konfigurieren. Siehe auch im Blog [der Microsoft-Teams für Fläche Hub-app mit Intune Bereitstellen](https://blogs.technet.microsoft.com/y0av/2018/07/16/97/).

|Einstellung   |Wert    |Beschreibung    |
|----------|---------|---------|
| Path      | ./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|Datentyp | Ganzzahl (0-2)   |0 – bevorzugte Skype-app auf der Startseite, Teams Besprechungen verfügbar<br>1 – Teams bevorzugte app auf der Startseite, Skype Besprechungen verfügbar<br>2 - Teams exklusive app auf der Startseite (Skype-app nicht verfügbar) |
|Betrieb| Abrufen, festlegen        |

|Einstellung   |Wert    |
|----------|---------|
| Path      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|Datentyp | String - Set-Zeichenfolge, die Teams Anwendungspaket-ID als **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe! Teams** |
|Betrieb| Abrufen, festlegen        |

Starten Sie das Fläche Hub-Gerät neu. Nach dem Neustart des Geräts, sollten Sie möglicherweise die Teams app aus dem Bildschirm Start starten und teilnehmen an einer Besprechung aus dem Kalender.

