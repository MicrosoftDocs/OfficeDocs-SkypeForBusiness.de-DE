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
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: Der Administrator kann sich über eine Liste der bekannten Probleme für Microsoft Teams-Räume informieren, einschließlich Update, Benutzeroberfläche, Hardware, Einschränkungen und erwartetem Verhalten.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: adf3b0fb7642b4a9774459527af304fe33167352
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578319"
---
# <a name="known-issues"></a>Bekannte Probleme 
 
Dieser Artikel führt die bekannten Probleme für Microsoft Teams Rooms nach Funktionsbereichen auf.
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>Aktualisieren 

| Problemtitel |  Verhalten \/ Symptom | Bekannte Problemumgehung | KB-Artikel |
|  ---        |      ---             |   ---            | --- |
| Anwendung wird nicht gestartet |  Nach dem Update auf Anwendungsversion 4.4.41.0 wird das System auf einen schwarzen Bildschirm ge bootst, oder nach ein paar Minuten zum Anmeldebildschirm wechseln. | Führen Sie die Schritte in Microsoft Teams-Räume die Anwendung nach dem Update auf [Version 4.4.41.0](/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update) nicht gestartet wird, um dieses Problem zu beheben.  | Keine |
|  Geringes Besprechungsvolumen nach Inhaltsfreigabe         |   Microsoft Teams-Räume auf Windows 10 20H2-Geräten verringert sich die Medien- und Besprechungslautstärke nach der Freigabe von Inhalten über den HDMI-Eingang im Raum. Dies wird durch ein Audioproblem in Windows 10 20H2 verursacht. | Der Fix für dieses Problem ist in Anwendungsversion [4.9.12.0 verfügbar.](/microsoftteams/rooms/rooms-release-note#49120-7282021) | Keine |
|  App nicht mehr aktuell         |    Die Microsoft Teams Rooms-Konsole zeigt einen Fehler des Typs „Systemkonfiguration abgelaufen“ an.                |   [Verwenden Sie das Wiederherstellungstools für Microsoft Teams Rooms](recovery-tool.md)             |  Keine |
|  Gerät auf nicht unterstützte Version von Windows 10   |    Windows 10 von Version 1803 auf Version 1809 aktualisiert, was nicht unterstützt wird. Die unterstützte Version ist 1903. |   Dies kann geschehen, wenn die Gruppenrichtlinie- oder MDM-Einstellung für die Einstellung [DeferFeatureUpdatesPeriodinDays,](/windows/deployment/update/waas-configure-wufb) mit der Sie Funktionsupdates für eine bestimmte Anzahl von Tagen zurück stellen können, auf den Höchstwert von 365 Tagen festgelegt ist. <br><br> Windows 10 Version 1809 wird von Microsoft Teams-Räume nicht unterstützt, während Version 1903 unterstützt wird. Ab dem 27. März 2020 ist Version 1809 jedoch mehr als 365 Tage alt. Wenn diese Einstellung nicht geändert wird, versucht Windows Version 1809 zu installieren, was zu Problemen mit dem Microsoft Teams-Räume.<br><br>Um diese Situation zu vermeiden, **entfernen** Sie alle Gruppenrichtlinien- oder MDM-Einstellungen zum Zurückdringen von Updates. Dadurch können Windows auf die neueste, unterstützte Betriebssystemversion aktualisieren. <br><br>**WICHTIG** Die Gruppenrichtlinie- oder MDM-Einstellung muss **entfernt** (links nicht konfiguriert) und **nicht auf "0" festgelegt werden.** Wenn die Richtlinie auf 0 festgelegt ist, Windows die neueste verfügbare Version, die möglicherweise nicht unterstützt wird. |  Keine |



<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>Benutzeroberfläche 

| Problemtitel |  Verhalten \/ Symptom | Bekannte Problemumgehung | KB-Artikel |
|  ---        |      ---             |   ---            | --- |
|Virtuelle Tastatur fehlt   | Die virtuelle Tastatur wird nicht angezeigt, wenn Sie Informationen in Microsoft Teams Rooms eingeben müssen. Dieses Problem tritt in Windows 10 Version 1903 auf. | Installieren Sie das kumulative Update 2020-04 für Windows 10 Version 1903 für x64-basierte Systeme über Windows Updates.  | Keine | 

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

Wenn Sie möchten, dass die Anzeige vor dem Raum automatisch zu einer aktiven Videoquelle (z. B. einer MTR-Konsole) wechselt, wenn die Quelle aus dem Standbymodus reaktiviert wird, müssen bestimmte Bedingungen erfüllt sein. Dieses Feature ist optional, wird aber von Microsoft Teams-Räume unterstützt, sofern die zugrunde liegende Hardware das Feature unterstützt. Ein Consumer-TV, das als Front-Of-Room-Anzeige verwendet wird, muss die HDMI-Funktion (Consumer Electronics Control) für Consumer Electronics Control (CEC) unterstützen.  Je nach ausgewählter Docking-Station oder Konsole (die CEC möglicherweise nicht unterstützt, finden Sie in der Dokumentation zum Support des Herstellers) kann ein Controller wie [HD-TX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) von Crestron oder [Exppe HD CTL 100](https://www.extron.com/article/hdctl100ad) von Ex selbst erforderlich sein, um das gewünschte Verhalten zu ermöglichen.

Darüber hinaus kann ein Consumer-TV, das vor dem Anzeigen im Raum verwendet wird, zu Stabilitätsproblemen bei der Microsoft Teams-Räume führen. Dies liegt an der inkonsistenten Implementierung von Standbymodi, der Auswahl aktiver Videoquellen und der Übermittlung fehlerhafter EDID-Informationen Microsoft Teams-Räume Gerät. Bekannte Symptome sind ein schwarzer/grauer Bildschirm auf der Vorderseite der Raumanzeige oder die Microsoft Teams-Räume-Konsole reagiert nicht mehr, nachdem sie aus dem Standbymodus wieder reagiert.  Wenn bei der Verwendung von Consumer-TVs Probleme auftreten, empfehlen wir die Installation eines konfigurierbaren EDID-Controllers oder EDID-Emulators wie [HD-TX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) von Crestron oder [DR-EDID Emulator](https://fsrinc.com/fsr-products/product/dr-edid-manager-learner/category_pathway-143) aus der FSR Video Products Group.

***

Verwenden Sie immer eine kabelgebundene 1-Gbit/s-Netzwerkverbindung, um sicherzustellen, dass Sie über die erforderliche Bandbreite verfügen. 

***

Wenn Ihr Microsoft Teams-Räume keine Vertrauensstellung mit der Domäne mehr hat, können Sie sich beim Gerät nicht mehr authentifizieren und keine Einstellungen. Wenn Sie beispielsweise die Domäne Microsoft Teams-Räume, nachdem die Domäne beigetreten ist, geht die Vertrauensstellung verloren. Die Lösung ist, sich mit dem lokalen Administratorkonto anzumelden. 
***
Microsoft Teams-Räume ist eine Anwendung mit mehreren Fenstern, für die eine Anzeige vor dem Raum an den HDMI-Port des Geräts angeschlossen werden muss, damit die App ordnungsgemäß funktioniert. Stellen Sie sicher, dass Sie entweder eine HDMI-Anzeige angeschlossen haben oder einen Dummy-HDMI-Stecker verwenden, wenn Sie testen und noch keine Anzeige erworben haben.
***
<a name="See"> </a>  
## <a name="see-also"></a>Siehe auch

[Microsoft Teams Rooms-Hilfe](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams Rooms verwalten](rooms-manage.md)
