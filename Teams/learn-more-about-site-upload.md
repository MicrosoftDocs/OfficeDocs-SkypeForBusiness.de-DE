---
title: Hinzufügen und Aktualisieren von Labels zur Berichterstellung
author: tonysmit
ms.author: tonysmit
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Normal
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
ms.openlocfilehash: 4a1af7f14695d1f933a9c3902b373eb668044e24
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918641"
---
<a name="add-and-update-reporting-labels"></a>Hinzufügen und Aktualisieren von Labels zur Berichterstellung
============================

Berichterstellungsbeschriftungen werden in Ihrer Organisation verwendet, um die physischen Standorte von Büros, Gebäuden oder Organisationsstandorten anzugeben. Auf der Seite "Berichterstellungsbeschriftungen" im Microsoft Teams Admin Center können Sie eine Textdatei (CSV oder TSV) bereitstellen, die eine Liste der physischen Standorte und der zugehörigen Netzwerksubnetze enthält. Diese Datei wird von der Anrufanalyse zum Generieren von Berichten verwendet. Wenn Sie Ihre Subnetzzuordnung hochladen, enthalten die von diesen Diensten bereitgestellten Berichte auch die Standortnamen, wodurch die Berichte einfacher zu verstehen und zur Behebung potenzieller Probleme zu verwenden sind.

> [!IMPORTANT]
> Von Ihnen hochgeladene Berichterstellungsbeschriftungen werden im Rahmen Ihrer Vereinbarung für Office 365 als Supportdaten behandelt, einschließlich aller Informationen, die andernfalls als Kundendaten oder persönliche *Daten betrachtet würden.*   Bitte geben Sie keine Daten an, die Sie Microsoft nicht als *Supportdaten* zur Verfügung stellen möchten, da diese Informationen zu Supportzwecken für die Microsoft Engineers sichtbar sind.

Die von Ihnen bereitstellenden Berichtbeschriftungen und -speicherorte sind eine einzige Datenstruktur – es gibt derzeit keine Schnittstelle, über die einzelne Änderungen an den Daten möglich sind.

**So bearbeiten Sie die Tabelle mit Subnetzen und Standorten**

1. Klicken Sie im linken Navigationsbereich des Microsoft Teams Admin Centers auf die **Beschriftungen für die**  >  **Standortberichte.**
2. Klicken Sie **auf "Speicherorte ersetzen".**
3. Klicken Sie **im Bereich "Speicherorte** ersetzen" auf "Datei **auswählen",** navigieren Sie dann zu Ihrer bearbeiteten CSV- oder TSV-Datei, und laden Sie sie hoch.
4. Klicken Sie **auf "Hochladen".**

Hier können Sie eine [Beispielvorlage herunterladen.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)

Verwenden Sie das folgende Beispiel, um die Datendatei zu erstellen.

> [!IMPORTANT]
> Ihre Datendatei sollte keine Spaltenüberschriften (z. B. "Netzwerk", "Netzwerkname" usw.) enthalten. Diese werden hier nur zu Informationszwecken verwendet. <br>

|Netzwerk|Netzwerkname|Netzwerkbereich|Gebäudename|Besitzertyp|Gebäudetyp|Building Office Type|Stadt/Ort|PLZ|Land|Status|Region|Inside Corp|ExpressRoute|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Mountain View|94043|US|CA|US|1|1|
|10.0.130.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Mountain View|94043|US|CA|US|1|1|
|10.0.131.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Mountain View|94043|US|CA|US|1|1|
|10.0.132.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Mountain View|94043|US|CA|US|1|1|

Weitere Informationen zum Formatieren der Datendatei finden Sie unter "Dateiformat der [Mandantendaten" und "Gebäudedatendateistruktur".](CQD-upload-tenant-building-data.md#upload-building-data-file)

## <a name="related-topics"></a>Verwandte Themen

[Einrichten von Anrufanalyse](set-up-call-analytics.md)

[Verwenden der Anrufanalyse zur Problembehandlung bei schlechter Anrufqualität](use-call-analytics-to-troubleshoot-poor-call-quality.md)
