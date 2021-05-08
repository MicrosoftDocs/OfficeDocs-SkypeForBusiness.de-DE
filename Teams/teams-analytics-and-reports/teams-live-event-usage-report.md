---
title: Microsoft Teams bericht zur Nutzung von Liveereignisen
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
description: Erfahren Sie, wie Sie Teams Bericht zur Nutzung von Liveereignissen im Microsoft Teams Admin Center verwenden, um einen Überblick über Teams Aktivitäten von Liveereignissen in Ihrer Organisation zu erhalten.
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
# <a name="microsoft-teams-live-event-usage-report"></a>Microsoft Teams bericht zur Nutzung von Liveereignisen

Der Teams Bericht zur Nutzung von Liveereignissen im Microsoft Teams Admin Center zeigt Ihnen die Aktivitätsübersicht für Liveereignisse, die in Ihrer Organisation abgehalten werden. Sie können Nutzungsinformationen wie Ereignisstatus, Startzeit, Ansichten und Produktionstyp für jedes Ereignis anzeigen. Sie können Einblicke in Nutzungstrends erhalten und sehen, wer in Ihrer Organisation Liveereignisse plant, präsentiert und produziert.

## <a name="view-the-live-event-usage-report"></a>Anzeigen des Berichts zur Nutzung von Liveereignisen

1. Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Center auf **Analyseberichte &**  >  **Verwendungsberichte**. Wählen Sie **auf der Registerkarte** Berichte anzeigen unter Bericht die Option **Teams** Verwendung **von Liveereignis aus.**
2. Wählen **Sie unter Datumsbereich** einen vordefinierten Bereich aus, oder legen Sie einen benutzerdefinierten Bereich fest. Sie können einen Bereich festlegen, um Daten bis zu einem Jahr, sechs Monate vor und nach dem aktuellen Datum, anzeigen zu können.
3. (Optional) Unter **Organisator** können Sie auswählen, dass nur Liveereignisse angezeigt werden, die von einem bestimmten Benutzer organisiert wurden.
4. Klicken **Sie auf Bericht ausführen.**  

    ![Screenshot des berichts Teams Liveereignisnutzung im Teams Admin Center mit Callouts](../media/teams-live-event-usage-report-with-callouts.png "Screenshot des berichts Teams Liveereignisnutzung im Teams Admin Center mit Callouts")

## <a name="interpret-the-report"></a>Interpretieren des Berichts

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Im bericht Teams Liveereignis werden die Trends über die letzten 7 Tage, 28 Tage oder einen von Ihnen festgelegten benutzerdefinierten Datumsbereich angezeigt. |
|**2**   |Jeder Bericht hat das Datum, an dem er generiert wurde. Der Bericht spiegelt die nahezu Echtzeitaktivität wider, wenn die Seite aktualisiert wird. |
|**3**   |<ul><li>Die X-Achse im Diagramm stellt den ausgewählten Datumsbereich für den Bericht dar.</li> <li> Die Y-Achse ist die Gesamtansichtsanzahl.</li> </ul>Zeigen Sie an einem bestimmten Datum auf den Punkt, um die Anzahl der Ansichten aller Liveereignisse an diesem Datum zu sehen.|
|**4**   |Die Tabelle enthält eine Aufschlüsselung der einzelnen Live-Ereignisse. <ul><li>**Ereignis** ist der Anzeigename des Live-Ereignisses. Klicken Sie auf den Namen des [Ereignisses, um weitere Details](#view-event-details) zum Ereignis anzuzeigen. </li> <li>**Startzeit** bezieht sich auf das Startdatum und die Startzeit des Ereignisses.</li> <li>**Der Ereignisstatus** zeigt an, ob das Ereignis stattgefunden hat.  </li><li>**Der** Organisator ist der Name des Ereignisorganisators.</li> <li>**Moderatoren** sind die Namen der Ereignis-Presenter.</li><li>**Produzenten** sind die Namen der Ereignis produzenten.</li><li>**Ansichten** ist die Anzahl der eindeutigen Ansichten nach Abschluss des Ereignisses.</li><li>**Bei der** Aufzeichnung wird gezeigt, ob die Aufzeichnungseinstellung ein- oder ausgeschaltet ist.</li><li>**Der Produktionstyp** zeigt an, ob das Ereignis in einer Teams oder von einer externen Anwendung oder einem gerät produziert wird.</li></li> </ul>Wenn in Azure AD kein Benutzerkonto mehr vorhanden ist, wird der Benutzername in der Tabelle als "--" angezeigt. <br><br>Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen. |
|**5**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen.|

## <a name="notes"></a>Hinweise
Es werden bis zu 100 Liveereignisse angezeigt, die den kriterien des aktuellen Berichts entsprechen. Wenn Sie weitere Liveereignisse sehen möchten, wenden Sie Datumsfilter an, um die Listengröße zu verringern.

## <a name="view-event-details"></a>Anzeigen von Ereignisdetails

Auf der Detailseite für ein Liveereignis erhalten Sie eine Zusammenfassung der Details eines Live-Ereignisses sowie alle Dateien, einschließlich Aufzeichnungen und Aufzeichnungen, die mit dem Ereignis verknüpft sind. Klicken Sie auf einen Dateinamen, um die Datei anzeigen oder herunterladen zu können.

![Screenshot mit Details zu einem Liveereignis](../media/teams-live-event-usage-report-event-detail.png)

Wenn Ihre Organisation für [Strukture](https://www.hivestreaming.com/partners/integration-partners/microsoft/) eCDN oder [Kollective](https://kollective.com) eCDN aktiviert ist, können Sie zusätzliche Teilnehmeranalysen erhalten, indem Sie auf den Link für den Partnerbericht klicken.

## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)
- [Was sind Teams-Liveereignisse?](../teams-live-events/what-are-teams-live-events.md)
