---
title: Bereitstellen von Microsoft Teams für Surface Hub
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/04/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: Erfahren Sie, wie Sie die App Teams für Surface Hub installieren und konfigurieren, sodass Teams die Standardanwendung für Anrufe und Besprechungen ist.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Devices
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 38202fcbb4c2147baae3f745bc2455da6fdff3e3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093935"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a>Bereitstellen von Microsoft Teams für Surface Hub
======================================

Bevor Sie Teams für Surface Hub installieren, sollten Sie unbedingt die folgenden Schritte ausführen:

 □ Stellen Sie sicher, dass Hardware-, Betriebssystem- und andere Anforderungen erfüllt sind. Weitere Informationen finden Sie im [Microsoft Surface Hub-Administratorhandbuch](/surface-hub/).<br>
 Stellen Sie sicher, dass das für Teams mindestens erforderliche Betriebssystemupdate installiert ist – [KB4343889](https://support.microsoft.com/help/4343889).<br>
 □ Weisen Sie dem Hub-Gerätekonto eine Teams-Lizenz zu.<br>
 □ Wenn Sie von Skype for Business Online wechseln, vergewissern Sie sich, dass dem Benutzer eine Teams-Lizenz zugewiesen ist.

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>Installieren von Teams für Surface Hub aus dem Microsoft Store 

Diese Anleitung bezieht sich auf die Installation von Teams für Surface Hub aus dem Microsoft Store. 
 
1. Öffnen Sie den Microsoft Store:<br>
   a. Tippen Sie auf **Start** > **Alle Anwendungen** > **Einstellungen**.<br> b. Tippen Sie auf **Surface Hub-Gerätekonto, Verwaltung**.<br>
   c. Tippen Sie auf der linken Seite auf die Registerkarte **Apps und Features**.<br> d. Tippen Sie auf der rechten Seite auf die Schaltfläche **Store öffnen**. 
2. Suchen Sie *Microsoft Teams* im Microsoft Store. **Microsoft Teams für Surface Hub** wird angezeigt. Tippen Sie zum Installieren auf die Schaltfläche **App abrufen**.  
3. Wenn die Installation abgeschlossen ist, starten Sie den Surface Hub neu. 

> [!NOTE]
> Tippen Sie nicht auf der Seite des Store-Eintrags auf **Starten**.

## <a name="make-teams-the-default-calling-and-meetings-application"></a>Festlegen von Teams als Standardanwendung für Anrufe und Besprechungen
 
Es gibt zwei Möglichkeiten der Konfiguration der Standardanwendungsrichtlinie für Anrufe und Besprechungen: 

- **Option 1**: Konfigurieren über USB-Stick. 
- **Option 2**: Konfigurieren über MDM z. B. Intune.
 
### <a name="option-1-configure-via-usb-key"></a>Option 1: Konfigurieren über USB-Stick 
 
Die Pakete befinden sich auf dieser [Downloadseite](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g). Wählen Sie das passende Paket, das Sie installieren möchten, und kopieren Sie es auf einen USB-Stick. Welche PPKG-Datei die richtige ist, hängt von der zu verwendenden Standardanwendungsrichtlinie ab: 

|Nummer  |Beschreibung  |
|---------|---------|
|0     | Skype als bevorzugte App auf dem Startbildschirm, Teams-Besprechungen verfügbar        |
|1     | Teams als bevorzugte App auf dem Startbildschirm, Skype-Besprechungen verfügbar        |
|2     | Teams als exklusive App auf dem Startbildschirm (Skype-App nicht verfügbar)        |
 
1. Schließen Sie den USB-Stick an das Surface Hub-Gerät an. 
2. Öffnen Sie die **Einstellungen**-App auf einem Surface Hub-Gerät. 
3. Öffnen Sie **Surface Hub-Gerätekonto, Verwaltung**.
4. Öffnen Sie **Geräteverwaltung**. 
5. Klicken Sie auf **Bereitstellungspaket hinzufügen oder entfernen**. 
6. Klicken Sie auf **Paket hinzufügen**.
7. Wählen Sie die Option **Wechselmedien** aus dem Dropdown-Menü aus. 
8. Fügen Sie das entsprechende <strong>TeamsRTMMode*.ppkg</strong>-Paket hinzu, das zuvor auf den USB-Stick kopiert wurde. 
9. Starten Sie das Surface Hub-Gerät neu. 
10. Nach dem Neustart des Geräts sollten Sie die Teams-App über den Startbildschirm starten und über den Kalender an einer Besprechung teilnehmen können. 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>Option 2: Konfigurieren über MDM z. B. Intune 

Verwenden Sie die folgenden Schritte, um die Standardanwendungsrichtlinie für Anrufe und Besprechungen über Intune zu konfigurieren. Außerdem finden Sie weitere Informationen im Blogbeitrag [Bereitstellen der Microsoft Teams für Surface Hub-App mit Intune](https://y0av.me/2018/07/16/deploy-the-microsoft-teams-for-surface-hub-app-using-intune/).

|Einstellung   |Wert    |Beschreibung    |
|----------|---------|---------|
|Pfad      | ./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|Datentyp | Ganze Zahl (0-2)   |0: Skype als bevorzugte App auf dem Startbildschirm, Teams-Besprechungen verfügbar<br>1: Teams als bevorzugte App auf dem Startbildschirm, Skype-Besprechungen verfügbar<br>2: Teams als exklusive App auf dem Startbildschirm (Skype-App nicht verfügbar) |
|Vorgänge| Abrufen, Einrichten        |

|Einstellung   |Wert    |
|----------|---------|
|Pfad      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|Datentyp | String: Teams-Anwendungspaket-ID wird auf **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams** festgelegt |
|Vorgänge| Abrufen, Einrichten        |

Starten Sie das Surface Hub-Gerät neu. Nach dem Neustart des Geräts sollten Sie die Teams-App über den Startbildschirm starten und über den Kalender an einer Besprechung teilnehmen können.