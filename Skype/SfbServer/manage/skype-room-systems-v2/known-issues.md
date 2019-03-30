---
title: Bekannte Probleme
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
description: In diesem Artikel werden bekannte Probleme für Microsoft-Teams, Räume nach Funktionsbereich.
ms.openlocfilehash: d71b209784f4737ac4433e2eececb1f9ada3ebc8
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2019
ms.locfileid: "31013087"
---
# <a name="known-issues"></a>Bekannte Probleme 
 
In diesem Artikel werden die bekannten Probleme für Microsoft-Teams, Räume nach Funktionsbereich.
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>Update 

| Titel des Problems |  Verhalten \/ Symptom | Bekannte Problemumgehung | KB-Artikel |
|  ---        |      ---             |   ---            | --- |
|  App veraltete         |    Die Microsoft-Teams Räume-Konsole zeigt einen "veraltet System Config".                |   [Verwenden Sie das Microsoft-Teams Chatrooms Recovery-tool](recovery-tool.md)             |  Keine  |


<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>Benutzeroberfläche 

| Titel des Problems |  Verhalten \/ Symptom | Bekannte Problemumgehung | KB-Artikel |
|  ---        |      ---             |   ---            | --- |
|Fehlende virtuelle Tastatur   | Virtuelle Tastatur wird nicht angezeigt, wenn Sie die Informationen in den Microsoft-Teams Chatrooms eingeben müssen. Dieses Problem tritt nach der Installation der Windows 10 Ersteller von Updates (Version 1703) unter Surface Pro 4, auf dem Microsoft-Teams Chatrooms ausgeführt wird. | Um dieses Problem zu umgehen, öffnen Sie manuell virtuelle Tastatur. Gehen Sie hierzu folgendermaßen vor:<br><br> **1.** Tippen Sie und halten Sie den Vorgangsbalken, und tippen Sie dann auf die Schaltfläche **Show Bildschirmtastatur** . Ein Tastatursymbol sollte auf der rechten Seite des Vorgangsbalkens angezeigt werden. <br><br> **2.** Tippen auf der Tastatursymbol, um die virtuelle Tastatur zu öffnen. | [KB4037694](https://support.microsoft.com/en-us/help/4037694/virtual-keyboard-missing-in-skype-room-systems-v2) | 
   

<a name="Hardware"> </a>  
## <a name="hardware"></a>Hardware

| Titel des Problems |  Verhalten \/ Symptom | Bekannte Problemumgehung | KB-Artikel |
|  ---        |      ---             |   ---            |   --- |
| Monitore nicht erkannt | Wenn Sie Microsoft-Teams Räume auf einem Gerät Surface Pro (Modell 2017) ausführen, werden die Monitore nicht erkannt. |  Halten Sie die Surface Pro Power mindestens 20 Sekunden lang. Wenn Sie dies tun, wird das Gerät neu gestartet, und löscht den Cache Grafiken. |[KB4055681](https://support.microsoft.com/en-us/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 
          
<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>Einschränkungen und erwartetes Verhalten
***
Microsoft-Teams Chatrooms unterstützt keine HDCP-Eingang beobachtet hat verursacht Probleme mit HDMI Aufnahme Funktionalität (Video, audio). Achten Sie darauf, dass Switches angeschlossen zu Microsoft-Teams Räumen HDCP-Optionen deaktiviert aufweisen. 
***
Ein Consumer TV als Front Raum Anzeige Anforderungen für den Support/HDMI das Consumer Electronics Steuerelement (CEC)-Feature aktivieren, damit er automatisch an eine aktive Bildquelle aus dem Standbymodus wechseln kann. Dieses Feature wird auf alle TV-Geräte nicht unterstützt. 
***
Verwenden Sie immer eine drahtgebundene 1 Gbit/s-Netzwerk-Verbindung, um sicherzustellen, dass Sie die erforderliche Bandbreite verfügen. 
***
Wenn Ihr Microsoft-Teams Chatrooms Gerät verliert Vertrauensstellung mit der Domäne (beispielsweise, wenn Sie die Microsoft-Teams Räume aus der Domäne entfernen, nach der Domäne beigetreten ist), werden nicht Sie an das Gerät authentifizieren und Einstellungen zu öffnen. Melden Sie sich über das lokale Administratorkonto werden der umgangen. 
***
3.0.12.0 freigeben, die 64-Bit-Version von Windows 10 Enterprise Jahrestag Edition (englische, Version 1607) ab Microsoft Teams Chatrooms nicht mehr unterstützt werden. 
***

<a name="See"> </a>  
## <a name="see-also"></a>Siehe auch

[Hilfe für Microsoft-Teams Räume](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Verwalten von Microsoft-Teams, Räume](skype-room-systems-v2.md)