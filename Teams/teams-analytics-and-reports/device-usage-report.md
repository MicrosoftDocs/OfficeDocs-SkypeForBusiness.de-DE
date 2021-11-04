---
title: Microsoft Teams – Gerätenutzungsbericht
author: cichur
ms.author: v-mahoffman
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
description: Erfahren Sie, wie Sie Teams Bericht zur Gerätenutzung im Microsoft Teams Admin Center verwenden, um zu sehen, wie Benutzer in Ihrer Organisation eine Verbindung mit Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 261a25cd998243c205424dd1a403166e03e1d921
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749574"
---
# <a name="microsoft-teams-device-usage-report"></a>Microsoft Teams – Gerätenutzungsbericht

Der Teams Bericht zur Gerätenutzung im Microsoft Teams Admin Center enthält Informationen dazu, wie Benutzer eine Verbindung mit Ihrem Teams. Sie können den Bericht verwenden, um die Geräte zu sehen, die in Ihrer Organisation verwendet werden, einschließlich der Teams von ihren mobilen Geräten, wenn Sie unterwegs sind.  

## <a name="view-the-device-usage-report"></a>Anzeigen des Geräteverwendungsberichts

1. Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Center auf **Analyseberichte &**  >  **Verwendungsberichte**. Wählen Sie **auf der Registerkarte** Berichte anzeigen unter **Bericht** die Option **Teams aus.**
2. Wähl Sie unter **Datumsbereich** einen Bereich aus, und klicken Sie dann auf **Bericht ausführen**.

    ![Screenshot des Berichts Teams Geräteverwendungsberichts im Teams Admin Center mit Callouts.](../media/teams-reports-device-usage-with-callouts.png "Screenshot des Berichts Teams Geräteverwendungsberichts im Teams Admin Center mit Callouts")

## <a name="interpret-the-report"></a>Interpretieren des Berichts

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Im Teams Bericht zur Gerätenutzung werden die Trends über die letzten 7 oder 30 Tage angezeigt.  |
|**2**   |Jeder Bericht hat das Datum, an dem der Bericht generiert wurde. Die Berichte zeigen in der Regel eine Latenz von 24 Stunden ab dem Zeitpunkt der Aktivität. |
|**3**   |<ul><li>Die X-Achse im Diagramm stellt die verschiedenen Geräte dar **(Windows**, **Mac,** **Linux,** **iOS,** **Android Telefon,** **Web**), die zum Herstellen einer Verbindung mit Teams. </li><li>Die Y-Achse gibt die Anzahl der Benutzer an, die das Gerät im ausgewählten Zeitraum verwenden.</li> </ul>Zeigen Sie mit der Maus auf die Leiste, die ein Gerät darstellt, um die Anzahl der Benutzer zu sehen, die das Gerät zum Herstellen einer Verbindung Teams.|
|**4**   |Die Tabelle enthält eine Aufschlüsselung der Gerätenutzung nach Benutzer. <ul><li>**Benutzername** ist der Anzeigename des Benutzers. Sie können auf den Anzeigenamen klicken, um zur Einstellungsseite des Benutzers im admin center Microsoft Teams zu wechseln. </li><li>**Windows** ist ausgewählt, wenn der Benutzer im Teams-Desktopclient auf einem Windows Computer aktiv war.</li><li>**Mac** ist ausgewählt, wenn der Benutzer im Desktopclient für Teams auf einem macOS-Computer aktiv war. </li> <li>**Linux** ist ausgewählt, wenn der Benutzer auf einem Linux-Computer im Teams-Desktopclient aktiv war. </li> <li>**iOS** ist ausgewählt, wenn der Benutzer auf dem mobilen Teams für iOS aktiv war.</li><li>**Android-Smartphone** ist ausgewählt, wenn der Benutzer auf dem mobilen Teams für Android aktiv war. <li><li>**Web** ist ausgewählt, wenn der Benutzer im Webclient Teams aktiv war. <li>**Letzte Aktivität** ist das letzte Datum (UTC), an dem der Benutzer an einer Aktivität Teams teilgenommen hat.</li> </ul> Beachten Sie: Wenn in einer Tabelle kein Azure AD mehr vorhanden ist, wird der Benutzername in der Tabelle als "--" angezeigt. <br><br>Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen. |
|**5**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen. |
|**6**   |Sie können den Bericht zur Offlineanalyse in eine CSV-Datei exportieren. Klicken **Sie auf In Excel** exportieren, und klicken  Sie dann auf der Registerkarte **Downloads** auf Herunterladen, um den Bericht herunterzuladen, sobald er bereit ist.<br><br>![Screenshot der Registerkarte "Downloads" mit exportierten Berichten](../media/teams-reports-export-to-csv.png)|


## <a name="make-the-user-specific-data-anonymous"></a>Anonymisiert benutzerspezifische Daten

Um die Daten in Teams Geräteverwendungsbericht anonym zu machen, müssen Sie ein globaler Administrator sein. Dadurch werden identifizierbare Informationen wie Anzeigename, E-Mail-Adresse und AAD-ID im Bericht und beim Export ausgeblendet.

1. Wechseln Microsoft 365 Admin Center In diesem Fenster  zum Einstellungen \> **Organisations-Einstellungen**, und  wählen Sie unter Registerkarte Dienste die Option Berichte **aus.**
    
2. Wählen **Sie Berichte** aus, und wählen Sie dann **anonyme Bezeichner anzeigen aus.** Diese Einstellung wird sowohl auf die Verwendungsberichte in Microsoft 365 Admin Center als Teams Admin Center angewendet.
  
3. Wählen Sie **Änderungen speichern aus.**

## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)
