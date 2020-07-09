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
description: Sie erfahren, wie Sie Berichts Etiketten hinzufügen und aktualisieren können, indem Sie eine Textdatei hochladen, die eine Liste mit physikalischen Speicherorten und zugehörigen Subnetzen enthält.
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
ms.openlocfilehash: 1b32e9db020b3498e8185b4d38e25d1d9a1feca5
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085291"
---
<a name="add-and-update-reporting-labels"></a>Hinzufügen und Aktualisieren von Labels zur Berichterstellung
============================

Bericht Erstellungs Beschriftungen werden in Ihrer Organisation verwendet, um die physischen Standorte von Büros, Gebäuden oder organisatorischen Websites anzugeben. Auf der Seite "Bericht Erstellungs Etiketten" im Microsoft Teams Admin Center können Sie eine Textdatei (CSV oder TSV) bereitstellen, die eine Liste von physikalischen Speicherorten und zugehörigen Netzwerk-Subnetzen enthält. Diese Datei wird von der anrufanalyse zum Generieren von Berichten verwendet. Wenn Sie Ihre Subnet-Zuordnung hochladen, enthalten die Berichte, die von diesen Diensten bereitgestellt werden, auch die Standortnamen, wodurch die Berichte verständlicher werden und zur Verdeutlichung potenzieller Probleme verwendet werden können.

> [!IMPORTANT]
> Von Ihnen hochgeladene Bericht Erstellungs Etiketten werden unter ihrer Vereinbarung für Office 365 als *Support Daten* behandelt, einschließlich aller Informationen, die andernfalls als *Kundendaten* oder *persönliche Daten*gelten. Bitte fügen Sie keine Daten ein, die Sie Microsoft nicht als *Support Daten*zur Verfügung stellen möchten, da diese Informationen von Microsoft-Ingenieuren zu Supportzwecken angezeigt werden.

Die von Ihnen bereitgestellten Berichts Beschriftungen und Speicherorte sind eine einzige Datenstruktur – derzeit ist keine Schnittstelle verfügbar, um einzelne Änderungen an den Daten vorzunehmen.

**So bearbeiten Sie die Tabelle von Subnetzen und Speicherorten**

1. Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **Speicherorte**, an denen  >  **Etiketten gemeldet**werden.
2. Klicken Sie auf **Daten von Speicherorten ersetzen**.
3. Klicken Sie im Bereich **Datenspeicherorte ersetzen** auf **Datei auswählen**, und navigieren Sie dann zu der bearbeiteten CSV-oder TSV-Datei, und laden Sie Sie hoch.
4. Klicken Sie auf **hochladen**.

Sie können [hier](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)eine Beispielvorlage herunterladen.

Verwenden Sie das folgende Beispiel, um Ihre Datendatei zu erstellen.

> [!IMPORTANT]
> Ihre Datendatei darf keine Spaltenüberschriften (wie Netzwerk, Netzwerk Name usw.) enthalten. Diese werden hier nur zu Informationszwecken verwendet. <br>

|Netzwerk|Netzwerk Name|Netzwerkbereich|Gebäude Name|Besitzertyp|Gebäudetyp|Gebäude-Office-Typ|Stadt/Ort|PLZ|Land|Status|Region|In Corp|Express Route|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0    |SVC-1|32|USCAMTV001|Contoso vermietet Re&F|Office|Re&F|Gebirgs Ansicht|94043|US|CA|US|1|1|
|10.0.130.0    |SVC-1|32|USCAMTV001|Contoso vermietet Re&F|Office|Re&F|Gebirgs Ansicht|94043|US|CA|US|1|1|
|10.0.131.0    |SVC-1|32|USCAMTV001|Contoso vermietet Re&F|Office|Re&F|Gebirgs Ansicht|94043|US|CA|US|1|1|
|10.0.132.0    |SVC-1|32|USCAMTV001|Contoso vermietet Re&F|Office|Re&F|Gebirgs Ansicht|94043|US|CA|US|1|1|

Weitere Informationen zum Formatieren Ihrer Datendatei finden Sie unter [Mandantendaten Dateiformat und Erstellen von Datendatei Strukturen](CQD-upload-tenant-building-data.md#upload-building-data-file).

## <a name="related-topics"></a>Verwandte Themen

[Einrichten von Anrufanalyse](set-up-call-analytics.md)
