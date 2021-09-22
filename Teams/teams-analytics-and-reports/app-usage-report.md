---
title: Microsoft Teams der App-Verwendung
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-quhur
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie Teams Bericht zur App-Verwendung im Microsoft Teams Admin Center verwenden.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fcf56c69824d1926a61b7fe09afc4e0d7cf474d9
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58730844"
---
# <a name="microsoft-teams-app-usage-report"></a>Microsoft Teams der App-Verwendung

Der Teams Bericht zur App-Verwendung im Microsoft Teams Admin Center enthält Informationen darüber, welche Apps Benutzer in Teams.  

## <a name="view-the-app-usage-report"></a>Anzeigen des Berichts "App-Verwendung"

1.  Klicken Sie im linken Navigationsbereich des Admin Centers unter <https://admin.teams.microsoft.com> auf **Analyseberichte &** \> **Verwendungsberichte**. Wählen Sie **auf der Registerkarte** Berichte anzeigen unter **Bericht** die Option **Apps-Verwendung aus.**

     :::image type="content" source="media/app-usage-report1.png" alt-text="Screenshot des Menüelements Verwendungsberichte.":::

2.  Wähl Sie unter **Datumsbereich** einen Bereich aus, und klicken Sie dann auf **Bericht ausführen**.

      :::image type="content" source="media/app-usage-report2.png" alt-text="Screenshot des Berichts Apps-Nutzung.":::

## <a name="interpret-the-report"></a>Interpretieren des Berichts

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Im bericht Teams Apps-Nutzung werden die Trends über die letzten 7, 30 oder 90 Tage angezeigt. |
|**2**   |Jeder Bericht hat das Datum, an dem der Bericht generiert wurde. Die Berichte zeigen in der Regel eine Latenz von 24 Stunden ab dem Zeitpunkt des Öffnens einer App. <br><br>![Screenshot des Berichts "Apps-Nutzung" mit Datumsbereichen](media/app-usage-report3.png)|
|**3**    | <ul><li>Die X-Achse in den Diagrammen ist der ausgewählte Datumsbereich für den jeweiligen Bericht.</li><li>Die Y-Achse ist die Anzahl der Benutzer, die für den angegebenen Tag mit dem Mauszeiger in einem Diagramm auf eine App zeigen. Diese Benutzer haben eine App mindestens einmal geöffnet und werden dadurch als aktiver Benutzer betrachtet und fallen in Richtung des Gesamtwerts an, der beim Zeigen mit der Maus angezeigt wird.</li></ul>|
|**4**   |Zeigen Sie an einem bestimmten Datum auf den Punkt, der eine App-Nutzung darstellt, um die Anzahl der Instanzen der gesamten aktiven Benutzer der App an diesem angegebenen Datum zu sehen.  |
|**5**   |Alle Apps werden einbezogen, aber wenn Sie das Filter-Symbol auswählen, sind weitere Filter verfügbar.  |
|**6**   |Die Tabelle enthält eine Aufschlüsselung der aktiven Benutzer und Teams nach App-Namen.<br><ul><li>**App-Name** ist der Anzeigename der App, die in der App Teams.</li><li>**Aktive Benutzer** ist die Anzahl der Benutzer, die die App im angegebenen Zeitraum mindestens einmal geöffnet haben.</li><li>**Der App-Typ** ist ein statischer Wert von "Microsoft" oder "Drittanbieter".</li><li>**Aktive Teams** ist die Anzahl der Teams, die die App von mindestens einem Mitglied des Teams und während der angegebenen Zeiträume geöffnet haben.</li><li>**Publisher** ist der Softwareherausgeber der App.</li><li>**Version** ist die Softwareversion der App vom App-Herausgeber.</li></ul><b> Hinweis:</b> Derzeit werden "Aktive Benutzer" und "Aktive Teams" nur für Apps berechnet, die nur in Kanälen verwendet werden.     

<br>![Screenshot eines Berichts "Apps-Nutzung".](media/app-usage-report4.png)  | | **7**  | Wählen **Sie Spalten bearbeiten aus,** um Spalten in der Tabelle hinzuzufügen oder zu entfernen.<br><br>![Screenshot der Seite "Spalten bearbeiten"](media/app-usage-report5.png)  | | **8**  | Sie können den Bericht zur Offlineanalyse in eine CSV-Datei exportieren. Klicken **Sie auf Excel** Exportieren, und klicken Sie  dann auf der Registerkarte **Downloads** auf Herunterladen, um den Bericht herunterzuladen, wenn er bereit ist.<br>![Screenshot der Seite "Downloads".](media/app-usage-report7.png)  | | **9** | Wenn Sie den Bericht in einer Excel, wird auch eine **ID-Spalte** angezeigt, die die App-ID darstellt. Eine Team-ID ist in der Regel eine alphanumerische Zeichenfolge. Wenn die **Spalte ID** als **\n**** angezeigt wird, bedeutet dies, dass ein Benutzer seine Informationen zum Löschen angefordert hat.<br>![Screenshot des heruntergeladenen Excel Berichts](media/app-usage-report8.png)  |

## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)