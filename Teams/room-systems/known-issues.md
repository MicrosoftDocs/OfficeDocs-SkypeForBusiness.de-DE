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
ms.openlocfilehash: 3e3da371a294582fc6a56db7e59615fdbe97c48b
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775194"
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

Ein Consumer-Fernsehgerät, das als Front-of-room-Display verwendet wird, muss die Funktion der Unterhaltungselektronik-Steuerung (CEC) von HDMI unterstützen, um automatisch auf eine aktive Videoquelle aus dem Standbymodus umzuschalten. Dieses Feature wird nicht auf allen TVs unterstützt.

***

Verwenden Sie immer eine verkabelte 1-Gbit/s-Netzwerkverbindung, um sicherzustellen, dass Sie die erforderliche Bandbreite aufweisen. 

***

Wenn Ihr Microsoft Teams rooms-Gerät die Vertrauensstellung für die Domäne verliert, können Sie sich nicht mehr bei dem Gerät authentifizieren und Einstellungen öffnen. Wenn Sie beispielsweise die Microsoft Teams-Räume aus der Domäne entfernen, nachdem Sie der Domäne beigetreten sind, geht die Vertrauensstellung verloren. Die Lösung ist, sich mit dem lokalen Administratorkonto anzumelden. 
***
Die 64-Bit-Version von Windows 10 Enterprise Anniversary Edition (Englisch, Version 1607) wird seit der Microsoft Teams Rooms-Version 3.0.12.0 nicht mehr unterstützt. 
***
Microsoft Teams Rooms ist eine Multi-Window-Anwendung und erfordert ein Front-Room-Display, das mit dem HDMI-Anschluss des Geräts verbunden werden muss, damit die APP ordnungsgemäß funktioniert. Stellen Sie sicher, dass Sie entweder ein HDMI-Display angeschlossen haben oder einen Dummy-HDMI-Stecker verwenden, wenn Sie testen und noch kein Display gekauft haben.
***
<a name="See"> </a>  
## <a name="see-also"></a>Siehe auch

[Microsoft Teams Rooms-Hilfe](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams Rooms verwalten](skype-room-systems-v2.md)
