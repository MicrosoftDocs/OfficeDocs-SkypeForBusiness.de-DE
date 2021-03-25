---
title: Bekannte Probleme
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Der Administrator kann sich über eine Liste bekannter Probleme für Microsoft Teams Rooms informieren, einschließlich Update, Benutzeroberfläche, Hardware sowie Einschränkungen und erwartetes Verhalten.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 02e7d2411fa1d8a86fe20dcab3013be758f22a21
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117533"
---
# <a name="known-issues"></a>Bekannte Probleme 
 
Dieser Artikel führt die bekannten Probleme für Microsoft Teams Rooms nach Funktionsbereichen auf.
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>Aktualisieren 

| Problemtitel |  Verhalten \/ Symptom | Bekannte Problemumgehung | KB-Artikel |
|  ---        |      ---             |   ---            | --- |
| Anwendung wird nicht gestartet |  Nach dem Update auf Anwendungsversion 4.4.41.0 startet das System auf den schwarzen Bildschirm, oder wechseln Sie nach einigen Minuten zum Anmeldebildschirm. | Führen Sie die Schritte in Der Microsoft Teams Rooms-Anwendung wird nach dem Update auf [Version 4.4.41.0](/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update) nicht gestartet, um dieses Problem zu beheben.  | Keine |
|  Die Inhaltsfreigabe von SfB-Besprechungen wird nicht im Vollbildmodus angezeigt         |    In Skype for Business-Besprechungen kann es bei Räumen mit Vorraumanzeigen mit Hohen DPI-Einstellungen zu Problemen mit Inhalten, die in einer Besprechung freigegeben wurden, nicht im Vollbildmodus auf der Vorderseite des Chatraums angezeigt werden. Dies wird durch ein zugrunde liegendes Problem in der Windows 10 Remote Desktop Protocol (RDP)-API verursacht. | Verwenden Sie die `<WinRTRdpEnabled>` XML-Einstellung, um die Windows 10 RDP-API zu deaktivieren, um dieses Problem zu beheben. Zum Deaktivieren müssen Sie den Wert als `false` angeben. Weitere Informationen finden Sie unter [Verwalten von Konsoleneinstellungen mit einer XML-Konfigurationsdatei.](xml-config-file.md#manage-console-settings-with-an-xml-configuration-file) | Keine |
|  App nicht mehr aktuell         |    Die Microsoft Teams Rooms-Konsole zeigt einen Fehler des Typs „Systemkonfiguration abgelaufen“ an.                |   [Verwenden Sie das Wiederherstellungstools für Microsoft Teams Rooms](recovery-tool.md)             |  Keine |
|  Gerät auf nicht unterstützte Version von Windows 10 aktualisiert   |    Windows 10-Gerät wurde von Version 1803 auf Version 1809 aktualisiert, was nicht unterstützt wird. Die unterstützte Version ist 1903. |   Dies kann geschehen, wenn die Einstellung Gruppenrichtlinie oder MDM für [DeferFeatureUpdatesPeriodinDays,](/windows/deployment/update/waas-configure-wufb) mit der Sie Featureupdates für eine bestimmte Anzahl von Tagen zurückdingen können, auf maximal 365 Tage festgelegt ist. <br><br> Windows 10 Version 1809 wird in Microsoft Teams Rooms nicht unterstützt, während Version 1903 unterstützt wird. Ab dem 27. März 2020 ist Version 1809 jedoch mehr als 365 Tage alt. Wenn diese Einstellung nicht geändert wird, versucht Windows, Version 1809 zu installieren, was zu Problemen mit Microsoft Teams Rooms führen kann.<br><br>Um diese Situation zu vermeiden, **entfernen Sie** alle Gruppenrichtlinien- oder MDM-Einstellungen zum Zurückdringen von Updates. Dadurch kann Windows auf die neueste, unterstützte Betriebssystemversion aktualisieren. <br><br>**WICHTIG** Die Einstellung Gruppenrichtlinie oder MDM muss **entfernt** werden (links nicht konfiguriert) und nicht **auf 0 festgelegt werden.** Wenn die Richtlinie auf 0 festgelegt ist, verwendet Windows die neueste verfügbare Version, die möglicherweise nicht unterstützt wird. |  Keine |



<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>Benutzeroberfläche 

| Problemtitel |  Verhalten \/ Symptom | Bekannte Problemumgehung | KB-Artikel |
|  ---        |      ---             |   ---            | --- |
|Virtuelle Tastatur fehlt   | Die virtuelle Tastatur wird nicht angezeigt, wenn Sie Informationen in Microsoft Teams Rooms eingeben müssen. Dieses Problem tritt in Windows 10, Version 1903, auf. | Installieren Sie das kumulative Update 2020-04 für Windows 10, Version 1903 für x64-basierte Systeme über Windows-Updates.  | Keine | 

<a name="Hardware"> </a>  
## <a name="hardware"></a>Hardware

| Problemtitel |  Verhalten \/ Symptom | Bekannte Problemumgehung | KB-Artikel |
|  ---        |      ---             |   ---            |   --- |
| Monitore nicht erkannt | Wenn Sie Microsoft Teams Rooms auf einem Surface Pro-Gerät (Modell 2017) ausführen, werden Monitore nicht erkannt. |  Halten Sie den Surface Pro Power-Netzschalter mindestens 20 Sekunden lang gedrückt. Wenn Sie dies tun, wird das Gerät neu gestartet und löscht den Grafik-Cache. |[KB4055681](https://support.microsoft.com/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>Einschränkungen und erwartetes Verhalten

***

Microsoft Teams Rooms unterstützt keine HDCP-Eingabe. Von dieser ist bekannt, dass sie Probleme mit der HDMI-Erfassungsfunktion (Video, Audio) verursacht. Stellen Sie sicher, dass die HDCP-Optionen der mit Microsoft Teams Rooms verbundenen Switches deaktiviert sind. 

***

Wenn Sie möchten, dass eine Anzeige vor dem Raum automatisch zu einer aktiven Videoquelle (z. B. einer MTR-Konsole) wechselt, wenn die Quelle aus dem Standbymodus aktiviert wird, müssen bestimmte Bedingungen erfüllt sein. Dieses Feature ist optional, wird aber von der Microsoft Teams Rooms-Software unterstützt, vorausgesetzt, die zugrunde liegende Hardware unterstützt das Feature. Ein Verbraucher-TV, das als Bildschirm vor dem Raum verwendet wird, muss das Feature Consumer Electronics Control (CEC) von HDMI unterstützen.  Je nach ausgewähltem Dock oder der ausgewählten Konsole (die CEC möglicherweise nicht unterstützt, lesen Sie die Dokumentation zum Herstellersupport), ist möglicherweise ein Controller wie [ein HD-TX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) von Crestron oder [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) von Extron erforderlich, um das gewünschte Verhalten zu ermöglichen. 

***

Verwenden Sie immer eine kabelgebundene 1-Gbit/s-Netzwerkverbindung, um sicherzustellen, dass Sie über die erforderliche Bandbreite verfügen. 

***

Wenn Ihr Microsoft Teams Rooms-Gerät das Vertrauen in die Domäne verliert, können Sie sich nicht beim Gerät authentifizieren und Einstellungen öffnen. Wenn Sie beispielsweise die Microsoft Teams-Räume aus der Domäne entfernen, nachdem sie der Domäne beigetreten ist, geht die Vertrauensstellung verloren. Die Lösung ist, sich mit dem lokalen Administratorkonto anzumelden. 
***
Microsoft Teams Rooms ist eine Mehrfensteranwendung und erfordert eine Anzeige vor dem Raum, um mit dem HDMI-Port des Geräts verbunden zu sein, damit die App ordnungsgemäß funktioniert. Stellen Sie sicher, dass entweder ein HDMI-Display angeschlossen ist, oder verwenden Sie einen Dummy-HDMI-Stecker, wenn Sie testen und noch kein Display gekauft haben.
***
<a name="See"> </a>  
## <a name="see-also"></a>Siehe auch

[Microsoft Teams Rooms-Hilfe](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams Rooms verwalten](rooms-manage.md)