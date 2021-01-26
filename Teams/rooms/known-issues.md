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
description: Der Administrator kann sich über eine Liste bekannter Probleme für Microsoft Teams-Räume informieren, einschließlich Update, Benutzeroberfläche, Hardware, Einschränkungen und erwartetem Verhalten.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: afa1bf4a2a4fdd36bd45d8b237998ec461dcc1f4
ms.sourcegitcommit: ab566ddab9d26440bac1716a975f30e075d0c7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865239"
---
# <a name="known-issues"></a>Bekannte Probleme 
 
Dieser Artikel führt die bekannten Probleme für Microsoft Teams Rooms nach Funktionsbereichen auf.
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>Aktualisieren 

| Problemtitel |  Verhalten \/ Symptom | Bekannte Problemumgehung | KB-Artikel |
|  ---        |      ---             |   ---            | --- |
| Anwendung wird nicht gestartet |  Nach dem Update auf Anwendungsversion 4.4.41.0 wird das System auf einen schwarzen Bildschirm gestartet, oder wechseln Sie nach einigen Minuten zum Anmeldebildschirm. | Führen Sie die Schritte in microsoft Teams Rooms aus, die nach dem Update auf [Version 4.4.41.0](https://docs.microsoft.com/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update) nicht gestartet werden, um dieses Problem zu beheben.  | Keine |
|  Die Inhaltsfreigabe für SfB-Besprechungen wird nicht im Vollbildmodus angezeigt         |    In Skype for Business-Besprechungen können probleme auftreten, wenn für In-Besprechungsinhalte, die in einer Besprechung freigegeben wurden, der Vollbildmodus auf der Anzeige vor dem Raum angezeigt wird. Dies wird durch ein zugrunde liegendes Problem in der RDP-API (Remote Desktop Protocol) von Windows 10 verursacht. | Verwenden Sie die `<WinRTRdpEnabled>` XML-Einstellung, um die Windows 10 RDP-API zu deaktivieren, um dieses Problem zu beheben. Zum Deaktivieren müssen Sie den Wert als `false` angeben. Weitere Informationen finden Sie unter Verwalten [von Konsoleneinstellungen mit einer XML-Konfigurationsdatei.](xml-config-file.md#manage-console-settings-with-an-xml-configuration-file) | Keine |
|  App nicht mehr aktuell         |    Die Microsoft Teams Rooms-Konsole zeigt einen Fehler des Typs „Systemkonfiguration abgelaufen“ an.                |   [Verwenden Sie das Wiederherstellungstools für Microsoft Teams Rooms](recovery-tool.md)             |  Keine |
|  Gerät auf nicht unterstützte Version von Windows 10 aktualisiert   |    Windows 10-Gerät wurde von Version 1803 auf Version 1809 aktualisiert, was nicht unterstützt wird. Die unterstützte Version ist 1903. |   Dies kann geschehen, wenn die Einstellung "Gruppenrichtlinie" oder "MDM" für die Einstellung ["DeferFeatureUpdatesPeriodinDays",](https://docs.microsoft.com/windows/deployment/update/waas-configure-wufb) mit der Sie Featureupdates für eine bestimmte Anzahl von Tagen zurück stellen können, auf den Höchstwert von 365 Tagen festgelegt ist. <br><br> Windows 10 Version 1809 wird von Microsoft Teams Rooms nicht unterstützt, während Version 1903 unterstützt wird. Ab dem 27. März 2020 ist Version 1809 jedoch mehr als 365 Tage alt. Wenn diese Einstellung nicht geändert wird, versucht Windows, Version 1809 zu installieren, was zu Problemen mit Microsoft Teams Rooms führen kann.<br><br>Um diese Situation zu vermeiden, **entfernen** Sie alle Gruppenrichtlinien- oder MDM-Einstellungen zum Zurückdringen von Updates. Dadurch kann Windows auf die neueste, unterstützte Betriebssystemversion aktualisieren. <br><br>**WICHTIG** Die Gruppenrichtlinie- oder MDM-Einstellung muss **entfernt** (links nicht konfiguriert) und nicht auf **"0" festgelegt werden.** Wenn die Richtlinie auf 0 festgelegt ist, verwendet Windows die neueste verfügbare Version, die möglicherweise nicht unterstützt wird. |  Keine |
|  Cisco Room-Geräte können nicht an Einer Besprechung in Teams teilnehmen   |    Die Teilnahme an einer Teams-Besprechung über die direkte Gasteinwahl über ein Cisco Room-Gerät schlägt fehl und der Anruf endet, nachdem ein Benutzer "Teilnehmen" **ausgewählt hat.** |  Eine Änderung im Teams-Webclient, die Cisco Room-Geräten die Teilnahme an Teambesprechungen ermöglicht, hat diese Regression verursacht. Wir veröffentlichen eine Lösung für dieses Problem, die bis zum 15.01.2020 für alle Mandanten bereitgestellt wird. Cisco und Microsoft arbeiten zusammen, um ähnliche Probleme in Zukunft zu vermeiden.   |  Keine |


<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>Benutzeroberfläche 

| Problemtitel |  Verhalten \/ Symptom | Bekannte Problemumgehung | KB-Artikel |
|  ---        |      ---             |   ---            | --- |
|Virtuelle Tastatur fehlt   | Die virtuelle Tastatur wird nicht angezeigt, wenn Sie Informationen in Microsoft Teams Rooms eingeben müssen. Dieses Problem tritt in Windows 10, Version 1903, auf. | Installieren Sie das kumulative Update 2020-04 für Windows 10, Version 1903 für x64-basierte Systeme über Windows Updates.  | Keine | 

<a name="Hardware"> </a>  
## <a name="hardware"></a>Hardware

| Problemtitel |  Verhalten \/ Symptom | Bekannte Problemumgehung | KB-Artikel |
|  ---        |      ---             |   ---            |   --- |
| Monitore nicht erkannt | Wenn Sie Microsoft Teams Rooms auf einem Surface Pro-Gerät (Modell 2017) ausführen, werden Monitore nicht erkannt. |  Halten Sie den Surface Pro Power-Netzschalter mindestens 20 Sekunden lang gedrückt. Wenn Sie dies tun, wird das Gerät neu gestartet und löscht den Grafik-Cache. |[KB4055681](https://support.microsoft.com/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>Einschränkungen und erwartetes Verhalten

**_

Microsoft Teams Rooms unterstützt keine HDCP-Eingabe. Von dieser ist bekannt, dass sie Probleme mit der HDMI-Erfassungsfunktion (Video, Audio) verursacht. Stellen Sie sicher, dass die HDCP-Optionen der mit Microsoft Teams Rooms verbundenen Switches deaktiviert sind. 

_*_

Wenn Sie möchten, dass die Anzeige vor dem Raum automatisch zu einer aktiven Videoquelle (z. B. einer MTR-Konsole) wechselt, wenn die Quelle aus dem Standbymodus reaktiviert wird, müssen bestimmte Bedingungen erfüllt sein. Dieses Feature ist optional, wird aber von der Microsoft Teams -Räume-Software unterstützt, sofern zugrunde liegende Hardware das Feature unterstützt. Ein Consumer-TV, das als Anzeige vor dem Raum verwendet wird, muss die Consumer Electronic Control (CEC)-Funktion von HDMI unterstützen.  Je nach ausgewählter #A0 oder Konsole (die CEC möglicherweise nicht unterstützt, finden Sie in der Supportdokumentation des Herstellers) kann ein Controller wie [HD-COMMERCE-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) von Crestron oder [Ex um die HD CTL 100](https://www.extron.com/article/hdctl100ad) von Ex während der #A1 erforderlich sein, um das gewünschte Verhalten zu ermöglichen. 

_*_

Verwenden Sie immer eine verkabelte 1-GBit/s-Netzwerkverbindung, um sicherzustellen, dass Sie über die erforderliche Bandbreite verfügen. 

_*_

Wenn Ihr Microsoft Teams -Räume-Gerät das Vertrauen in die Domäne verliert, können Sie sich nicht mehr beim Gerät authentifizieren und die Einstellungen öffnen. Wenn Sie beispielsweise die Microsoft Teams Rooms aus der Domäne entfernen, nachdem sie der Domäne beigetreten ist, geht die Vertrauensstellung verloren. Die Lösung ist, sich mit dem lokalen Administratorkonto anzumelden. 
_*_ Microsoft Teams Rooms ist eine Anwendung mit mehreren Fenstern und setzt voraus, dass eine Anzeige vor dem Raum mit dem HDMI-Port des Geräts verbunden ist, damit die App ordnungsgemäß funktioniert. Stellen Sie sicher, dass entweder ein HDMI-Display angeschlossen ist, oder verwenden Sie einen Dummy-HDMI-Stecker, wenn Sie testen und noch keine Anzeige gekauft haben.
_** <a name="See"> </a>  
## <a name="see-also"></a>Siehe auch

[Microsoft Teams Rooms-Hilfe](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams Rooms verwalten](rooms-manage.md)
