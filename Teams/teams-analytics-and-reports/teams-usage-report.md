---
title: Microsoft Teams – Nutzungsbericht
author: cichur
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kojika
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie den Microsoft Teams-Nutzungsbericht im Microsoft Teams Admin Center verwenden, um sich einen Überblick über die Microsoft Teams-Aktivitäten in Ihrem Unternehmen zu verschaffen.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: deb29f1a625d2a19e65315dbaf2a11de4ae121b3
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763013"
---
# <a name="microsoft-teams-usage-report"></a>Microsoft Teams – Nutzungsbericht

Der Microsoft Teams-Nutzungsbericht im Microsoft Teams Admin Center gibt Ihnen einen Überblick über die Nutzungsaktivität in Microsoft Teams, einschließlich der Anzahl der aktiven Benutzer und Kanäle, sodass Sie schnell sehen können, wie viele Benutzer in Ihrer Organisation Microsoft Teams zur Kommunikation und Zusammenarbeit verwenden. Sie können Nutzungsinformationen für Microsoft Teams anzeigen, einschließlich der Anzahl der aktiven Benutzer und Kanäle, Gäste und Nachrichten in jedem Team.

## <a name="view-the-usage-report"></a>Anzeigen des Verwendungsberichts

1. Klicken Sie im linken Navigationsbereich Microsoft Teams Admin Center auf **Analyseberichte &**  >  **Verwendungsberichte**. Wählen Sie **auf der Registerkarte** Berichte anzeigen unter **Bericht** die Option **Teams aus.**
2. Wähl Sie unter **Datumsbereich** einen Bereich aus, und klicken Sie dann auf **Bericht ausführen**.

    ![Screenshot des Teams Nutzungsberichts im Teams Admin Center mit Callouts.](../media/teams-reports-teams-usage-with-callouts1.png "Screenshot des Teams-Nutzungsberichts im Teams Admin Center mit Callouts")

## <a name="interpret-the-report"></a>Interpretieren des Berichts

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Im Teams Nutzungsaktivitätsbericht werden die Trends über die letzten 7 Tage, 30 oder 90 Tage angezeigt. |
|**2**   |Jeder Bericht weist das Datum auf, an dem er generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**3**   |<ul><li>Die X-Achse im Diagramm stellt den ausgewählten Datumsbereich für den Bericht dar.</li> <li> Die Y-Achse gibt die Anzahl der aktiven Elemente oder Aktivitäten an.</li> </ul>Bewegen Sie den Mauszeiger über den Punkt, der ein Element oder eine Aktivität an einem bestimmten Datum darstellt, um die Anzahl der Instanzen dieses Elements bzw. dieser Aktivität an dem bestimmten Datum anzuzeigen.|
|**4**   |Sie können filtern, was im Diagramm angezeigt wird, indem Sie in der Legende auf ein Element klicken. Klicken Sie z. **B.** auf Aktive Benutzer insgesamt ,  **Teams &** Kanäle aktive Benutzer , **Aktive** Kanäle oder Nachrichten, um nur die jeweils zugehörigen Informationen zu sehen. Durch das Ändern dieser Auswahl werden die Informationen in der Tabelle nicht geändert. |
|**5**   |Die Tabelle enthält eine Aufschlüsselung der Nutzung nach Team. <ul><li>**Teamname** ist der Anzeigename des Teams. Sie können auf den Teamnamen klicken, um zur Einstellungsseite des Teams im Microsoft Teams Admin Center zu wechseln. </li> <li>**Datenschutz** gibt an, ob es sich um ein privates oder öffentliches Team handelt.</li> <li>**Aktive Benutzer** entspricht der Anzahl der aktiven Benutzer im Team im angegebenen Zeitraum.</li><li>**Gäste** entspricht der Anzahl der Gäste im Team im angegebenen Zeitraum.</li> <li>**Aktive Kanäle** ist die Anzahl der Kanäle, die im angegebenen Zeitraum über mindestens einen aktiven Benutzer verfügen.</li> <li>**Nachrichten posten** ist die Anzahl aller Beitragnachrichten in Kanälen im angegebenen Zeitraum.</li> <li>**Antwortnachrichten** ist die Anzahl aller Antwortnachrichten in Kanälen im angegebenen Zeitraum.</li> <li>**Organisierte Besprechungen** ist die Anzahl der geplanten und Ad-hoc-Besprechungen, die ein Benutzer während des angegebenen Zeitraums organisiert hat. </li><li>**Dringende** Nachrichten ist die Anzahl aller dringenden Nachrichten im angegebenen Zeitraum.</li><li>**Reaktionen** ist die Anzahl aller Reaktionen auf Nachrichten im angegebenen Zeitraum.</li><li>**Erwähnungen** ist die Anzahl aller Erwähnungen, die im angegebenen Zeitraum in Nachrichten verwendet wurden.</li><li>**Kanalnachrichten** ist die Anzahl der eindeutigen Nachrichten, die die Benutzer des Teams während des angegebenen Zeitraums in einem Teamchat gepostet haben.</li> </li> </ul>Beachten Sie: Wenn in einer Tabelle kein Azure AD mehr vorhanden ist, wird der Benutzername in der Tabelle als "--" angezeigt. <br><br>Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen. |
|**6**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen.|
|**7**   |Sie können den Bericht zur Offlineanalyse in eine CSV-Datei exportieren. Klicken **Sie auf In Excel** exportieren, und klicken  Sie dann auf der Registerkarte **Downloads** auf Herunterladen, um den Bericht herunterzuladen, sobald er bereit ist.<br><br>![Screenshot der Registerkarte "Downloads" mit exportierten Berichten zum Herunterladen](../media/teams-reports-export-to-csv.png)|
|**8** |Die Datenpunkte der Zeitreihen im Diagramm zeigen unterschiedliche Nutzungsmetriken, die im Mandanten zusammengefasst sind.|
|**9** |Tabellarische Daten stellten unterschiedliche, pro Team zusammengefasste Nutzungsmetriken|

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)
