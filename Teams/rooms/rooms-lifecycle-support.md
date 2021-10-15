---
title: Microsoft Teams-Räume – Unterstütze App-Versionen
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Erfahren Sie mehr über die Lifecycle-Unterstützung von Microsoft Teams-Räume, einschließlich der Struktur und der Phasen der dynamischen Unterstützung.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 937c6b43ebdc7c775251f0a7fc576cc11e666a7f
ms.sourcegitcommit: d23185cf6caeeeb055c36609e7c788a2b2e8d07d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2021
ms.locfileid: "60367497"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Microsoft Teams-Räume – Unterstütze App-Versionen
 
Die Microsoft Teams-Räume-App erhält vierteljährlich Updates über den Windows Store. Zwischendurch kann ein Out-of-Band-Update vorgenommen werden, um dringende Probleme zu beheben. Microsoft Teams Die Raum-App verwendet einen sich immergrünen Produktlebenszyklus, und zu einem bestimmten Zeitpunkt werden nur die aktuelle und die letzte Version der App unterstützt. Die Microsoft Teams Raum-App bündelt eine bestimmte Version der Teams-Desktop-App, die für die Raumnutzung geändert wird. Die Teams Desktop-App wird alle zwei Wochen aktualisiert. Erfahren Sie mehr über [Teams Aktualisierungsvorgang.](../teams-client-update.md) Dies bedeutet, Teams-Räume-Version der aktuellen Version der Teams-App bis zu sechs Desktop-App-Updates zurück liegen kann. Es wird daher empfohlen, die Teams Room-Anwendung immer auf die neueste Version der Teams-Räume-App zu aktualisieren. 

Die Supportstruktur für Teams-Räume ist dynamisch und hängt von der Verfügbarkeit der neuesten Version ab. Wenn Sie bei einer Version der Anwendung auf Code stoßen, der nicht die neueste ist, müssen Sie die neueste Version installieren, um einen Fix zu erhalten.

Alle Versionen sind in den [Versionshinweisen zu Microsoft Teams-Räume](rooms-release-note.md) aufgeführt.

> [!IMPORTANT]
> Bei der Installation eines neuen Geräts, das mit einer älteren Version [](manual-update.md) der Teams-Raumanwendung enthalten war, wird empfohlen, die Anwendung nach dem Festlegen des Kontos manuell zu aktualisieren, bevor Sie alle Windows herunterladen. Dadurch wird sichergestellt, dass korrekte Betriebssystemversion und Windows Updates auf Ihrem Gerät installiert werden.  

## <a name="windows-10-release-support"></a>Unterstützte Windows 10-Versionen

Microsoft Teams-Räume erfordert die Windows 10 IoT Enterprise- oder Windows 10 Enterprise-SKUs unter den Wartungsoptionen für den halbjährlichen Kanal. Die folgenden anderen Windows 10-Editionen werden nicht unterstützt:

- Die Enterprise Long Term Servicing Branch (LTSB)/Long Term Servicing Channel (LTSC)-Editionen von Windows 10
- Die Internet of Things (IoT) Enterprise LTSB/LTSC-Editionen von Windows 10
- Alle anderen Windows-Editionen wie z. B. Windows 10 Pro oder Home

Neue Windows 10 Featureupdates werden auf Ihren Geräten Microsoft Teams-Räume angeboten. Es gibt eine beabsichtigte Verzögerung von bis zu sechs Monaten oder mehr nach dem allgemeinen Verfügbarkeitsdatum, das auf der Seite Windows 10 [veröffentlicht](/windows/release-information/) wurde. Dieses Mal wird verwendet, um Windows 10 Veröffentlichungskompatibilität für die Microsoft Teams-Räume, Gerätehardware und zertifizierte Audiovideoperipheriegeräte zu überprüfen. Die Überprüfung beginnt mit und wird während der aktiven Entwicklung jeder Hauptversion von Windows 10 fortgesetzt. Zusätzliche Zeit ist erforderlich, um zu überprüfen, ob alle Gerätehersteller aktualisierte Images für ihre Geräte erstellt haben, und für die Zertifizierung und das Testen dieser Images durch Microsoft Teams. Während des Überprüfungszeitraums verwendet die Microsoft Teams Raum-App die Windows Update for Business-Gruppenrichtlinien, um Windows 10 zu verzögern. [](/windows/deployment/update/waas-manage-updates-wufb) Nach dem Suchen und Beheben von Kompatibilitätsproblemen wird die Blockierung durch die Aktualisierung von Gruppenrichtlinien über eine neue App-Version im Windows Store aufgehoben. Geräte, auf denen die Microsoft Teams-Räume-App ausgeführt wird, werden während des nächtlichen Wartungs-Neustarts automatisch auf eine geeignete Windows 10-Version aktualisiert. Kunden, die Updates manuell verwalten möchten, wird eine MSI-Version zur Verfügung gestellt.  

> [!IMPORTANT]
> Während des Überprüfungszeitraums sollten Geräte mit Microsoft Teams-Räume **nicht** auf die neue Version von Windows 10 aktualisiert werden. Dies umfasst das Überschreiben bestehender Gruppenrichtlinien und die Verwendung von System Center oder anderen Geräteverwaltungsdiensten von Drittanbietern. Jedes dieser Probleme kann Probleme für die App Microsoft Teams Raum verursachen oder dafür sorgen, dass Geräte nicht mehr verwendet werden können.  

Die folgende Tabelle enthält die empfohlenen und unterstützten Versionen von Windows 10, die Microsoft Teams-Räume garantiert unterstützen. Alle Datumsangaben sind im ISO 8601-Format "JJJJ-MM-DD" aufgeführt.

|Version  |Datum der Verfügbarkeit   |Support-Status für Microsoft Teams-Räume   |Mindestens erforderliche Microsoft Teams-Räume-Anwendungsversion | Empfohlener BS-Build  |
|:---  |:---       |:---                                  |:---     |:---     |
| 20H2 |2020-10-20 |"Unterstützt" <br/>Empfohlen|4.10.10.0 |19042.631 |
| 2004 |2020-05-27 |Übersprungen, <br/> Nicht empfohlene &#x2780;|&#x2014; |&#x2014; |
| 1909 |2019-11-12 |Unterstützt |4.5.33.0 |18363.418  |
| 1903 |2019-05-21 |Nicht unterstützt  |&#x2014; |&#x2014; |
| 1809 |2019-03-28 |Nicht unterstützt, <br/>Bekannte Kompatibilitätsprobleme &#x2781;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |Nicht unterstützt                             |&#x2014;  |&#x2014; |
| 1709 |2018-01-18 |Nicht unterstützt                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |Nicht unterstützt                         |&#x2014; |&#x2014; |

&#x2780; Windows 10 Version 2004 wird aufgrund von Kompatibilitätsproblemen bei der Anwendung Microsoft Teams-Räume empfohlen. Dieses spezifische Problem bewirkt, dass die Microsoft Teams-Räume-Anwendung nach dem nächtlichen Neustart nicht mehr gestartet werden kann. 

&#x2781; Windows 10 Version 1809 wird aufgrund von Kompatibilitätsproblemen bei der Anwendung Microsoft Teams-Räume empfohlen. Dieses spezifische Problem bewirkt, dass die Microsoft Teams-Räume-Anwendung nach dem nächtlichen Neustart nicht mehr gestartet werden kann. Dieses Problem wurde in Windows 10, Version 1903, behoben.  

Wenn Sie eine unterstützte Version von Windows 10 verwenden, erhalten Sie immer die neuesten Anwendungsupdates für die Microsoft Teams-Räume-App.  


## <a name="related-topics"></a>Verwandte Themen

[Microsoft Teams Rooms-Hilfe](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams-Räume – Versionshinweise](rooms-release-note.md)

[Plan für Microsoft Teams-Räume](rooms-plan.md)
