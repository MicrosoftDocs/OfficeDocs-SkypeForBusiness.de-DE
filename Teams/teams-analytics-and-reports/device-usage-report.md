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
description: Erfahren Sie, wie Sie den Bericht zur Gerätenutzung von Teams im Microsoft Teams Admin Center verwenden, um zu sehen, wie Benutzer in Ihrer Organisation eine Verbindung mit Teams herstellen.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1d47888884ce86bfa56546a9df600ce958380e0d
ms.sourcegitcommit: 66e7b28ba1c0433535eb6a3e7d883851c27d9d1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "51478355"
---
# <a name="microsoft-teams-device-usage-report"></a>Microsoft Teams – Gerätenutzungsbericht

Der Bericht zur Gerätenutzung von Teams im Microsoft Teams Admin Center enthält Informationen dazu, wie Benutzer eine Verbindung mit Teams herstellen. Sie können den Bericht verwenden, um die Geräte zu sehen, die in Ihrer Organisation verwendet werden, einschließlich der Nutzung von Teams von ihren mobilen Geräten, wenn sie unterwegs sind.  

## <a name="view-the-device-usage-report"></a>Anzeigen des Gerätenutzungsberichts

1. Klicken Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers auf **Analytics & Berichte**  >  **Verwendungsberichte**. Wählen Sie **auf der Registerkarte** Berichte anzeigen unter **Bericht** die Option **Gerätenutzung von Teams aus.**
2. Wähl Sie unter **Datumsbereich** einen Bereich aus, und klicken Sie dann auf **Bericht ausführen**.

    ![Screenshot des Teams-Gerätenutzungsberichts im Teams Admin Center mit Callouts](../media/teams-reports-device-usage-with-callouts.png "Screenshot des Teams-Gerätenutzungsberichts im Teams Admin Center mit Callouts")

## <a name="interpret-the-report"></a>Interpretieren des Berichts

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Der Bericht zur Gerätenutzung von Teams kann für Trends der letzten 7 Tage oder 30 Tage angezeigt werden.  |
|**2**   |Jeder Bericht verfügt über ein Datum, an dem der Bericht generiert wurde. Die Berichte geben in der Regel eine Latenz von 24 Stunden ab dem Zeitpunkt der Aktivität wieder. |
|**3**   |<ul><li>Die X-Achse im Diagramm stellt die verschiedenen Geräte **(Windows,** **Mac,** **Linux,** **iOS,** **Android Phone,** **Web)** dar, die zum Herstellen einer Verbindung mit Teams verwendet werden. </li><li>Die Y-Achse ist die Anzahl der Benutzer, die das Gerät im ausgewählten Zeitraum verwenden.</li> </ul>Zeigen Sie mit der Maus auf die Leiste, die ein Gerät darstellt, um die Anzahl der Benutzer zu sehen, die das Gerät zum Herstellen einer Verbindung mit Teams verwenden.|
|**4**   |Die Tabelle enthält eine Aufschlüsselung der Gerätenutzung nach Benutzer. <ul><li>**Benutzername** ist der Anzeigename des Benutzers. Sie können auf den Anzeigenamen klicken, um zur Einstellungsseite des Benutzers im Microsoft Teams Admin Center zu wechseln. </li><li>**Windows** ist ausgewählt, wenn der Benutzer im Desktopclient von Teams auf einem Windows-basierten Computer aktiv war.</li><li>**Mac** ist ausgewählt, wenn der Benutzer im Teams-Desktopclient auf einem macOS-Computer aktiv war. </li> <li>**Linux** ist ausgewählt, wenn der Benutzer im Desktopclient von Teams auf einem Linux-Computer aktiv war. </li> <li>**iOS** ist ausgewählt, wenn der Benutzer auf dem mobilen Teams-Client für iOS aktiv war.</li><li>**Android Phone** ist ausgewählt, wenn der Benutzer auf dem mobilen Teams-Client für Android aktiv war. <li><li>**Das Web** ist ausgewählt, wenn der Benutzer im Teams-Webclient aktiv war. <li>**Die letzte Aktivität** ist das letzte Datum (UTC), an dem der Benutzer an einer Teams-Aktivität teilgenommen hat.</li> </ul> Beachten Sie, dass, wenn in Azure AD kein Benutzerkonto mehr vorhanden ist, der Benutzername in der Tabelle als "--" angezeigt wird. <br><br>Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen. |
|**5**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen. |
|**6**   |Sie können den Bericht zur Offlineanalyse in eine CSV-Datei exportieren. Klicken **Sie auf Nach Excel** exportieren, und klicken Sie dann auf der Registerkarte **Downloads** auf **Herunterladen,** um den Bericht herunterzuladen, wenn er fertig ist.<br><br>![Screenshot der Registerkarte Downloads mit exportierten Berichten](../media/teams-reports-export-to-csv.png)|


## <a name="make-the-user-specific-data-anonymous"></a>Anonymisierter Benutzerdaten

Um die Daten in Teams-Gerätenutzungsbericht anonym zu machen, müssen Sie ein globaler Administrator sein. Dadurch werden identifizierbare Informationen wie Anzeigename, E-Mail und AAD-ID im Bericht und deren Export ausgeblendet.

1. Wechseln Sie im Microsoft 365  Admin Center zu Einstellungen für Organisationseinstellungen, und wählen Sie auf der Registerkarte Dienste \> die Option **Berichte aus.** 
    
2. Wählen **Sie Berichte** und dann anonyme **Bezeichner anzeigen aus.** Diese Einstellung wird sowohl auf die Nutzungsberichte im Microsoft 365 Admin Center als auch auf das Teams Admin Center angewendet.
  
3. Wählen **Sie Änderungen speichern aus.**

## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)
