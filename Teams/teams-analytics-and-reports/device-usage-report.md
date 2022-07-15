---
title: Microsoft Teams – Gerätenutzungsbericht
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Erfahren Sie, wie Sie den Microsoft Teams-Gerätenutzungsbericht im Microsoft Teams Admin Center verwenden, um zu sehen, wie Benutzer in Ihrer Organisation eine Verbindung mit Teams herstellen.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 949ad172425f5e02da2fa67078193b198cb987d1
ms.sourcegitcommit: 4c4f2f220832cae3efb3f6f3c74795300d661295
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2022
ms.locfileid: "66825509"
---
# <a name="microsoft-teams-device-usage-report"></a>Microsoft Teams – Gerätenutzungsbericht

Der Microsoft Teams-Gerätenutzungsbericht im Microsoft Teams Admin Center enthält Informationen dazu, wie Benutzer eine Verbindung mit Teams herstellen. Sie können den Bericht verwenden, um die Geräte anzuzeigen, die in Ihrer Organisation verwendet werden, einschließlich der Anzahl der Benutzer, die Teams von ihren mobilen Geräten aus verwenden, wenn Sie unterwegs sind.  

## <a name="view-the-device-usage-report"></a>Anzeigen des Gerätenutzungsberichts

1. Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Centers auf **"Analyse" & Berichte** > **"Nutzungsberichte"**. Wählen Sie auf der Registerkarte " **Berichte anzeigen** " unter **"Bericht"** die Option " **Teams-Gerätenutzung"** aus.
2. Wähl Sie unter **Datumsbereich** einen Bereich aus, und klicken Sie dann auf **Bericht ausführen**.

    ![Screenshot des Teams-Gerätenutzungsberichts im Teams Admin Center mit Popups.](../media/teams-reports-device-usage-with-callouts.png "Screenshot des Teams-Gerätenutzungsberichts im Teams Admin Center mit Popups")

## <a name="interpret-the-report"></a>Interpretieren des Berichts

|Beschriftung |Beschreibung  |
|--------|-------------|
|**1**   |Der Teams-Gerätenutzungsbericht kann nach Trends in den letzten 7 Tagen oder 30 Tagen angezeigt werden.  |
|**2**   |Jeder Bericht hat ein Datum, an dem der Bericht generiert wurde. Die Berichte spiegeln in der Regel eine Wartezeit von 24 Stunden ab dem Zeitpunkt der Aktivität wider. |
|**3**   |<ul><li>Die X-Achse im Diagramm stellt die verschiedenen Geräte (**Windows**, **Mac**, **Linux**, **iOS**, **Android Phone**, **Web**) dar, die zum Herstellen einer Verbindung mit Teams verwendet werden. </li><li>Die Y-Achse ist die Anzahl der Benutzer, die das Gerät im ausgewählten Zeitraum verwenden.</li> </ul>Zeigen Sie mit der Maus auf die Leiste, die ein Gerät darstellt, um die Anzahl der Benutzer anzuzeigen, die das Gerät zum Herstellen einer Verbindung mit Teams verwenden.|
|**4**   |In der Tabelle finden Sie eine Aufschlüsselung der Gerätenutzung nach Benutzer. <ul><li>**Benutzername** ist der Anzeigename des Benutzers. Sie können auf den Anzeigenamen klicken, um zur Einstellungsseite des Benutzers im Microsoft Teams Admin Center zu wechseln. </li><li>**Windows** ist ausgewählt, wenn der Benutzer im Teams-Desktopclient auf einem Windows-basierten Computer aktiv war.</li><li>**Mac** ist ausgewählt, wenn der Benutzer im Teams-Desktopclient auf einem macOS-Computer aktiv war. </li> <li>**Linux** ist ausgewählt, wenn der Benutzer im Teams-Desktopclient auf einem Linux-Computer aktiv war. </li> <li>**iOS** ist ausgewählt, wenn der Benutzer auf dem mobilen Microsoft Teams-Client für iOS aktiv war.</li><li>**Das Android-Smartphone** ist ausgewählt, wenn der Benutzer auf dem mobilen Microsoft Teams-Client für Android aktiv war. <li><li>**Das Web** wird ausgewählt, wenn der Benutzer im Teams-Webclient aktiv war. <li>**Die letzte Aktivität** ist das letzte Datum (UTC), an dem der Benutzer an einer Teams-Aktivität teilgenommen hat.</li> </ul> Wenn ein Benutzerkonto in Azure AD nicht mehr vorhanden ist, wird der Benutzername in der Tabelle als "--" angezeigt. <br><br>Um in der Tabelle die gewünschten Informationen anzuzeigen, stellen Sie sicher, dass Sie der Tabelle die entsprechenden Spalten hinzufügen. |
|**5**   |Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen. |
|**6**   |Sie können den Bericht zur Offlineanalyse in eine CSV-Datei exportieren. Klicken Sie auf **"Nach Excel exportieren**", und klicken Sie dann auf der Registerkarte " **Downloads** " auf " **Herunterladen** ", um den Bericht herunterzuladen, wenn er fertig ist.<br><br>![Screenshot der Registerkarte "Downloads" mit exportierten Berichten.](../media/teams-reports-export-to-csv.png)|


## <a name="make-the-user-specific-data-anonymous"></a>Anonymisieren der benutzerspezifischen Daten

Um die Daten im Teams-Gerätenutzungsbericht anonym zu machen, müssen Sie ein globaler Administrator sein. Dadurch werden identifizierbare Informationen wie Anzeigename, E-Mail und AAD-ID im Bericht und deren Export ausgeblendet.

1. Wechseln Sie in Microsoft 365 Admin Center zu den **Organisationseinstellungen "Einstellungen**\>", und wählen Sie auf der Registerkarte "**Dienste**" die Option "**Berichte**" aus.
    
2. Wählen Sie **"Berichte**" und dann " **Anonyme Bezeichner anzeigen" aus**. Diese Einstellung wird sowohl auf die Nutzungsberichte in Microsoft 365 Admin Center als auch auf das Teams Admin Center angewendet.
  
3. Wählen Sie **"Änderungen speichern" aus**.

## <a name="related-topics"></a>Verwandte Themen

- [Teams – Analyse und Berichterstellung](teams-reporting-reference.md)
