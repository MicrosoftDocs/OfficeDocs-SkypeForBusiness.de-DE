---
title: Microsoft Teams – Gerätenutzungsbericht
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
description: Erfahren Sie, wie Sie den Bericht "Teams-Gerätenutzung" im Microsoft Teams Admin Center verwenden, um zu sehen, wie Benutzer in Ihrer Organisation eine Verbindung mit Teams herstellen.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 292632972396f5d4300fa2526f01e69a5555ff45
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815645"
---
# <a name="microsoft-teams-device-usage-report"></a>Microsoft Teams – Gerätenutzungsbericht

Im Bericht zur Gerätenutzung von Microsoft Teams im Microsoft Teams Admin Center finden Sie Informationen dazu, wie Benutzer sich mit Teams verbinden. Sie können den Bericht verwenden, um die Geräte zu sehen, die in Ihrer Organisation verwendet werden, einschließlich der Nutzung von Teams von ihren mobilen Geräten, wenn Sie unterwegs sind.  

## <a name="view-the-device-usage-report"></a>Anzeigen des Gerätenutzungsberichts

1. Klicken Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers auf "Analysefunktionen&   >  **Verwendungsberichte.** Wählen Sie auf **der Registerkarte "Berichte anzeigen"** unter **"Bericht"** die Option **"Teams-Gerätenutzung" aus.**
2. Wähl Sie unter **Datumsbereich** einen Bereich aus, und klicken Sie dann auf **Bericht ausführen**.

    ![Screenshot des Teams-Gerätenutzungsberichts im Teams Admin Center mit Callouts](../media/teams-reports-device-usage-with-callouts.png "Screenshot des Teams-Gerätenutzungsberichts im Teams Admin Center mit Callouts")

## <a name="interpret-the-report"></a>Interpretieren des Berichts

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Im Bericht zur Gerätenutzung in Teams werden die Trends über die letzten 7 Tage oder 30 Tage angezeigt.  |
|**2**   |Jeder Bericht hat ein Datum, an dem der Bericht generiert wurde. Die Berichte zeigen in der Regel eine Latenz von 24 Stunden ab dem Zeitpunkt der Aktivität an. |
|**3**   |<ul><li>Die X-Achse im Diagramm stellt die verschiedenen Geräte **(Windows,** **Mac,** **Linux,** **iOS,** **Android Phone,** **Web)** dar, die zum Herstellen einer Verbindung mit Teams verwendet werden. </li><li>Die Y-Achse gibt die Anzahl der Benutzer an, die das Gerät im ausgewählten Zeitraum verwenden.</li> </ul>Zeigen Sie auf die Leiste, die ein Gerät darstellt, um die Anzahl der Benutzer zu sehen, die das Gerät zum Herstellen einer Verbindung mit Teams verwenden.|
|**4**   |Die Tabelle enthält eine Aufschlüsselung der Gerätenutzung nach Benutzer. <ul><li>**"Benutzername"** ist der Anzeigename des Benutzers. Sie können auf den Anzeigenamen klicken, um zur Einstellungsseite des Benutzers im Microsoft Teams Admin Center zu wechseln. </li><li>**Windows** ist ausgewählt, wenn der Benutzer auf einem Windows-basierten Computer im Desktopclient von Teams aktiv war.</li><li>**Mac** ist ausgewählt, wenn der Benutzer im Teams-Desktopclient auf einem macOS-Computer aktiv war. </li> <li>**Linux** ist ausgewählt, wenn der Benutzer auf einem Linux-Computer im Teams-Desktopclient aktiv war. </li> <li>**iOS** ist ausgewählt, wenn der Benutzer im mobilen Client von Teams für iOS aktiv war.</li><li>**Android Phone ist** ausgewählt, wenn der Benutzer auf dem mobilen Client von Teams für Android aktiv war. <li><li>**Das Web** ist ausgewählt, wenn der Benutzer im Webclient von Teams aktiv war. <li>**Die letzte Aktivität** ist das letzte Datum (UTC), an dem der Benutzer an einer Teamaktivität teilgenommen hat.</li> </ul> Beachten Sie: Wenn in Azure AD kein Benutzerkonto mehr vorhanden ist, wird der Benutzername in der Tabelle als "--" angezeigt. <br><br>Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen. |
|**5**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen. |
|**6**   |Sie können den Bericht zur Offlineanalyse in eine CSV-Datei exportieren. Klicken **Sie auf "Nach Excel exportieren",** und klicken Sie dann auf der Registerkarte **"Downloads"** auf "Herunterladen", um den Bericht herunterzuladen, sobald er bereit ist. <br><br>![Screenshot der Registerkarte "Downloads" mit exportierten Berichten](../media/teams-reports-export-to-csv.png)|

## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)
