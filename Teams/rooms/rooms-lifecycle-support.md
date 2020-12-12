---
title: Versionsunterstützung
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
localization_priority: Normal
description: Erfahren Sie mehr über die Lifecycle-Unterstützung von Microsoft Teams-Räume, einschließlich der Struktur und der Phasen der dynamischen Unterstützung.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 584f4661a39d21f916b2097c242f71b996c568e6
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662450"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Microsoft Teams-Räume – Unterstütze App-Versionen
 
Für die Microsoft Teams-Räume-App werden ein paar Mal pro Jahr Updates veröffentlicht. Jedes Update wird zwölf (12) Monate ab dem Veröffentlichungsdatum seiner allgemeinen Verfügbarkeit (GA) unterstützt. Über die gesamten 12 Monate wird technischer Support bereitgestellt. Allerdings ist die Unterstützung dynamisch und in zwei unterschiedliche Phasen gegliedert, die von der Verfügbarkeit der neuesten Version abhängig sind:

- **Phase der Bereitstellung von Wartungs- und wichtigen Updates** \- Wenn Sie die neueste Version der Microsoft Teams-Räume-App verwenden, erhalten Sie regelmäßig Updates, die *Sicherheits- und Wartungsupdates* umfassen.

- **Phase der Bereitstellung reiner Sicherheitsupdates** \- Wenn eine neue Version der Microsoft Teams-Räume-App veröffentlicht wird, reduziert sich für ältere Versionen der App die Supportstufe auf *nur Sicherheitsupdates* für den Rest des 12-Monat-Lebenszyklus.

> [!NOTE]
> Die neueste Version befindet sich immer in der Phase der Bereitstellung von Wartungs- und wichtigen Updates. Wenn Sie auf einen Codefehler stoßen, der ein wichtiges Update betrifft, müssen Sie auch die neueste Version installiert haben, um einen Fix zu erhalten. Alle anderen unterstützten Versionen können nur Sicherheitsupdates erhalten.

Sämtliche Unterstützung endet nach Ablauf des 12-Monate-Lebenszyklus einer Version oder wenn in der Zwischenzeit mehr als zwei Updates veröffentlicht wurden. Kunden müssen dann eine Aktualisierung auf eine unterstützte Version durchführen.

Alle Versionen sind in den [Versionshinweisen zu Microsoft Teams-Räume](rooms-release-note.md) aufgeführt.

## <a name="windows-10-release-support"></a>Unterstützte Windows 10-Versionen

Microsoft Teams-Räume erfordert die Windows 10 IoT Enterprise- oder Windows 10 Enterprise-SKUs unter den Wartungsoptionen für den halbjährlichen Kanal. Die folgenden anderen Windows 10-Editionen werden nicht unterstützt:

- Die Enterprise Long Term Servicing Branch (LTSB)/Long Term Servicing Channel (LTSC)-Editionen von Windows 10
- Die Internet of Things (IoT) Enterprise LTSB/LTSC-Editionen von Windows 10
- Alle anderen Windows-Editionen wie z. B. Windows 10 Pro oder Home

Ein Windows 10-Feature-Update wird auf Microsoft Teams-Räume-Geräten nicht sofort angeboten oder aktualisiert. Eine absichtliche Verzögerung von bis zu sechs Monaten nach dem Datum der allgemeinen Verfügbarkeit, das auf der Seite [Windows 10-Versionsinformationen](https://docs.microsoft.com/windows/release-information/) veröffentlicht wird. Die Verzögerung dient dazu, die Kompatibilität der Windows 10-Version mit der Microsoft Teams-Räume-Anwendung, Gerätehardware und zertifizierten Audio-/Video-Peripheriegeräten zu überprüfen. Die Überprüfung beginnt mit und wird während der aktiven Entwicklung jeder Hauptversion von Windows 10 fortgesetzt. Zusätzliche Zeit ist erforderlich, um zu überprüfen, ob alle Gerätehersteller aktualisierte Images für ihre Geräte erstellt haben, und für die Zertifizierung und das Testen dieser Images durch Microsoft Teams. Während des Überprüfungszeitraums verwendet die Microsoft Teams-Räume-App  [Windows Update for Business-Gruppenrichtlinien](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb), um Windows 10-Featureupdates zu verzögern. Nach dem Suchen und Beheben von Kompatibilitätsproblemen wird die Blockierung durch die Aktualisierung von Gruppenrichtlinien über eine neue App-Version im Windows Store aufgehoben. Geräte, auf denen die Microsoft Teams-Räume-App ausgeführt wird, werden während des nächtlichen Wartungs-Neustarts automatisch auf eine geeignete Windows 10-Version aktualisiert. Kunden, die Updates manuell verwalten möchten, wird eine MSI-Version zur Verfügung gestellt.  

> [!IMPORTANT]
> Während des Überprüfungszeitraums sollten Geräte mit Microsoft Teams-Räume **nicht** auf die neue Version von Windows 10 aktualisiert werden. Dies umfasst das Überschreiben bestehender Gruppenrichtlinien und die Verwendung von System Center oder anderen Geräteverwaltungsdiensten von Drittanbietern. Das könnte nämlich zu Problemen mit der Microsoft Teams-Räume-Anwendung führen oder Geräte unbrauchbar machen.  

Die folgende Tabelle enthält die empfohlenen und unterstützten Versionen von Windows 10, die Microsoft Teams-Räume garantiert unterstützen. Alle Datumsangaben sind im ISO 8601-Format "JJJJ-MM-DD" aufgeführt.

|Version  |Datum der Verfügbarkeit   |Support-Status für Microsoft Teams-Räume   |Mindestens erforderliche Microsoft Teams-Räume-Anwendungsversion | Empfohlener BS-Build  |
|:---  |:---       |:---                                  |:---     |:---     |
| 20H2 |2020-10-20 |Wird überprüft, <br/>Noch nicht unterstützt|&#x2014; |19042.572 |
| 2004 |2020-05-27 |Übersprungen, <br/> Nicht empfohlen|&#x2014; |19041.264 |
| 1909 |2019-11-12 |Stützt <br/>Empfohlen |4.5.33.0 |18363.418  |
| 1903 |2019-05-21 |Unterstützt  |4.2.4.0 |18362.356 |
| 1809 |2019-03-28 |Nicht unterstützt, <br/>Bekannte Kompatibilitätsprobleme &#x2780;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |Nicht unterstützt                             |&#x2014;  |&#x2014; |
| 1709 |2018-01-18 |Nicht unterstützt                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |Nicht unterstützt                         |&#x2014; |&#x2014; |

&#x2780; Windows 10, Version 1809, wird aufgrund von festgestellten Kompatibilitätsproblemen mit der Microsoft Teams-Räume-Anwendung nicht empfohlen. Dieses spezifische Problem bewirkt, dass die Microsoft Teams-Räume-Anwendung nach dem nächtlichen Neustart nicht mehr gestartet werden kann. Dieses Problem wurde in Windows 10, Version 1903, behoben.  

&#x2781; Windows 10, Version 2004, wird aufgrund von festgestellten Kompatibilitätsproblemen mit der Microsoft Teams-Räume-Anwendung nicht empfohlen. Dieses spezifische Problem bewirkt, dass die Microsoft Teams-Räume-Anwendung nach dem nächtlichen Neustart nicht mehr gestartet werden kann. 

Wenn Sie eine unterstützte Version von Windows 10 verwenden, erhalten Sie immer die neuesten Anwendungsupdates für die Microsoft Teams-Räume-App.  

## <a name="related-topics"></a>Verwandte Themen

[Microsoft Teams Rooms-Hilfe](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams-Räume – Versionshinweise](rooms-release-note.md)

[Plan für Microsoft Teams-Räume](rooms-plan.md)
