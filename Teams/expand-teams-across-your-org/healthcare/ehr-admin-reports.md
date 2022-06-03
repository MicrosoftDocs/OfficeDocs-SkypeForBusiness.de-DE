---
title: Microsoft Teams-VNR-Connector – Bericht "Virtuelle Termine"
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Erfahren Sie, wie Sie den Microsoft Teams EHR-Connector für virtuelle Termine im Microsoft Teams Admin Center verwenden, um einen Überblick über die in die EGA integrierte Nutzung virtueller Termine in Ihrer Organisation zu erhalten.
ms.openlocfilehash: 0e78b89c934eac101b863bd7b5ba9957939f994b
ms.sourcegitcommit: cf2f2d23e6dcda0c03f22a5800a210a1c88e583f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2022
ms.locfileid: "65883538"
---
# <a name="microsoft-teams-ehr-connector-virtual-appointments-report"></a>Microsoft Teams-VNR-Connector – Bericht "Virtuelle Termine"

Der Microsoft Teams Electronic Health Record (EHR)-Connector für virtuelle Termine im Microsoft Teams Admin Center bietet Ihnen eine schnelle und einfache Möglichkeit, die in Teams integrierte Nutzung virtueller Termine in Ihrer Organisation anzuzeigen.

Zum Anzeigen des Berichts müssen Sie ein globaler Administrator, Teams-Administrator, globaler Leser oder Berichtsleser sein.

## <a name="view-the-report"></a>Anzeigen des Berichts

Es gibt zwei Möglichkeiten, auf den Bericht im Teams Admin Center zuzugreifen und den Bericht anzuzeigen.

- Über die [EHR-Connector-Verwendungskarte](#the-ehr-connector-usage-card) im Dashboard
- Direkt durch Auswählen von [**virtuellen EHR-Konnektoren**](#the-teams-ehr-connector-virtual-appointments-report) in **Analytics & berichte** > **Nutzungsberichte**

### <a name="the-ehr-connector-usage-card"></a>Die Verwendungskarte für denEHR-Connector

Wählen Sie im linken Navigationsbereich des Microsoft Teams Admin Centers **"Dashboard**" aus, und wechseln Sie dann zur Karte " **Virtuelle Termine" desEHR-Connectors** .

Hier erhalten Sie einen Überblick über die in TeamsEHR integrierten virtuellen Terminaktivitäten nach Monat, einschließlich abgeschlossener Termine, verbleibender Zuweisung und ob Sie das monatliche Limit überschritten haben (je nach Ihrer Lizenz).

:::image type="content" source="../../media/ehr-connector-report-card.png" alt-text="Screenshot der EHR-Connector-Nutzungskarte im Teams Admin Center-Dashboard." lightbox="../../media/ehr-connector-report-card.png":::

Wählen Sie **"Details anzeigen"** aus, um Berichtsdetails anzuzeigen. Um weitere Lizenzen zu erwerben, wählen Sie **"Weitere kaufen"** aus.

### <a name="the-teams-ehr-connector-virtual-appointments-report"></a>Der Bericht über virtuelle Termine des Teams-EHR-Connectors

1. Wechseln Sie in der linken Navigationsleiste des Teams Admin Centers zu **Analytics-& berichte** > **Nutzungsberichte**.
1. Wählen Sie auf der Registerkarte " **Berichte anzeigen** " den **EHR-Connector "Virtuelle Termine** " und einen Datumsbereich aus. Wählen Sie dann " **Bericht ausführen" aus**.

    :::image type="content" source="../../media/ehr-connector-report.png" alt-text="Screenshot des Teams EHR Connector Virtual Appointments Report im Teams Admin Center." lightbox="../../media/ehr-connector-report.png":::

#### <a name="interpret-the-report"></a>Interpretieren des Berichts

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Jeder Bericht zeigt das Datum der Generierung des Berichts und den ausgewählten Datumsbereich an.|
|**2**   |Die Tabelle enthält detaillierte Informationen zu jedem Termin, der während des ausgewählten Datumsbereichs stattgefunden hat. Denken Sie daran, dass Keine Einträge für Termine angezeigt werden, an denen weder ein Mitarbeiter noch ein Patient teilnimmt. <ul><li>**Die Startzeit (UTC)** ist das Datum und die Uhrzeit, an dem sowohl ein Mitarbeiter als auch ein Teilnehmer am Termin teilnehmen.  </li> <li>**Dauer** ist der Zeitunterschied zwischen der Startzeit und dem Zeitpunkt, zu dem die letzte Person den Termin verlässt.</li> <li>**Primär** ist der Name des Besprechungsorganisators. <li>**Die primäre E-Mail-Adresse** ist die E-Mail-Adresse des Besprechungsorganisators.</li> <li> **Abteilung** ist die Abteilungsinformationen für den Termin. Wenn die Informationen nicht ordnungsgemäß angezeigt werden, wenden Sie sich an das SUPPORT-Team der AEM. Stellen Sie für die Integration mit Epic sicher, dass ```&departmentId=%PERFDEPID;;; ; ;;NONE;%``` sie Teil des Datensatzes für die Anbieterintegration ist. </li></li> <li>**Attendants** is the total number of staff members and participants in the appointment.</li> <li>**"Innerhalb** " gibt an, ob sich der Termin innerhalb des Zuteilungslimits befindet. </li> </ul> |
|**3**   |Sie können den Bericht zur Offlineanalyse in eine CSV-Datei exportieren. Wählen Sie **"Nach Excel exportieren** " aus, um den Bericht herunterzuladen. |
|**4**   |Wählen Sie **"Filtern** " aus, um die Berichtsdetailseite zu filtern. |
|**5**   |Wählen Sie **"Vollbild"** aus, um den Bericht im Vollbildmodus anzuzeigen. |
|**6**   |Wählen Sie **"Spalten bearbeiten** " aus, um Spalten in der Tabelle hinzuzufügen oder zu entfernen. |

> [!NOTE]
> Weitere Analysen zu in Teams INTEGRIERTen virtuellen Terminen finden Sie im [Nutzungsbericht "Virtuelle Besuche"](../../teams-analytics-and-reports/virtual-visits-usage-report.md). Mit dem Nutzungsbericht für virtuelle Besuche können Sie wichtige Metriken anzeigen, z. B. Gesamttermine, Wartezeit in der Wartebereich, Termindauer und keine Anzeigen. Verwenden Sie diese Informationen, um Einblicke in Nutzungstrends zu erhalten, die Ihnen helfen, virtuelle Termine zu optimieren, um bessere Geschäftsergebnisse zu erzielen.

## <a name="related-articles"></a>Verwandte Artikel

- [Virtuelle Termine mit Teams – Integration in Cerner EHR](ehr-admin-cerner.md)
- [Virtuelle Termine mit Teams – Integration in Epic EHR](ehr-admin.md) 
