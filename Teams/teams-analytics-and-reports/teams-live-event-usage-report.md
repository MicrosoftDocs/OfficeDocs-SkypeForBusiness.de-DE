---
title: Bericht zur Nutzung von Liveereignisen in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie den Bericht zur Nutzung von Liveereignissen in Teams im Microsoft Teams Admin Center verwenden, um einen Überblick über die Aktivitäten von Liveereignissen in Teams in Ihrer Organisation zu erhalten.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 971e9bc846ad1a7134c1877a1716fc535ae65e4d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809285"
---
# <a name="microsoft-teams-live-event-usage-report"></a>Bericht zur Nutzung von Liveereignisen in Microsoft Teams

Der Bericht zur Nutzung von Liveereignissen in Teams im Microsoft Teams Admin Center zeigt Ihnen eine Übersicht über die Aktivitäten für Liveereignisse in Ihrer Organisation. Sie können Nutzungsinformationen anzeigen, einschließlich Ereignisstatus, Startzeit, Ansichten und Produktionstyp für jedes Ereignis. Sie können Einblicke in Nutzungstrends erhalten und sehen, wer in Ihrer Organisation Liveereignisse plant, präsentiert und produziert.

## <a name="view-the-live-event-usage-report"></a>Anzeigen des Berichts zur Nutzung von Liveereignisen

1. Klicken Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers auf "Analysefunktionen&   >  **Verwendungsberichte.** Wählen Sie auf **der Registerkarte "Berichte anzeigen"** unter **"Bericht"** die Option **"Teams-Liveereignisnutzung" aus.**
2. Wählen **Sie unter "Datumsbereich"** einen vordefinierten Bereich aus, oder legen Sie einen benutzerdefinierten Bereich fest. Sie können einen Bereich festlegen, in dem Daten bis zu einem Jahr, sechs Monate vor und nach dem aktuellen Datum, gezeigt werden.
3. (Optional) Unter **"Organisator"** können Sie auswählen, dass nur Liveereignisse angezeigt werden, die von einem bestimmten Benutzer organisiert wurden.
4. Klicken Sie **auf "Bericht ausführen".**  

    ![Screenshot des Berichts zur Nutzung von Liveereignisen in Teams im Teams Admin Center mit Callouts](../media/teams-live-event-usage-report-with-callouts.png "Screenshot des Berichts zur Nutzung von Liveereignisen in Teams im Teams Admin Center mit Callouts")

## <a name="interpret-the-report"></a>Interpretieren des Berichts

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Im Liveereignisbericht von Teams werden die Trends über die letzten 7 Tage, 28 Tage oder einen von Ihnen festgelegten benutzerdefinierten Datumsbereich angezeigt. |
|**2**   |Jeder Bericht hat ein Datum, an dem er generiert wurde. Der Bericht spiegelt die Fast-Echtzeit-Aktivität wider, wenn die Seite aktualisiert wird. |
|**3**   |<ul><li>Die X-Achse im Diagramm stellt den ausgewählten Datumsbereich für den Bericht dar.</li> <li> Die Y-Achse ist die Gesamtansichtsanzahl.</li> </ul>Zeigen Sie an einem bestimmten Datum auf den Punkt, um die Anzahl der Ansichten für alle Liveereignisse an diesem Datum zu sehen.|
|**4**   |Die Tabelle enthält eine Aufschlüsselung der einzelnen Live-Ereignisse. <ul><li>**"Ereignis"** ist der Anzeigename des Live-Ereignisses. Klicken Sie auf den Namen des [Ereignisses, um weitere Details](#view-event-details) zum Ereignis anzuzeigen. </li> <li>**"Startzeit"** bezieht sich auf das Startdatum und die Startzeit des Ereignisses.</li> <li>**Der Ereignisstatus** zeigt an, ob das Ereignis stattgefunden hat.  </li><li>**Der** Organisator ist der Name des Ereignisorganisators.</li> <li>**Presenters** are the names of the event presenters.</li><li>**Produzenten** sind die Namen der Ereignishersteller.</li><li>**"Ansichten"** gibt die Anzahl eindeutiger Ansichten nach Abschluss des Ereignisses an.</li><li>**Die** Aufzeichnung zeigt an, ob die Aufzeichnungseinstellung ein- oder ausgeschaltet ist.</li><li>**Der Produktionstyp** zeigt an, ob das Ereignis in Teams oder von einer externen Anwendung oder einem gerät produziert wird.</li></li> </ul>Beachten Sie: Wenn in Azure AD kein Benutzerkonto mehr vorhanden ist, wird der Benutzername in der Tabelle als "--" angezeigt. <br><br>Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen. |
|**5**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen.|

## <a name="notes"></a>Hinweise
Es werden bis zu 100 Liveereignisse angezeigt, die den aktuellen Berichtskriterien entsprechen. Wenn Sie weitere Liveereignisse sehen möchten, wenden Sie Datumsfilter an, um die Listengröße zu verringern.

## <a name="view-event-details"></a>Anzeigen von Ereignisdetails

Auf der Detailseite für Liveereignis erhalten Sie eine Zusammenfassung der Details eines Live-Ereignisses, und es werden alle Dateien, einschließlich Aufzeichnungen und Aufzeichnungen, aufgeführt, die dem Ereignis zugeordnet sind. Klicken Sie auf einen Dateinamen, um die Datei anzeigen oder herunterladen zu können.

![Screenshot mit Details zu einem Liveereignis](../media/teams-live-event-usage-report-event-detail.png)

Wenn Ihre Organisation für [Strukture](https://www.hivestreaming.com/partners/integration-partners/microsoft/) eCDN oder [Kollective](https://kollective.com) eCDN aktiviert ist, können Sie zusätzliche Teilnehmeranalysen erhalten, indem Sie auf den Link für den Partnerbericht klicken.

## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)
- [Was sind Teams-Liveereignisse?](../teams-live-events/what-are-teams-live-events.md)
