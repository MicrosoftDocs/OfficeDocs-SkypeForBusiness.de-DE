---
title: Bekannte Probleme
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection: M365-voice
description: Dieser Artikel erläutert die bekannten Probleme für Microsoft Teams Rooms nach Funktionsbereich.
ms.openlocfilehash: eaf95f8afd470376ee4f14549b50df8b38d93d34
ms.sourcegitcommit: e84becc101232b8017aab519378480c5dbebbb48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2019
ms.locfileid: "37468487"
---
# <a name="known-issues"></a>Bekannte Probleme 
 
Dieser Artikel führt die bekannten Probleme für Microsoft Teams Rooms nach Funktionsbereichen auf.
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>Aktualisieren 

| Problemtitel |  Verhalten \/ Symptom | Bekannte Problemumgehung | KB-Artikel |
|  ---        |      ---             |   ---            | --- |
|  App nicht mehr aktuell         |    Die Microsoft Teams Rooms-Konsole zeigt einen Fehler des Typs „Systemkonfiguration abgelaufen“ an.                |   [Verwenden Sie das Wiederherstellungstools für Microsoft Teams Rooms](recovery-tool.md)             |  Keine |


<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>Benutzeroberfläche 

| Problemtitel |  Verhalten \/ Symptom | Bekannte Problemumgehung | KB-Artikel |
|  ---        |      ---             |   ---            | --- |
|Virtuelle Tastatur fehlt   | Die virtuelle Tastatur wird nicht angezeigt, wenn Sie Informationen in Microsoft Teams Rooms eingeben müssen. Dieses Problem tritt nach der Installation des Windows 10 Creators Update (Version 1703) auf dem Surface Pro 4 auf, auf dem Microsoft Teams Rooms ausgeführt wird. | Um dieses Problem zu umgehen, öffnen Sie die virtuelle Tastatur manuell. Führen Sie hierzu folgende Schritte aus:<br><br> **1.** Halten Sie die Taskleiste gedrückt, und tippen Sie dann auf die Schaltfläche **Bildschirmtastatur anzeigen**. Ein Tastatursymbol sollte auf der rechten Seite der Taskleiste angezeigt werden. <br><br> **2.** Tippen Sie auf das Tastatursymbol, um die virtuelle Tastatur zu öffnen. | [KB4037694](https://support.microsoft.com/en-us/help/4037694/virtual-keyboard-missing-in-skype-room-systems-v2) | 

<a name="Hardware"> </a>  
## <a name="hardware"></a>Hardware

| Problemtitel |  Verhalten \/ Symptom | Bekannte Problemumgehung | KB-Artikel |
|  ---        |      ---             |   ---            |   --- |
| Monitore nicht erkannt | Wenn Sie Microsoft Teams Rooms auf einem Surface Pro-Gerät (Modell 2017) ausführen, werden Monitore nicht erkannt. |  Halten Sie den Surface Pro Power-Netzschalter mindestens 20 Sekunden lang gedrückt. Wenn Sie dies tun, wird das Gerät neu gestartet und löscht den Grafik-Cache. |[KB4055681](https://support.microsoft.com/en-us/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

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
Die 64-Bit-Version von Windows 10 Enterprise Anniversary Edition (Englisch, Version 1607) wird seit der Microsoft Teams Rooms-Version 3.0.12.0 nicht mehr unterstützt. 
***
Microsoft Teams Rooms ist eine Multi-Window-Anwendung und erfordert ein Front-Room-Display, das mit dem HDMI-Anschluss des Geräts verbunden werden muss, damit die APP ordnungsgemäß funktioniert. Stellen Sie sicher, dass Sie entweder ein HDMI-Display angeschlossen haben oder einen Dummy-HDMI-Stecker verwenden, wenn Sie testen und noch kein Display gekauft haben.
***
Windows 10 1903 wird in Microsoft Teams rooms-Geräten von Crestron aufgrund von Problemen mit einem Grafiktreiber noch nicht angeboten.

***
<a name="See"> </a>  
## <a name="see-also"></a>Siehe auch

[Microsoft Teams Rooms-Hilfe](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams Rooms verwalten](skype-room-systems-v2.md)
