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
ms.openlocfilehash: 7ecfd878b5d8aa22a19b4b2831c04a73e0d8911e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58607028"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Microsoft Teams-Räume – Unterstütze App-Versionen
 
Für die Microsoft Teams-Räume-App werden ein paar Mal pro Jahr Updates veröffentlicht. Jedes Update wird für zwölf (12) Monate ab dem Veröffentlichungsdatum der allgemeinen Verfügbarkeit unterstützt. Über die gesamten 12 Monate wird technischer Support bereitgestellt. Allerdings ist die Unterstützung dynamisch und in zwei unterschiedliche Phasen gegliedert, die von der Verfügbarkeit der neuesten Version abhängig sind:

- **Servicing and Critical Updates phase** – When you run the latest version of the Microsoft Teams-Räume app, you receive regular updates that contain Security and *Servicing* updates.

- Phase Nur Sicherheitsupdates: Wenn eine neue Version der Microsoft Teams-Räume-App veröffentlicht wird, verfügen  ältere Versionen der App nur für die restlichen zwölf (12) Monate über eine eingeschränkte Unterstützungsstufe mit Sicherheitsupdates. 

> [!NOTE]
> Die neueste Version befindet sich immer in der Phase der Bereitstellung von Wartungs- und wichtigen Updates. Wenn Sie auf einen Codefehler stoßen, der ein wichtiges Update betrifft, müssen Sie auch die neueste Version installiert haben, um einen Fix zu erhalten. Alle anderen unterstützten Versionen können nur Sicherheitsupdates erhalten.

Sämtliche Unterstützung endet nach Ablauf des 12-Monate-Lebenszyklus einer Version oder wenn in der Zwischenzeit mehr als zwei Updates veröffentlicht wurden. Kunden müssen dann eine Aktualisierung auf eine unterstützte Version durchführen.

Alle Versionen sind in den [Versionshinweisen zu Microsoft Teams-Räume](rooms-release-note.md) aufgeführt.

## <a name="windows-10-release-support"></a>Unterstützte Windows 10-Versionen

Microsoft Teams-Räume erfordert die Windows 10 IoT Enterprise- oder Windows 10 Enterprise-SKUs unter den Wartungsoptionen für den halbjährlichen Kanal. Die folgenden anderen Windows 10-Editionen werden nicht unterstützt:

- Die Enterprise Long Term Servicing Branch (LTSB)/Long Term Servicing Channel (LTSC)-Editionen von Windows 10
- Die Internet of Things (IoT) Enterprise LTSB/LTSC-Editionen von Windows 10
- Alle anderen Windows-Editionen wie z. B. Windows 10 Pro oder Home

Neue Windows 10-Featureupdates werden nicht sofort auf Microsoft Teams-Räume angeboten. Eine absichtliche Verzögerung von bis zu sechs Monaten nach dem Datum der allgemeinen Verfügbarkeit, das auf der Seite [Windows 10-Versionsinformationen](/windows/release-information/) veröffentlicht wird. Die Verzögerungszeit wird verwendet, um die Windows 10 Release-Kompatibilität für die Microsoft Teams-Räume, Gerätehardware und zertifizierte Audiovideoperipheriegeräte zu überprüfen. Die Überprüfung beginnt mit und wird während der aktiven Entwicklung jeder Hauptversion von Windows 10 fortgesetzt. Zusätzliche Zeit ist erforderlich, um zu überprüfen, ob alle Gerätehersteller aktualisierte Images für ihre Geräte erstellt haben, und für die Zertifizierung und das Testen dieser Images durch Microsoft Teams. Während des Überprüfungszeitraums verwendet die Microsoft Teams Raum-App die Windows Update for Business-Gruppenrichtlinien, um Windows 10 zu verzögern. [](/windows/deployment/update/waas-manage-updates-wufb) Nach dem Suchen und Beheben von Kompatibilitätsproblemen wird die Blockierung durch die Aktualisierung von Gruppenrichtlinien über eine neue App-Version im Windows Store aufgehoben. Geräte, auf denen die Microsoft Teams-Räume-App ausgeführt wird, werden während des nächtlichen Wartungs-Neustarts automatisch auf eine geeignete Windows 10-Version aktualisiert. Kunden, die Updates manuell verwalten möchten, wird eine MSI-Version zur Verfügung gestellt.  

> [!IMPORTANT]
> Während des Überprüfungszeitraums sollten Geräte mit Microsoft Teams-Räume **nicht** auf die neue Version von Windows 10 aktualisiert werden. Dies umfasst das Überschreiben bestehender Gruppenrichtlinien und die Verwendung von System Center oder anderen Geräteverwaltungsdiensten von Drittanbietern. Jedes dieser Punkte kann Probleme für die App Microsoft Teams Raum verursachen oder dafür sorgen, dass Geräte nicht mehr verwendet werden können.  

Die folgende Tabelle enthält die empfohlenen und unterstützten Versionen von Windows 10, die Microsoft Teams-Räume garantiert unterstützen. Alle Datumsangaben sind im ISO 8601-Format "JJJJ-MM-DD" aufgeführt.

|Version  |Datum der Verfügbarkeit   |Support-Status für Microsoft Teams-Räume   |Mindestens erforderliche Microsoft Teams-Räume-Anwendungsversion | Empfohlener BS-Build  |
|:---  |:---       |:---                                  |:---     |:---     |
| 20H2 |2020-10-20 |"Unterstützt" <br/>Empfohlen|4.8.31.0 |19042.631 |
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

> [!IMPORTANT]
> Das Windows 10 20H2-Update ist für die folgenden Teams-Räume aufgrund von Kompatibilitätsproblemen noch nicht verfügbar. GERÄTE-OEMs arbeiten daran, diese Probleme so schnell wie möglich zu beheben. Windows 10 20H2 wird auf diesen Geräten nicht angeboten. Aktualisieren Sie diese Geräte nicht manuell auf 20H2, indem Sie Gruppenrichtlinienobjekte (Group Policy Objects, GPOs) oder MdM (Verwaltung mobiler Geräte) außer Kraft setzen. 
> 
> Die Geräte mit Kompatibilitätsproblemen sind:
> 
> - Crestron UC-Engine (BIOS-Version/Datum enthält "KYSKLI" – gibt ein Skull Canyon-BIOS an) 

## <a name="related-topics"></a>Verwandte Themen

[Microsoft Teams Rooms-Hilfe](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams-Räume – Versionshinweise](rooms-release-note.md)

[Plan für Microsoft Teams-Räume](rooms-plan.md)
