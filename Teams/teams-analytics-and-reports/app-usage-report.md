---
title: Bericht zur Verwendung von Microsoft Teams-Apps
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-quhur
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie den Bericht zur Verwendung der Teams-App im Microsoft Teams Admin Center verwenden.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 29e51e91cdc42000350a48dd0d83225e7791aea6
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460595"
---
# <a name="microsoft-teams-app-usage-report"></a>Bericht zur Verwendung von Microsoft Teams-Apps

Der Bericht zur Verwendung der Teams-App im Microsoft Teams Admin Center enthält Informationen dazu, welche Apps Benutzer in Teams verwenden.  

## <a name="view-the-app-usage-report"></a>Anzeigen des Berichts "App-Nutzung"

1.  Klicken Sie im linken Navigationsbereich des Admin Centers unter auf <https://admin.teams.microsoft.com> **Analytics & Berichte** \> **Verwendungsberichte**. Wählen Sie **auf der Registerkarte** Berichte anzeigen unter **Bericht** die Option **Apps-Nutzung aus.**

     :::image type="content" source="media/app-usage-report1.png" alt-text="Screenshot des Menüelements "Nutzungsberichte"":::

2.  Wähl Sie unter **Datumsbereich** einen Bereich aus, und klicken Sie dann auf **Bericht ausführen**.

      :::image type="content" source="media/app-usage-report2.png" alt-text="Screenshot des Berichts "Apps–Nutzung"":::

## <a name="interpret-the-report"></a>Interpretieren des Berichts

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Der Bericht zur Nutzung von Teams-Apps kann für Trends in den letzten 7, 30 oder 90 Tagen angezeigt werden. |
|**2**   |Jeder Bericht verfügt über ein Datum, an dem der Bericht generiert wurde. Die Berichte geben in der Regel eine Latenz von 24 Stunden ab dem Zeitpunkt des Öffnens einer App wieder. <br><br>![Screenshot des Berichts "Apps– Nutzung" mit Datumsbereichen](media/app-usage-report3.png)|
|**3**    | <ul><li>Die X-Achse in den Diagrammen ist der ausgewählte Datumsbereich für den jeweiligen Bericht.</li><li>Die Y-Achse ist die Anzahl der Benutzer, die für den angegebenen Tag im Diagramm auf eine App zeigen, mindestens einmal eine App geöffnet haben und auf diese Art als aktiver Benutzer gelten und auf die Summe auffallen, die bei der Mausbewegung zu sehen ist.</li></ul>|
|**4**   |Zeigen Sie mit der Maus auf den Punkt, der eine Nutzung von Apps an einem bestimmten Datum darstellt, um die Anzahl der Instanzen der insgesamt aktiven Benutzer dieser App an diesem angegebenen Datum zu sehen.  |
|**5**   |Alle Apps werden einbezogen, aber durch Auswählen des Symbols Filter sind weitere Filter verfügbar.  |
|**6**   |Die Tabelle enthält eine Aufschlüsselung der aktiven Benutzer und Teams nach Dem Namen der App.<br><ul><li>**Der Name der** App ist der Anzeigename der app, die in Teams verwendet wird.</li><li>**Aktive Benutzer** ist die Anzahl der Benutzer, die die App während des angegebenen Zeitraums mindestens einmal geöffnet haben.</li><li>**Der App-Typ** ist ein statischer Wert von "Microsoft" oder "Drittanbieter".</li><li>**Aktive Teams** ist die Anzahl der Teams, die die App von mindestens einem Mitglied des Teams und während der angegebenen Zeiträume geöffnet haben.</li><li>**Publisher** ist der Softwareherausgeber der App.</li><li>**Version** ist die Softwareversion der App aus dem App-Herausgeber.</li></ul><b> Hinweis:</b> Derzeit werden "Aktive Benutzer" und "Aktive Teams" nur für Apps berechnet, die nur in Kanälen verwendet werden.     

<br>![Screenshot eines Berichts zur Verwendung ](media/app-usage-report4.png)  von Apps | |**7**  | Wählen **Sie Spalten bearbeiten** aus, um Spalten in der Tabelle hinzuzufügen oder zu entfernen.<br><br>![Screenshot der Seite Spalten ](media/app-usage-report5.png)  bearbeiten | |**8**  | Sie können den Bericht zur Offlineanalyse in eine CSV-Datei exportieren. Klicken **Sie auf Nach Excel** exportieren, und klicken Sie dann auf der Registerkarte **Downloads** auf **Herunterladen,** um den Bericht herunterzuladen, wenn er fertig ist.<br>![Screenshot der Seite ](media/app-usage-report7.png)  "Downloads"**| | 9**   | Wenn Sie den Bericht in Excel anzeigen, wird auch eine Spalte **ID** angezeigt, die die App-ID darstellt. Eine Team-ID ist in der Regel eine alphanumerische Zeichenfolge. Wenn die **Spalte ID** als **\n**** angezeigt wird, bedeutet dies, dass ein Benutzer seine Informationen zum Löschen angefordert hat.<br>![Screenshot des heruntergeladenen Excel-Berichts](media/app-usage-report8.png)  |

## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)