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
description: Hier erfahren Sie, wie Sie eine Textdatei hochladen, die eine Liste von physischem Standort und zugehörigen Subnetzen enthält, die als Bericht Erstellungs Etiketten für anrufanalyse-und Anruf Qualitäts Dashboard-Berichte verwendet werden.
ms.custom:
- NewAdminCenter_Update
f1keywords:
- ms.teamsadmincenter.locations.reportinglabels.overview
- ms.teamsadmincenter.voice.phonenumbers.searchacquire.tooltip.location
- ms.teamsadmincenter.locations.overview
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0519af0f9c26260f23e2a0dd9b0c60a676aa5766
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572036"
---
<a name="add-and-update-reporting-labels"></a>Hinzufügen und Aktualisieren von Labels zur Berichterstellung
============================

Bericht Erstellungs Beschriftungen werden in Ihrer Organisation verwendet, um die physischen Standorte von Büros, Gebäuden oder organisatorischen Websites anzugeben. Auf der Seite "Bericht Erstellungs Etiketten" im Microsoft Teams Admin Center können Sie eine Textdatei (CSV oder TSV) bereitstellen, die eine Liste von physikalischen Speicherorten und zugehörigen Netzwerk-Subnetzen enthält. Diese Datei wird von der anrufanalyse und dem Anruf Qualitäts Dashboard zum Generieren von Berichten verwendet. Wenn Sie Ihre Subnet-Zuordnung hochladen, enthalten die Berichte, die von diesen Diensten bereitgestellt werden, auch die Standortnamen, wodurch die Berichte verständlicher werden und zur Verdeutlichung potenzieller Probleme verwendet werden können.

Die von Ihnen bereitgestellten Berichts Beschriftungen und Speicherorte sind eine einzige Datenstruktur – derzeit ist keine Schnittstelle verfügbar, um einzelne Änderungen an den Daten vorzunehmen.

**So bearbeiten Sie die Tabelle von Subnetzen und Speicherorten**

1. Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **Speicherorte** > , an denen**Etiketten gemeldet**werden.
2. Klicken Sie auf **Daten von Speicherorten ersetzen**.
3. Klicken Sie im Bereich **Standortdaten ersetzen** auf **Datei auswählen**, und navigieren Sie dann zu der bearbeiteten CSV-oder TSV-Datei, und laden Sie Sie hoch.
4. Klicken Sie auf **hochladen**.

Sie können [hier](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)eine Beispielvorlage herunterladen.

Verwenden Sie das folgende Beispiel, um Ihre Datendatei zu erstellen.

> [!IMPORTANT]
> Ihre Datendatei darf keine Spaltenüberschriften (wie Netzwerk, Netzwerk Name usw.) enthalten. Diese werden hier nur zu Informationszwecken verwendet. <br>

|Netzwerk|Netzwerk Name|Netzwerkbereich|Gebäude Name|Besitzertyp|Gebäudetyp|Gebäude-Office-Typ|Ort|PLZ|Land|Bundesland|Region|In Corp|Express Route|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0 |SVC-1|32|USCAMTV001|Contoso vermietet Re&F|Office|Re&F|Gebirgs Ansicht|94043|USA|CA|USA|1|1|
|10.0.130.0 |SVC-1|32|USCAMTV001|Contoso vermietet Re&F|Office|Re&F|Gebirgs Ansicht|94043|USA|CA|USA|1|1|
|10.0.131.0 |SVC-1|32|USCAMTV001|Contoso vermietet Re&F|Office|Re&F|Gebirgs Ansicht|94043|USA|CA|USA|1|1|
|10.0.132.0 |SVC-1|32|USCAMTV001|Contoso vermietet Re&F|Office|Re&F|Gebirgs Ansicht|94043|USA|CA|USA|1|1|

Weitere Informationen zum Formatieren Ihrer Datendatei finden Sie unter [Mandantendaten Dateiformat und Erstellen von Datendatei Strukturen](turning-on-and-using-call-quality-dashboard.md#tenant-data-file-format-and-structure).

## <a name="related-topics"></a>Verwandte Themen

[Einrichten von Anrufanalyse](set-up-call-analytics.md)
