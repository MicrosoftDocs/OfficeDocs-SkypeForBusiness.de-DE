---
title: Hinzufügen und Aktualisieren von Labels zur Berichterstellung
author: tonysmit
ms.author: tonysmit
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie Berichtsbeschriftungen hinzufügen und aktualisieren, indem Sie eine Textdatei hochladen, die eine Liste der physischen Standorte und zugehörigen Subnetze enthält.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- ms.teamsadmincenter.locations.reportinglabels.overview
- ms.teamsadmincenter.voice.phonenumbers.searchacquire.tooltip.location
- ms.teamsadmincenter.locations.overview
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 189b821e7238911190c4c72c07b863fc961f3074
ms.sourcegitcommit: ab9d27d7ddd1494539ae9424de200c9d0e76a9ec
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2021
ms.locfileid: "59984610"
---
# <a name="add-and-update-reporting-labels"></a>Hinzufügen und Aktualisieren von Labels zur Berichterstellung

Berichtsbezeichnungen werden in Ihrer Organisation verwendet, um die physischen Standorte von Büros, Gebäuden oder Organisationsstandorten anzugeben. Auf der Seite Reporting Labels im Microsoft Teams Admin Center können Sie eine Textdatei (.csv oder TSV) bereitstellen, die eine Liste der physischen Standorte und der zugehörigen Netzwerksubnetze enthält. Diese Datei wird von der Anrufanalyse zum Generieren von Berichten verwendet. Wenn Sie Ihre Subnetz-Zuordnung hochladen, enthalten die Von diesen Diensten bereitgestellten Berichte auch die Standortnamen, wodurch die Berichte leichter zu verstehen und zur Behebung potenzieller Probleme zu verwenden sind.

> [!IMPORTANT]
> Von Ihnen hochgeladene Berichterstellungsbeschriftungen werden im Rahmen Ihrer Vereinbarung für Office 365  als Supportdaten behandelt, einschließlich aller Informationen, die andernfalls als Kundendaten oder persönliche *Daten betrachtet würden.*  Bitte fügen Sie keine Daten ein, die Sie Microsoft nicht als *Supportdaten* zur Verfügung stellen möchten, da diese Informationen zu Supportzwecken für Microsoft-Entwickler sichtbar sind.

Die von Ihnen bereitstellenden Berichtbeschriftungen und Speicherortdaten sind eine einzige Datenstruktur – es gibt derzeit keine Schnittstelle, über die einzelne Änderungen an den Daten möglich sind.

**So bearbeiten Sie die Tabelle mit Subnetzen und Standorten**

1. Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Center auf **Analyseanalyse& beschriftungen**  >  **erstellen**.
2. Klicken Hochladen **auf Daten speichern**.
3. Klicken Sie **Hochladen** Im Bereich Daten speichern auf Datei auswählen **,** navigieren Sie dann zu Ihrer bearbeiteten Datei .csv TSV-Datei, und laden Sie sie hoch.
4. Klicken Sie **Hochladen**.

Hier können Sie eine [Beispielvorlage herunterladen.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)

Verwenden Sie das folgende Beispiel, um die Datendatei zu erstellen.

> [!IMPORTANT]
> Ihre Datendatei sollte keine Spaltenüberschriften (z. B. Netzwerk, Netzwerkname usw.) enthalten. Diese werden hier nur zu Informationszwecken verwendet. <br>

|Netzwerk|Netzwerkname|Netzwerkbereich|Gebäudename|Besitzertyp|Gebäudetyp|Gebäudetyp Office|Stadt/Ort|PLZ|Land|Status|Region|Inside Corp|Express Route|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Bergansicht|94043|US|CA|US|1|1|
|10.0.130.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Bergansicht|94043|US|CA|US|1|1|
|10.0.131.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Bergansicht|94043|US|CA|US|1|1|
|10.0.132.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Bergansicht|94043|US|CA|US|1|1|

Weitere Informationen zum Formatieren der Datendatei finden Sie unter Dateiformat für [Mandantendaten und Erstellen einer Datendateistruktur.](CQD-upload-tenant-building-data.md#upload-building-data-file)

## <a name="related-topics"></a>Verwandte Themen

[Einrichten von Anrufanalyse](set-up-call-analytics.md)

[Verwenden der Anrufanalyse zur Problembehandlung bei schlechter Anrufqualität](use-call-analytics-to-troubleshoot-poor-call-quality.md)
