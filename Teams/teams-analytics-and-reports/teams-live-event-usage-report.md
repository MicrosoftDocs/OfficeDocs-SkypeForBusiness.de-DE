---
title: Microsoft Teams-Bericht zur Nutzung von Liveereignissen
author: CarolynRowe
ms.author: crowe
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie den Nutzungsbericht zu Teams-Liveereignissen im Microsoft Teams Admin Center verwenden, um einen Überblick über die Aktivitäten von Teams-Liveereignissen in Ihrer Organisation zu erhalten.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 29a255c9248f07db00d4295e99d4062116ca4e76
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794093"
---
# <a name="microsoft-teams-live-event-usage-report"></a>Microsoft Teams-Bericht zur Nutzung von Liveereignissen

Der Teams-Bericht zur Nutzung von Liveereignissen im Microsoft Teams Admin Center zeigt Ihnen die Aktivitätsübersicht für Liveereignisse in Ihrer Organisation. Sie können Nutzungsinformationen anzeigen, einschließlich Ereignisstatus, Startzeit, Ansichten und Produktionstyp für jedes Ereignis. Sie können Einblicke in Nutzungstrends erhalten und sehen, wer in Ihrer Organisation Liveereignisse plant, präsentiert und produziert.

## <a name="view-the-live-event-usage-report"></a>Anzeigen des Nutzungsberichts für Liveereignisse

1. Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Centers auf **"Analyse" & Berichte** > **"Nutzungsberichte"**. Wählen Sie auf der Registerkarte " **Berichte anzeigen** " unter **"Bericht"** die **Teams-Liveereignisnutzung** aus.
2. Wählen Sie unter **"Datumsbereich**" einen vordefinierten Bereich aus, oder legen Sie einen benutzerdefinierten Bereich fest. Sie können einen Bereich so festlegen, dass Daten bis zu einem Jahr, sechs Monate vor und nach dem aktuellen Datum angezeigt werden.
3. (Optional) Unter **"Organisator**" können Sie auswählen, dass nur Liveereignisse angezeigt werden sollen, die von einem bestimmten Benutzer organisiert werden.
4. Klicken Sie auf **"Bericht ausführen"**.  

   :::image type="content" alt-text="Screenshot des Teams-Liveereignis-Nutzungsberichts im Teams Admin Center mit Popups." source="../media/teams-live-event-usage-report-with-callouts.png" lightbox="../media/teams-live-event-usage-report-with-callouts.png":::

## <a name="interpret-the-report"></a>Interpretieren des Berichts

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Der Teams-Liveereignisbericht kann nach Trends in den letzten 7 Tagen, 28 Tagen oder einem von Ihnen festgelegten benutzerdefinierten Datumsbereich angezeigt werden. |
|**2**   |Jeder Bericht hat ein Datum für die Generierung. Der Bericht spiegelt nahezu Echtzeitaktivitäten wider, wenn die Seite aktualisiert wird. |
|**3**   |<ul><li>Die X-Achse im Diagramm stellt den ausgewählten Datumsbereich für den Bericht dar.</li> <li> Die Y-Achse ist die Gesamtansichtsanzahl.</li> </ul>Zeigen Sie auf den Punkt an einem bestimmten Datum, um die Anzahl der Ansichten für alle Liveereignisse an diesem Datum anzuzeigen.|
|**4**   |In der Tabelle finden Sie eine Aufschlüsselung der einzelnen Liveereignisse. <ul><li>**Ereignis** ist der Anzeigename des Liveereignisses. Klicken Sie auf den Namen des Ereignisses, um [weitere Details](#view-event-details) zum Ereignis zu erhalten. </li> <li>**Die Startzeit** bezieht sich auf das Startdatum und die Startzeit des Ereignisses.</li> <li>**Der Ereignisstatus** zeigt an, ob das Ereignis stattgefunden hat.  </li><li>**Organisator** ist der Name des Ereignisorganisators.</li> <li>**Referenten** sind die Namen der Ereignisreferenten.</li><li>**Produzenten** sind die Namen der Ereignisproduzenten.</li><li>**Ansichten** ist die Anzahl der eindeutigen Ansichten, nachdem das Ereignis abgeschlossen wurde.</li><li>**Die Aufzeichnung** zeigt an, ob die Einstellung für die Aufzeichnung aktiviert oder deaktiviert ist.</li><li>**Der Produktionstyp** zeigt an, ob das Ereignis in Teams oder von einer externen Anwendung oder einem externen Gerät erstellt wird.</li></li> </ul>Wenn ein Benutzerkonto in Azure AD nicht mehr vorhanden ist, wird der Benutzername in der Tabelle als "--" angezeigt. <br><br>Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen. |
|**5**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen.|

## <a name="notes"></a>Hinweise
Es werden bis zu 100 Liveereignisse angezeigt, die den aktuellen Berichtskriterien entsprechen. Um weitere Liveereignisse anzuzeigen, wenden Sie Datumsfilter an, um die Listengröße zu verringern.

Anonyme Referenten werden nicht in den Bericht einbezogen.

Jeder, der die Aufzeichnung des Ereignisses oder des Ereignisses bei Bedarf überwacht, wird nicht in die Ansichtsanzahl einbezogen. 

## <a name="view-event-details"></a>Anzeigen von Ereignisdetails

Die Detailseite des Liveereignisses enthält eine Zusammenfassung der Details eines Liveereignisses und listet alle Dateien auf, einschließlich Transkriptionen und Aufzeichnungen, die dem Ereignis zugeordnet sind. Klicken Sie auf einen Dateinamen, um die Datei anzuzeigen oder herunterzuladen.

:::image type="content" alt-text="Screenshot mit Details eines Liveereignisses." source="../media/teams-live-event-usage-report-event-detail.png" lightbox="../media/teams-live-event-usage-report-event-detail.png":::

Wenn Ihre Organisation für [Hive](https://www.hivestreaming.com/partners/integration-partners/microsoft/) eCDN oder [Kollective](https://kollective.com) eCDN aktiviert ist, können Sie zusätzliche Teilnehmeranalysen erhalten, indem Sie auf den Partnerberichtslink klicken.

## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)
- [Was sind Microsoft Teams-Liveereignisse?](../teams-live-events/what-are-teams-live-events.md)
