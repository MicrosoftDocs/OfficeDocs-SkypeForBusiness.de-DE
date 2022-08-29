---
title: Microsoft Teams-App-Nutzungsbericht
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Erfahren Sie, wie Sie den Microsoft Teams-App-Nutzungsbericht im Microsoft Teams Admin Center verwenden.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 745761b80bd2507a31cb76cdadc015eac8e9f7fd
ms.sourcegitcommit: a4a65283e85d0c393c844dfd335df0d48e0e4105
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2022
ms.locfileid: "67313927"
---
# <a name="microsoft-teams-app-usage-report"></a>Microsoft Teams-App-Nutzungsbericht

Der Microsoft Teams-App-Nutzungsbericht im Microsoft Teams Admin Center enthält Informationen darüber, welche Apps Benutzer in Teams verwenden.  

## <a name="view-the-app-usage-report"></a>Anzeigen des App-Nutzungsberichts

1. Wählen Sie im linken Navigationsbereich des Teams Admin Centers **Die Option "Analyse" & Berichte** > **["Nutzungsberichte"](https://admin.teams.microsoft.com/analytics/reports)** aus.

   :::image type="content" source="media/app-usage-report1.png" alt-text="Screenshot des Menüelements &quot;Nutzungsberichte&quot;.":::

1. Wählen Sie auf der Registerkarte " **Berichte anzeigen** " unter **"Bericht"** die Option **"App-Nutzung"** aus.

1. Wählen Sie unter **"Datumsbereich**" einen Bereich und dann " **Bericht ausführen**" aus. Sie können den Bericht "Teams-Apps-Nutzung" für Trends in den letzten 7, 30 oder 90 Tagen anzeigen.

   :::image type="content" source="media/app-usage-report2-trimmed.png" alt-text="Screenshot der Benutzeroberfläche des Berichts &quot;Apps-Verwendung&quot;." lightbox="media/app-usage-report2.png":::

## <a name="interpret-the-report"></a>Interpretieren des Berichts

:::image type="content" alt-text="Screenshot des Teams-App-Nutzungsberichts im Teams Admin Center mit Popups." source="media/app-usage-report5.png" lightbox="media/app-usage-report5.png":::

Jeder Bericht hat ein Datum oben links, das anzeigt, wann der Bericht erstellt wurde. Berichte spiegeln in der Regel eine Wartezeit von 24 Stunden ab dem Zeitpunkt des Öffnens einer App wider.

Admin Mitte stellt ein Diagramm der aktiven Benutzer und der Datumsangaben bereit. Aktive Benutzer ist die Anzahl der Benutzer, die eine App mindestens einmal während des ausgewählten Zeitraums geöffnet haben.

Zeigen Sie mit der Maus auf den Punkt (4), der die Nutzung einer App an einem beliebigen Datum darstellt, um die Gesamtzahl der aktiven Benutzer dieser App an diesem Datum anzuzeigen.

Wenn Sie andere Apps auswählen möchten, wählen Sie oben rechts das **Filtersymbol** (5) aus, wählen sie neue Kriterien aus, oder geben Sie neue Kriterien ein, und wählen Sie dann **"Übernehmen"** aus.

In der Tabelle unten im Bericht (6) werden aktive Benutzer und Teams nach App-Namen angezeigt.

   - **Der App-Name** ist der Anzeigename der in Teams verwendeten App.
   - **Aktive Benutzer** ist die Anzahl der Benutzer, die die App mindestens einmal während des angegebenen Zeitraums geöffnet haben.
   - **Der App-Typ** ist ein statischer Wert von "Microsoft" oder "Third Party".
   - **Aktive Teams** ist die Anzahl der Teams, die die App von mindestens einem Mitglied des Teams und während der angegebenen Zeiträume geöffnet haben.
   - **Publisher** ist der Softwareentwickler der App.
   - **Version** ist die Softwareversion der App vom App-Entwickler.

   > [!NOTE]
   > **Aktive Benutzer** und **aktive Teams** werden nur für Apps berechnet, die in Kanälen verwendet werden.

Um Spalten in der Tabelle hinzuzufügen oder zu entfernen, wählen Sie oben rechts das Symbol " **Spalten bearbeiten** " (7) aus, wählen Sie auf der Registerkarte " **Spalten bearbeiten** " neue Kriterien aus, und wählen Sie dann **"Übernehmen"** aus.

Um den Bericht zur Offlineanalyse in eine CSV-Datei zu exportieren, wählen Sie oben rechts das Symbol " **Nach Excel exportieren** " (8) und dann auf der Registerkarte **"Downloads** " unter **"Status**" die Option **"Herunterladen**" aus.

   :::image type="content" alt-text="Screenshot des Bereichs &quot;Downloads&quot;." source="media/app-usage-report7.png" lightbox="media/app-usage-report7.png":::

Wenn Sie den Bericht in Microsoft Excel anzeigen, wird auch eine `Id` Spalte angezeigt, die die App-ID darstellt, in der Regel eine alphanumerische Zeichenfolge. Wenn der Wert des Werts `Id` **\n** ist, bedeutet dies, dass ein Benutzer die Löschung seiner Informationen angefordert hat.

   :::image type="content" source="media/app-usage-report8.png" alt-text="Screenshot des heruntergeladenen Excel-Berichts.":::

## <a name="related-articles"></a>Verwandte Artikel

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)
