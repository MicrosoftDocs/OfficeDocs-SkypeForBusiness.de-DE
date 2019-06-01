---
title: Hinzufügen und Aktualisieren von Standortdaten
author: tonysmit
ms.author: tonysmit
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Hier erfahren Sie, wie Sie auf eine Website hochladen.
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.locations.overview
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6e7e9211b207c008de22fe86ae0c7bb6c9f9ac51
ms.sourcegitcommit: 1336f6c182043016c42660d5f21632d82febb658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "34667482"
---
<a name="adding-and-updating-locations-data"></a>Hinzufügen und Aktualisieren von Standortdaten
============================

In Ihrer Organisation werden Standorte verwendet, um die physischen Standorte von Büros, Gebäuden oder organisatorischen Websites anzugeben. Auf der Seite "Orte" können Administratoren eine Textdatei (CSV oder TSV) bereitstellen, die eine Liste mit physikalischen Speicherorten und zugehörigen Netzwerk-Subnetzen enthält. Diese Datei wird von der anrufanalyse und dem Anruf Qualitäts Dashboard zum Generieren von Berichten verwendet. Wenn Kunden ihre Subnet-Zuordnung hochladen, enthalten die Berichte, die von diesen Diensten bereitgestellt werden, auch die Standortnamen, wodurch die Berichte verständlicher werden und zur Verdeutlichung potenzieller Probleme verwendet werden können.

Die von Ihnen bereitgestellten Positionsdaten sind eine einzige Datenstruktur – derzeit steht keine Schnittstelle zur Verfügung, um einzelne Änderungen an Standortdaten vorzunehmen. 

**So bearbeiten Sie die Tabelle von Subnetzen und Speicherorten**

1. Klicken Sie auf **Daten von Speicherorten ersetzen**.
2. Klicken Sie im Bereich **Standortdaten ersetzen** auf **Datei auswählen**, und navigieren Sie dann zu der bearbeiteten CSV-oder TSV-Datei, und laden Sie Sie hoch. 
3. Klicken Sie auf **hochladen**. 


Sie können [hier](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)eine Beispielvorlage herunterladen.

Mit dem folgenden Beispiel können Sie Ihre Datendatei erstellen. 

> [!IMPORTANT]
> Ihre Datendatei darf keine Spaltenüberschriften (wie Netzwerk, Netzwerk Name usw.) enthalten. Diese werden hier nur zu Informationszwecken verwendet. </br>

|Netzwerk|Netzwerk Name|Netzwerkbereich|Gebäude Name|Besitzertyp|Gebäudetyp|Gebäude-Office-Typ|Ort|PLZ|Land|Bundesland|Region|In Corp|Express Route|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0 |SVC-1|32|USCAMTV001|Contoso vermietet Re&F|Office|Re&F|Gebirgs Ansicht|94043|USA|CA|USA|1|1|
|10.0.130.0 |SVC-1|32|USCAMTV001|Contoso vermietet Re&F|Office|Re&F|Gebirgs Ansicht|94043|USA|CA|USA|1|1|
|10.0.131.0 |SVC-1|32|USCAMTV001|Contoso vermietet Re&F|Office|Re&F|Gebirgs Ansicht|94043|USA|CA|USA|1|1|
|10.0.132.0 |SVC-1|32|USCAMTV001|Contoso vermietet Re&F|Office|Re&F|Gebirgs Ansicht|94043|USA|CA|USA|1|1|


Weitere Informationen zum Formatieren Ihrer Datendatei finden Sie unter [Mandantendaten Dateiformat und Erstellen von Datendatei Strukturen](turning-on-and-using-call-quality-dashboard.md#tenant-data-file-format-and-structure).


## <a name="related-topics"></a>Verwandte Themen

[Einrichten von Anrufanalyse](set-up-call-analytics.md)
