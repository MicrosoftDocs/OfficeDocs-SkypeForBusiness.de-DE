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
- Teams_ITAdmin_Rooms
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Erfahren Sie mehr über die Lifecycle-Unterstützung von Microsoft Teams-Räume, einschließlich der Struktur und der Phasen der dynamischen Unterstützung.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 509f4da415d7a7bd583442f21bd46efc52c9984f
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706652"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Microsoft Teams-Räume – Unterstütze App-Versionen
 
Für die Microsoft Teams-Räume-App werden ein paar Mal pro Jahr über den Windows-Store Updates veröffentlicht. Die App verwendet einen immergrünen Produktlebenszyklus, und nur die aktuelle und die neueste Version der App werden zu einem bestimmten Zeitpunkt unterstützt. Die App bündelt eine bestimmte Version der Teams-Desktop-App, die für die Raumnutzung geändert wird. Die Teams-Desktop-App wird alle zwei Wochen aktualisiert, während die Teams-Räume-App weniger häufig aktualisiert wird. Dies bedeutet, dass Teams-Räume Aktuelle-1-Version der App bis zu sechs Teams-Desktop-App-Updates zurücklegen kann. Daher wird empfohlen, die Teams-Räume-App jederzeit auf die neueste Version zu aktualisieren. Erfahren Sie mehr über den [Microsoft Teams-Aktualisierungsvorgang](../teams-client-update.md).

Die Supportstruktur für Microsoft Teams-Räume ist dynamisch und hängt von der Verfügbarkeit der neuesten Version ab. Wenn ein Codefehler in einer Version der Anwendung auftritt, die nicht die neueste ist, müssen Sie die neueste Version installieren, um eine Lösung zu erhalten.

Alle Versionen sind in den [Versionshinweisen zu Microsoft Teams-Räume](rooms-release-note.md) aufgeführt.

> [!IMPORTANT]
> Bei der Installation eines neuen Geräts, das mit einer älteren Version der Microsoft Teams-Räume-Anwendung ausgeliefert wurde, wird empfohlen, die Anwendung nach dem Konfigurieren des Kontos [manuell zu aktualisieren](manual-update.md), bevor Sie Windows-Updates herunterladen. Dadurch wird sichergestellt, dass die richtige Betriebssystemversion und Windows-Updates auf Ihrem Gerät installiert sind.  

## <a name="windows-10-release-support"></a>Unterstützte Windows 10-Versionen

Microsoft Teams-Räume erfordert die Windows 10 IoT Enterprise- oder Windows 10 Enterprise-SKUs unter den Wartungsoptionen für den halbjährlichen Kanal. Die folgenden anderen Windows 10-Editionen werden nicht unterstützt:

- Die Enterprise Long Term Servicing Branch (LTSB)/Long Term Servicing Channel (LTSC)-Editionen von Windows 10
- Die Internet of Things (IoT) Enterprise LTSB/LTSC-Editionen von Windows 10
- Alle anderen Windows-Editionen wie z. B. Windows 10 Pro oder Home

Windows 10-Feature-Updates werden auf Microsoft Teams-Räume-Geräten nicht sofort angeboten. Es gibt eine absichtliche Verzögerung von bis zu sechs Monaten oder mehr nach dem Datum der allgemeinen Verfügbarkeit, das auf der Seite [Windows 10-Versionsinformationen](/windows/release-information/) veröffentlicht wird. Die Verzögerung dient dazu, die Kompatibilität der Windows 10-Version mit der Microsoft Teams-Räume-Anwendung, Gerätehardware und zertifizierten Audio-/Video-Peripheriegeräten zu überprüfen. Die Überprüfung beginnt mit und wird während der aktiven Entwicklung jeder Hauptversion von Windows 10 fortgesetzt. Zusätzliche Zeit ist erforderlich, um zu überprüfen, ob alle Gerätehersteller aktualisierte Images für ihre Geräte erstellt haben, und für die Zertifizierung und das Testen dieser Images durch Microsoft. Während des Überprüfungszeitraums verwendet die Microsoft Teams-Räume-App [Windows Update for Business-Gruppenrichtlinien](/windows/deployment/update/waas-manage-updates-wufb), um Windows 10 Featureupdates zu verzögern. Nach dem Suchen und Beheben von Kompatibilitätsproblemen wird die Blockierung durch die Aktualisierung von Gruppenrichtlinien über eine neue App-Version im Windows Store aufgehoben. Geräte, auf denen die Microsoft Teams-Räume-App ausgeführt wird, werden während des nächtlichen Wartungs-Neustarts automatisch auf eine geeignete Windows 10-Version aktualisiert. Kunden, die Updates manuell verwalten müssen, wird eine MSI-Version zur Verfügung gestellt.  

> [!IMPORTANT]
> Während des Überprüfungszeitraums sollten Geräte mit Microsoft Teams-Räume **nicht** auf die neue Version von Windows 10 aktualisiert werden. Dies umfasst das Überschreiben bestehender Gruppenrichtlinien und die Verwendung von System Center oder anderen Geräteverwaltungsdiensten von Drittanbietern. Jede dieser Elemente kann Probleme für die Microsoft Teams-Räume-App verursachen oder Geräte unbrauchbar machen.  

Die folgende Tabelle enthält die empfohlenen und unterstützten Versionen von Windows 10, die Microsoft Teams-Räume garantiert unterstützen. Alle Datumsangaben sind im ISO 8601-Format "JJJJ-MM-DD" aufgeführt.

| Version | Datum der Verfügbarkeit | Support-Status für Microsoft Teams-Räume                    | Mindestens erforderliche Microsoft Teams-Räume-Anwendungsversion | Empfohlener BS-Build |
|:--------|:------------------|:--------------------------------------------------------|:--------------------------------------------------|:---------------------|
| 21H2    | 2021-11-16        | Unterstützt,<br>Empfohlen                               | 4.12.126.0                                        | 19044.1288           |
| 21H1    | 2021-05-18        | Nicht unterstützt                                           | &#x2014;                                          | &#x2014;             |
| 20H2    | 2020-10-20        | Unterstützt                                               | 4.10.10.0                                         | 19042.631            |
| 2004    | 2020-05-27        | Übersprungen, <br/> Nicht empfohlen &#x2780;                 | &#x2014;                                          | &#x2014;             |
| 1909    | 2019-11-12        | Unterstützt                                               | 4.5.33.0                                          | 18363.418            |
| 1903    | 2019-05-21        | Nicht unterstützt                                           | &#x2014;                                          | &#x2014;             |
| 1809    | 2019-03-28        | Nicht unterstützt, <br/>Bekannte Kompatibilitätsprobleme &#x2781; | &#x2014;                                          | &#x2014;             |
| 1803    | 2018-07-10        | Nicht unterstützt                                           | &#x2014;                                          | &#x2014;             |
| 1709    | 2018-01-18        | Nicht unterstützt                                           | &#x2014;                                          | &#x2014;             |
| 1703    | 2017-07-11        | Nicht unterstützt                                           | &#x2014;                                          | &#x2014;             |

&#x2780; Windows 10, Version 2004, wird aufgrund von festgestellten Kompatibilitätsproblemen mit der Microsoft Teams-Räume-Anwendung nicht empfohlen. Dieses spezifische Problem bewirkt, dass die Microsoft Teams-Räume-Anwendung nach dem nächtlichen Neustart nicht mehr gestartet werden kann. 

&#x2781; Windows 10, Version 1809, wird aufgrund von festgestellten Kompatibilitätsproblemen mit der Microsoft Teams-Räume-Anwendung nicht empfohlen. Dieses spezifische Problem bewirkt, dass die Microsoft Teams-Räume-Anwendung nach dem nächtlichen Neustart nicht mehr gestartet werden kann. Dieses Problem wurde in Windows 10, Version 1903, behoben.  

Wenn Sie eine unterstützte Version von Windows 10 verwenden, erhalten Sie immer die neuesten Anwendungsupdates für die Microsoft Teams-Räume-App.  


## <a name="related-topics"></a>Verwandte Themen

[Microsoft Teams Rooms-Hilfe](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams-Räume – Versionshinweise](rooms-release-note.md)

[Plan für Microsoft Teams-Räume](rooms-plan.md)
