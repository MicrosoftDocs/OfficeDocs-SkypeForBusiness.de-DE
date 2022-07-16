---
title: Microsoft Teams – Nutzungsbericht
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.openlocfilehash: 3770d3e45e75808d8dc92e139c1886f6623df922
ms.sourcegitcommit: 4c4f2f220832cae3efb3f6f3c74795300d661295
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2022
ms.locfileid: "66825539"
---
# <a name="microsoft-teams-usage-report"></a>Microsoft Teams – Nutzungsbericht

Der Microsoft Teams-Nutzungsbericht im Microsoft Teams Admin Center gibt Ihnen einen Überblick über die Nutzungsaktivität in Microsoft Teams, einschließlich der Anzahl der aktiven Benutzer und Kanäle, sodass Sie schnell sehen können, wie viele Benutzer in Ihrer Organisation Microsoft Teams zur Kommunikation und Zusammenarbeit verwenden. Sie können Nutzungsinformationen für Microsoft Teams anzeigen, einschließlich der Anzahl der aktiven Benutzer und Kanäle, Gäste und Nachrichten in jedem Team.

## <a name="view-the-usage-report"></a>Anzeigen des Nutzungsberichts

1. Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Centers auf **"Analyse" & Berichte** > **"Nutzungsberichte"**. Wählen Sie auf der Registerkarte " **Berichte anzeigen** " unter **"Bericht"** die Option " **Teams-Nutzung"** aus.
2. Wähl Sie unter **Datumsbereich** einen Bereich aus, und klicken Sie dann auf **Bericht ausführen**.

    ![Screenshot des Teams-Nutzungsberichts im Teams Admin Center mit Popups.](../media/teams-reports-teams-usage-with-callouts1.png "Screenshot des Teams-Nutzungsberichts im Teams Admin Center mit Popups")

## <a name="interpret-the-report"></a>Interpretieren des Berichts

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Der Teams-Nutzungsaktivitätsbericht kann nach Trends in den letzten 7 Tagen, 30 oder 90 Tagen angezeigt werden. |
|**2**   |Jeder Bericht weist das Datum auf, an dem er generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**3**   |<ul><li>Die X-Achse im Diagramm stellt den ausgewählten Datumsbereich für den Bericht dar.</li> <li> Die Y-Achse gibt die Anzahl der aktiven Elemente oder Aktivitäten an.</li> </ul>Bewegen Sie den Mauszeiger über den Punkt, der ein Element oder eine Aktivität an einem bestimmten Datum darstellt, um die Anzahl der Instanzen dieses Elements bzw. dieser Aktivität an dem bestimmten Datum anzuzeigen.|
|**4**   |Sie können filtern, was im Diagramm angezeigt wird, indem Sie in der Legende auf ein Element klicken. Klicken Sie z. B. auf  **"Aktive Benutzer insgesamt**", **"Teams & Aktive Kanäle**",  **"Aktive Kanäle**" oder **"Nachrichten** ", um nur die jeweils zugehörigen Informationen anzuzeigen. Durch das Ändern dieser Auswahl werden die Informationen in der Tabelle nicht geändert. |
|**5**   |Die Tabelle enthält eine Aufschlüsselung der Nutzung nach Team. <ul><li>**Der Teamname** ist der Anzeigename des Teams. Sie können auf den Teamnamen klicken, um zur Einstellungsseite des Teams im Microsoft Teams Admin Center zu wechseln. </li> <li>**Datenschutz** gibt an, ob es sich um ein privates oder öffentliches Team handelt.</li> <li>**Aktive Benutzer** entspricht der Anzahl der aktiven Benutzer im Team im angegebenen Zeitraum.</li><li>**Gäste** entspricht der Anzahl der Gäste im Team im angegebenen Zeitraum.</li> <li>**Aktive Kanäle** ist die Anzahl der Kanäle, die mindestens einen aktiven Benutzer im angegebenen Zeitraum haben.</li> <li>**Post Messages** ist die Anzahl aller Postnachrichten in Kanälen im angegebenen Zeitraum.</li> <li>**Antwortnachrichten** ist die Anzahl aller Antwortnachrichten in Kanälen im angegebenen Zeitraum.</li> <li>**Besprechungen organisiert** ist die Anzahl der geplanten und Ad-hoc-Besprechungen, die ein Benutzer während des angegebenen Zeitraums organisiert hat. </li><li>**Dringende Nachrichten** sind die Anzahl aller dringenden Nachrichten im angegebenen Zeitraum.</li><li>**Reaktionen** ist die Anzahl aller Reaktionen auf Nachrichten im angegebenen Zeitraum.</li><li>**Erwähnungen** ist die Anzahl aller Erwähnungen, die in Nachrichten im angegebenen Zeitraum verwendet werden.</li><li>**Kanalnachrichten** sind die Anzahl eindeutiger Nachrichten, die die Benutzer des Teams während des angegebenen Zeitraums in teamchats gepostet haben.</li> </li> </ul>Beachten Sie, dass, wenn kein Team mehr vorhanden ist, der Name in der Tabelle als "--" angezeigt wird. <br><br>Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen. |
|**6**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen.|
|**7**   |Sie können den Bericht zur Offlineanalyse in eine CSV-Datei exportieren. Klicken Sie auf **"Nach Excel exportieren**", und klicken Sie dann auf der Registerkarte " **Downloads** " auf " **Herunterladen** ", um den Bericht herunterzuladen, wenn er fertig ist.<br><br>![Screenshot der Registerkarte "Downloads" mit exportierten Berichten, die heruntergeladen werden sollen.](../media/teams-reports-export-to-csv.png)|
|**8** |Zeitreihen-Datenpunkte im Diagramm zeigen verschiedene Nutzungsmetriken an, die auf dem Mandanten aggregiert werden|
|**9** |Tabellarische Daten stellten verschiedene Nutzungsmetriken dar, die pro Team aggregiert wurden|

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)
