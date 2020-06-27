---
title: Microsoft Teams-App-Verwendungsbericht
author: LolaJacobsen
ms.author: lolaj
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
description: Hier erfahren Sie, wie Sie den Bericht zur APP-Nutzung von Teams im Microsoft Teams Admin Center verwenden.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1a5d5c1bdb5b5bbe58ecdb90721ce24bd0081a65
ms.sourcegitcommit: a73df97a06ea860bfaf5387e0acbf3c724697e14
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "44902330"
---
# <a name="microsoft-teams-app-usage-report"></a>Microsoft Teams-App-Verwendungsbericht

Der Bericht "Teams-App-Nutzung" im Microsoft Teams Admin Center bietet Informationen darüber, welche apps Benutzer in Teams verwenden.  

## <a name="view-the-app-usage-report"></a>Anzeigen des Berichts zur APP-Nutzung

1.  Klicken Sie in der linken Navigationsleiste des Admin Centers auf <https://teams.admin.microsoft.com> **Analytics & Berichte** \> **Nutzungsberichte**. Wählen Sie auf der Registerkarte **Berichte anzeigen** unter **Bericht**die Option **apps-Verwendung**aus.

     :::image type="content" source="media/app-usage-report1.png" alt-text="Screenshot des Menüelements "Verwendungsberichte"":::

2.  Wähl Sie unter **Datumsbereich** einen Bereich aus, und klicken Sie dann auf **Bericht ausführen**.

      :::image type="content" source="media/app-usage-report2.png" alt-text="Screenshot des App-Verwendungsberichts":::

## <a name="interpret-the-report"></a>Interpretieren des Berichts

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Der Bericht "Teams-apps-Nutzung" kann für Trends in den letzten 7, 30 oder 90 Tagen angezeigt werden. |
|**2**   |Jeder Bericht hat ein Datum, an dem der Bericht generiert wurde. Die Berichte geben in der Regel eine Wartezeit von 24 Stunden ab dem Zeitpunkt wieder, zu dem eine APP geöffnet wurde. <br><br>![Screenshot des App-Verwendungsberichts mit Datumsbereichen](media/app-usage-report3.png)|
|**3**    | <ul><li>Die X-Achse in den Diagrammen ist der ausgewählte Datumsbereich für den jeweiligen Bericht.</li><li>Bei der Y-Achse handelt es sich um die Anzahl der Benutzer, die für den angegebenen Tag in einem Diagramm angezeigt werden, da diese Benutzer eine APP mindestens einmal geöffnet haben und dabei als aktiver Benutzer gelten und dem Gesamtergebnis des Mauszeigers zugerechnet werden.</li></ul>|
|**4**   |Zeigen Sie mit der Maus auf den Punkt, der eine apps-Verwendung an einem bestimmten Datum darstellt, um die Anzahl der Instanzen der aktiven Gesamtbenutzer dieser APP an diesem angegebenen Datum anzuzeigen.  |
|**5**   |Alle apps werden eingeschlossen, aber durch Auswählen des Filters-Symbols sind weitere Filter verfügbar.  |
|**6**   |Die Tabelle enthält eine Aufschlüsselung der aktiven Benutzer und Teams nach APP-Namen.<br><ul><li>**App-Name** ist der Anzeigename der in Teams verwendeten app.</li><li>**Aktive Benutzer** ist die Anzahl der Benutzer, die die APP während des angegebenen Zeitraums mindestens einmal geöffnet haben.</li><li>Der **App-Typ** ist ein statischer Wert von "Microsoft" oder "Drittanbieter".</li><li>" **Aktive Teams** " ist die Anzahl der Teams, die die APP von mindestens einem Mitglied des Teams und in den angegebenen Zeiträumen geöffnet haben.</li><li>**Publisher** ist der Softwareherausgeber der app.</li><li>**Version** ist die Software Version der APP aus dem App-Publisher.</li></ul><br>![Screenshot eines App-Verwendungsberichts](media/app-usage-report4.png)  |
|**7**  |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen.<br><br>![Screenshot der Seite "Spalten bearbeiten"](media/app-usage-report5.png)  |
|**8**  |Sie können den Bericht zur Offlineanalyse in eine CSV-Datei exportieren. Klicken Sie auf **nach Excel exportieren**, und klicken Sie dann auf der Registerkarte **Downloads** auf **herunterladen** , um den Bericht herunterzuladen, wenn er fertig ist.<br>![Screenshot der Seite "Downloads"](media/app-usage-report7.png)  |
|**9**   |Wenn Sie den Bericht in Excel anzeigen, wird auch eine **ID-** Spalte angezeigt, die die APP-ID darstellt. Eine Team-ID ist in der Regel eine alphanumerische Zeichenfolge. Wenn die Spalte " **ID** " als * * \n * * * * angezeigt wird, bedeutet dies, dass ein Benutzer die Löschung der Informationen beantragt hat.<br>![Screenshot des heruntergeladenen Excel-Berichts](media/app-usage-report8.png)  |

## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)