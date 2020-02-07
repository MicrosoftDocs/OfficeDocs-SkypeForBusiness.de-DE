---
title: Microsoft Teams – Gerätenutzungsbericht
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
description: Hier erfahren Sie, wie Sie im Microsoft Teams Admin Center den Bericht "Geräteverwendung für Teams" verwenden, um zu sehen, wie Benutzer in Ihrer Organisation mit Teams verbunden sind.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 16abf763579a542583f3aafa30252c1423759641
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827353"
---
# <a name="microsoft-teams-device-usage-report"></a>Microsoft Teams – Gerätenutzungsbericht

Der Bericht "Teams-Gerätenutzung" im Microsoft Teams Admin Center bietet Informationen dazu, wie Benutzer eine Verbindung mit Teams herstellen. Sie können den Bericht verwenden, um die Geräte anzuzeigen, die in Ihrer Organisation verwendet werden, einschließlich der Anzahl der Verwendung von Teams auf Ihren mobilen Geräten, wenn Sie unterwegs sind.  

## <a name="view-the-report"></a>Anzeigen des Berichts

1. Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **Analytics #a0 Berichte** > **Nutzungsberichte**. Wählen Sie auf der Registerkarte **Berichte anzeigen** unter **Bericht**die Option **Teams-Gerätenutzung**aus.
2. Wähl Sie unter **Datumsbereich** einen Bereich aus, und klicken Sie dann auf **Bericht ausführen**.

    ![Screenshot des Teams-Geräte Nutzungsberichts im Team Admin Center mit Beschriftungen](../media/teams-reports-device-usage-with-callouts.png "Screenshot des Teams-Geräte Nutzungsberichts im Team Admin Center mit Beschriftungen")

## <a name="interpret-the-report"></a>Interpretieren des Berichts

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Der Bericht "Geräteverwendung für Teams" kann für Trends in den letzten 7 Tagen oder 28 Tagen angezeigt werden.  |
|**2**   |Jeder Bericht hat ein Datum, an dem der Bericht generiert wurde. Die Berichte weisen in der Regel eine Latenz von 24 bis 48 Stunden ab dem Zeitpunkt der Aktivität auf. |
|**3**   |<ul><li>Die X-Achse im Diagramm steht für die verschiedenen Geräte (**Windows**, **Mac**, **Linux**, **IOS**, **Android-Telefon**), die für die Verbindung zu Teams verwendet werden. </li><li>Bei der Y-Achse handelt es sich um die Anzahl der Benutzer, die das Gerät über den ausgewählten Zeitraum verwenden.</li> </ul>Zeigen Sie mit der Maus auf die Leiste, die ein Gerät darstellt, um die Anzahl der Benutzer anzuzeigen, die das Gerät zum Herstellen einer Verbindung mit Teams verwenden.|
|**4**   |Die Tabelle zeigt eine Aufschlüsselung der Gerätenutzung durch den Benutzer. <ul><li>**Anzeigename** ist der Anzeigename des Benutzers. Sie können auf den Anzeigenamen klicken, um zur Einstellungsseite des Benutzers im Microsoft Teams Admin Center zu wechseln. </li><li>**Windows** ist ausgewählt, wenn der Benutzer im Desktop Client von Teams auf einem Windows-basierten Computer aktiv war.</li><li>**Mac** ist ausgewählt, wenn der Benutzer im Desktop Client von Teams auf einem macOS-Computer aktiv war. </li> <li>**Linux** ist ausgewählt, wenn der Benutzer im Team-Desktop Client auf einem Linux-Computer aktiv war. </li> <li>**IOS** ist ausgewählt, wenn der Benutzer auf dem mobilen Team-Client für IOS aktiv war.</li><li>**Android-Telefon** ist ausgewählt, wenn der Benutzer auf dem mobilen Team-Client für Android aktiv war. <li>**Letzte Aktivität** ist das letzte Datum (UTC), an dem der Benutzer an einer Team Aktivität teilgenommen hat.</li> </ul> Beachten Sie, dass der Benutzername in der Tabelle als "--" angezeigt wird, wenn ein Benutzerkonto in Azure AD nicht mehr vorhanden ist. <br><br>Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen. |
|**5**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen. |
|**6**   |Sie können den Bericht zur Offlineanalyse in eine CSV-Datei exportieren. Klicken Sie auf **nach Excel exportieren**, und klicken Sie dann auf der Registerkarte **Downloads** auf **herunterladen** , um den Bericht herunterzuladen, wenn er fertig ist.<br><br>![Screenshot der Registerkarte "Downloads" mit exportierten Berichten](../media/teams-reports-export-to-csv.png)|

## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)