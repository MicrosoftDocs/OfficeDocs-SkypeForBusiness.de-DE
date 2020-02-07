---
title: Microsoft Teams – Nutzungsbericht
author: LanaChin
ms.author: v-lanac
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
description: Erfahren Sie, wie Sie den Microsoft Teams-Nutzungsbericht im Microsoft Teams Admin Center verwenden, um sich einen Überblick über die Microsoft Teams-Aktivitäten in Ihrem Unternehmen zu verschaffen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3419ecb6c4ef1b976681f626fd8ec567e665d6a5
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827233"
---
# <a name="microsoft-teams-usage-report"></a>Microsoft Teams – Nutzungsbericht

Der Microsoft Teams-Nutzungsbericht im Microsoft Teams Admin Center gibt Ihnen einen Überblick über die Nutzungsaktivität in Microsoft Teams, einschließlich der Anzahl der aktiven Benutzer und Kanäle, sodass Sie schnell sehen können, wie viele Benutzer in Ihrer Organisation Microsoft Teams zur Kommunikation und Zusammenarbeit verwenden. Sie können Nutzungsinformationen für Microsoft Teams anzeigen, einschließlich der Anzahl der aktiven Benutzer und Kanäle, Gäste und Nachrichten in jedem Team.

## <a name="view-the-report"></a>Anzeigen des Berichts

1. Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **Analytics #a0 Berichte** > **Nutzungsberichte**. Wählen Sie auf der Registerkarte **Berichte anzeigen** unter **Bericht**die Option **Teams-Verwendung**aus.
2. Wähl Sie unter **Datumsbereich** einen Bereich aus, und klicken Sie dann auf **Bericht ausführen**.

    ![Screenshot des Teams-Nutzungsberichts im Team Admin Center mit Beschriftungen](../media/teams-reports-teams-usage-with-callouts.png "Screenshot des Teams-Nutzungsberichts im Team Admin Center mit Beschriftungen")

## <a name="interpret-the-report"></a>Interpretieren des Berichts

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Im Teams-Nutzungsaktivitätsbericht werden die Trends der letzten 7 ober 28 Tage angezeigt. |
|**2**   |Jeder Bericht weist das Datum auf, an dem er generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**3**   |<ul><li>Die X-Achse im Diagramm stellt den ausgewählten Datumsbereich für den Bericht dar.</li> <li> Die Y-Achse gibt die Anzahl der aktiven Elemente oder Aktivitäten an.</li> </ul>Bewegen Sie den Mauszeiger über den Punkt, der ein Element oder eine Aktivität an einem bestimmten Datum darstellt, um die Anzahl der Instanzen dieses Elements bzw. dieser Aktivität an dem bestimmten Datum anzuzeigen.|
|**4**   |Sie können filtern, was im Diagramm angezeigt wird, indem Sie in der Legende auf ein Element klicken. Klicken Sie beispielsweise auf **Gesamtzahl aktiver Benutzer**, **Teams #a0 aktiven Benutzern**, **aktiven Kanälen**oder **Nachrichten** , um nur die Informationen anzuzeigen, die sich auf die einzelnen Personen beziehen. Durch das Ändern dieser Auswahl werden die Informationen in der Tabelle nicht geändert. |
|**5**   |Die Tabelle enthält eine Aufschlüsselung der Nutzung nach Team. <ul><li>**Teamname** ist der Anzeigename des Teams. Sie können auf den Teamnamen klicken, um zur Seite Einstellungen des Teams im Microsoft Teams Admin Center zu wechseln. </li> <li>**Datenschutz** gibt an, ob es sich um ein privates oder öffentliches Team handelt.</li> <li>**Aktive Benutzer** entspricht der Anzahl der aktiven Benutzer im Team im angegebenen Zeitraum.</li><li>**Gäste** entspricht der Anzahl der Gäste im Team im angegebenen Zeitraum.</li> </li> </ul>Beachten Sie, dass der Benutzername in der Tabelle als "--" angezeigt wird, wenn ein Benutzerkonto in Azure AD nicht mehr vorhanden ist. <br><br>Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen. |
|**6**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen.|
|**7**   |Sie können den Bericht zur Offlineanalyse in eine CSV-Datei exportieren. Klicken Sie auf **nach Excel exportieren**, und klicken Sie dann auf der Registerkarte **Downloads** auf **herunterladen** , um den Bericht herunterzuladen, wenn er fertig ist.<br><br>![Screenshot der Registerkarte "Downloads" mit exportierten Berichten zum herunterladen](../media/teams-reports-export-to-csv.png)|

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)
