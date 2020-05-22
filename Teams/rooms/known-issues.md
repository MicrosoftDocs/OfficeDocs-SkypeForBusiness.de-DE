---
title: Bekannte Probleme
ms.author: v-lanac
author: lanachin
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
description: Der Administrator kann eine Liste der bekannten Probleme in Microsoft Teams-Räumen kennenlernen, einschließlich Update, Benutzeroberfläche, Hardware sowie Einschränkungen und erwarteten Verhaltensweisen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e3cb46ed1ca3fde81f301ec6c2f2f8620452b389
ms.sourcegitcommit: f63cf7fdde333a7cb36c39e9b6cdc33afd2b4601
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "44338225"
---
# <a name="known-issues"></a>Bekannte Probleme 
 
Dieser Artikel führt die bekannten Probleme für Microsoft Teams Rooms nach Funktionsbereichen auf.
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>Aktualisieren 

| Problemtitel |  Verhalten \/ Symptom | Bekannte Problemumgehung | KB-Artikel |
|  ---        |      ---             |   ---            | --- |
|  App nicht mehr aktuell         |    Die Microsoft Teams Rooms-Konsole zeigt einen Fehler des Typs „Systemkonfiguration abgelaufen“ an.                |   [Verwenden Sie das Wiederherstellungstools für Microsoft Teams Rooms](recovery-tool.md)             |  Keine |
|  Gerät auf nicht unterstützte Version von Windows 10 aktualisiert   |    Das Windows 10-Gerät wurde von Version 1803 auf Version 1809 aktualisiert, was nicht unterstützt wird. Die unterstützte Version ist 1903. |   Dies kann geschehen, wenn die Einstellung ["Gruppenrichtlinie" oder "MDM-Einstellung für DeferFeatureUpdatesPeriodinDays](https://docs.microsoft.com/windows/deployment/update/waas-configure-wufb) ", mit der Sie die Funktionsupdates für eine bestimmte Anzahl von Tagen verzögern können, auf den Höchstwert von 365 Tage festgelegt ist. <br><br> Windows 10, Version 1809, wird in Microsoft Teams-Räumen nicht unterstützt, während Version 1903 unterstützt wird. Ab dem 27. März 2020 ist Version 1809 jedoch mehr als 365 Tage alt. Wenn diese Einstellung nicht geändert wird, versucht Windows, Version 1809 zu installieren, was zu Problemen mit Microsoft Teams-Räumen führen kann.<br><br>Um dieses Problem zu vermeiden, **Entfernen Sie** alle Gruppenrichtlinien-oder MDM-Einstellungen, um Aktualisierungen zu verzögern. Dadurch kann Windows auf die neueste, unterstützte Betriebssystemversion aktualisieren. <br><br>**Wichtig** Die Gruppenrichtlinien-oder MDM-Einstellung muss **entfernt** (Links nicht konfiguriert) und **nicht auf 0 festgelegt**werden. Wenn die Richtlinie auf "0" gesetzt ist, übernimmt Windows die neueste verfügbare Version, die möglicherweise nicht unterstützt wird. |  Keine |
| Anwendung wird nicht gestartet |  Nach dem Update auf die Anwendungsversion 4.4.41.0 bootet das System auf den schwarzen Bildschirm, wo es möglicherweise hängen bleibt, oder wechseln Sie nach einigen Minuten zum Anmeldebildschirm. | Befolgen Sie die Schritte in [Microsoft Teams rooms-Anwendung startet nicht nach dem Update auf Version 4.4.41.0](https://docs.microsoft.com/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update) , um dieses Problem zu beheben.  | Keine |


<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>Benutzeroberfläche 

| Problemtitel |  Verhalten \/ Symptom | Bekannte Problemumgehung | KB-Artikel |
|  ---        |      ---             |   ---            | --- |
|Virtuelle Tastatur fehlt   | Die virtuelle Tastatur wird nicht angezeigt, wenn Sie Informationen in Microsoft Teams Rooms eingeben müssen. Dieses Problem tritt in Windows 10, Version 1903, auf. | Installieren Sie 2020-04 Kumulatives Update für Windows 10, Version 1903 für x64-basierte Systeme, mithilfe von Windows-Updates.  | Keine | 

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

Wenn Sie möchten, dass ein Front-Room-Display automatisch zu einer aktiven Videoquelle (wie einer MTR-Konsole) wechselt, wenn die Quelle aus dem Standbymodus aktiviert wird, müssen bestimmte Bedingungen erfüllt sein. Dieses Feature ist optional, wird aber von der Microsoft Teams Rooms-Software unterstützt, sofern die zugrunde liegende Hardware das Feature unterstützt. Ein Consumer-Fernsehgerät, das als Front-of-room-Display verwendet wird, muss die Funktion Consumer Electronics Control (CEC) von HDMI unterstützen.  Je nachdem, welches Dock oder welche Konsole ausgewählt wurde (das CEC möglicherweise nicht unterstützt, lesen Sie die Dokumentation zum Hersteller Support), kann ein Arbeitsbereichs Controller wie eine [newtron HD CTL 100](https://www.extron.com/article/hdctl100ad) benötigt werden, um das gewünschte Verhalten zu ermöglichen. 

***

Verwenden Sie immer eine verkabelte 1-Gbit/s-Netzwerkverbindung, um sicherzustellen, dass Sie die erforderliche Bandbreite aufweisen. 

***

Wenn Ihr Microsoft Teams rooms-Gerät die Vertrauensstellung für die Domäne verliert, können Sie sich nicht mehr bei dem Gerät authentifizieren und Einstellungen öffnen. Wenn Sie beispielsweise die Microsoft Teams-Räume aus der Domäne entfernen, nachdem Sie der Domäne beigetreten sind, geht die Vertrauensstellung verloren. Die Lösung ist, sich mit dem lokalen Administratorkonto anzumelden. 
***
Microsoft Teams Rooms ist eine Multi-Window-Anwendung und erfordert ein Front-Room-Display, das mit dem HDMI-Anschluss des Geräts verbunden werden muss, damit die APP ordnungsgemäß funktioniert. Stellen Sie sicher, dass Sie entweder ein HDMI-Display angeschlossen haben oder einen Dummy-HDMI-Stecker verwenden, wenn Sie testen und noch kein Display gekauft haben.
***
<a name="See"> </a>  
## <a name="see-also"></a>Siehe auch

[Microsoft Teams Rooms-Hilfe](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams Rooms verwalten](rooms-manage.md)
