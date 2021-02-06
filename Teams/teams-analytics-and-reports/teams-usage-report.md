---
title: Microsoft Teams – Nutzungsbericht
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kojika
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie den Microsoft Teams-Nutzungsbericht im Microsoft Teams Admin Center verwenden, um sich einen Überblick über die Microsoft Teams-Aktivitäten in Ihrem Unternehmen zu verschaffen.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 993c1b124737a0f335e9c9b1e720af72fcc88a8e
ms.sourcegitcommit: 93d84e172cb4b19acde4b8bae9b77efe96c44c00
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122255"
---
# <a name="microsoft-teams-usage-report"></a>Microsoft Teams – Nutzungsbericht

Der Microsoft Teams-Nutzungsbericht im Microsoft Teams Admin Center gibt Ihnen einen Überblick über die Nutzungsaktivität in Microsoft Teams, einschließlich der Anzahl der aktiven Benutzer und Kanäle, sodass Sie schnell sehen können, wie viele Benutzer in Ihrer Organisation Microsoft Teams zur Kommunikation und Zusammenarbeit verwenden. Sie können Nutzungsinformationen für Microsoft Teams anzeigen, einschließlich der Anzahl der aktiven Benutzer und Kanäle, Gäste und Nachrichten in jedem Team.

## <a name="view-the-usage-report"></a>Anzeigen des Nutzungsberichts

1. Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Centers auf **"Analyseanalyseberichte&**  >  **Verwendungsberichte.** Wählen Sie **auf der Registerkarte "Berichte** anzeigen" unter **"Bericht"** die Option **"Teams-Nutzung" aus.**
2. Wähl Sie unter **Datumsbereich** einen Bereich aus, und klicken Sie dann auf **Bericht ausführen**.

    ![Screenshot des Teams-Nutzungsberichts im Teams Admin Center mit Callouts](../media/teams-reports-teams-usage-with-callouts.png "Screenshot des Teams-Nutzungsberichts im Teams Admin Center mit Callouts")

## <a name="interpret-the-report"></a>Interpretieren des Berichts

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Im Bericht zu den Nutzungsaktivitäten von Teams werden die Trends über die letzten 7 Tage, 30 oder 90 Tage angezeigt. |
|**2**   |Jeder Bericht weist das Datum auf, an dem er generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**3**   |<ul><li>Die X-Achse im Diagramm stellt den ausgewählten Datumsbereich für den Bericht dar.</li> <li> Die Y-Achse gibt die Anzahl der aktiven Elemente oder Aktivitäten an.</li> </ul>Bewegen Sie den Mauszeiger über den Punkt, der ein Element oder eine Aktivität an einem bestimmten Datum darstellt, um die Anzahl der Instanzen dieses Elements bzw. dieser Aktivität an dem bestimmten Datum anzuzeigen.|
|**4**   |Sie können filtern, was im Diagramm angezeigt wird, indem Sie in der Legende auf ein Element klicken. Klicken Sie beispielsweise auf "Aktive Benutzer **insgesamt",**  **"Teams" &**"Aktive Benutzer", **"Aktive** Kanäle" oder "Nachrichten", um nur die jeweils zugehörigen Informationen zu sehen. Durch das Ändern dieser Auswahl werden die Informationen in der Tabelle nicht geändert. |
|**5**   |Die Tabelle enthält eine Aufschlüsselung der Nutzung nach Team. <ul><li>**Der Teamname** ist der Anzeigename des Teams. Sie können auf den Teamnamen klicken, um zur Seite "Einstellungen" des Teams im Microsoft Teams Admin Center zu wechseln. </li> <li>**Datenschutz** gibt an, ob es sich um ein privates oder öffentliches Team handelt.</li> <li>**Aktive Benutzer** entspricht der Anzahl der aktiven Benutzer im Team im angegebenen Zeitraum.</li><li>**Gäste** entspricht der Anzahl der Gäste im Team im angegebenen Zeitraum.</li> <li>**Bei aktiven** Kanälen handelt es sich um die Anzahl der Kanäle, die im angegebenen Zeitraum über mindestens einen aktiven Benutzer verfügen.</li> <li>**"Nachrichten** posten" ist die Anzahl aller Beiträge in Kanälen im angegebenen Zeitraum.</li> <li>**"Antwortnachrichten"** ist die Anzahl aller Antwortnachrichten in Kanälen im angegebenen Zeitraum.</li> <li>**Bei organisierten** Besprechungen handelt es sich um die Anzahl der geplanten und ad-hoc-Besprechungen, die ein Benutzer während des angegebenen Zeitraums organisiert hat. </li><li>**"Dringende** Nachrichten" ist die Anzahl aller dringenden Nachrichten im angegebenen Zeitraum.</li><li>**"Reaktionen"** gibt die Anzahl aller Reaktionen auf Nachrichten im angegebenen Zeitraum an.</li><li>**Erwähnungen** ist die Anzahl aller Erwähnungen, die in Nachrichten im angegebenen Zeitraum verwendet wurden.</li><li>**Bei Kanalnachrichten** handelt es sich um die Anzahl der eindeutigen Nachrichten, die die Benutzer des Teams während des angegebenen Zeitraums in einem Teamchat gepostet haben.</li> </li> </ul>Beachten Sie, dass, wenn ein Benutzerkonto in Azure AD nicht mehr vorhanden ist, der Benutzername in der Tabelle als "--" angezeigt wird. <br><br>Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen. |
|**6**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen.|
|**7**   |Sie können den Bericht zur Offlineanalyse in eine CSV-Datei exportieren. Klicken **Sie auf "Nach Excel exportieren",** und klicken Sie dann auf der Registerkarte "Downloads" auf **"Herunterladen",** um den Bericht herunterzuladen, wenn er bereit ist. <br><br>![Screenshot der Registerkarte "Downloads" mit exportierten Berichten zum Herunterladen](../media/teams-reports-export-to-csv.png)|

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)
