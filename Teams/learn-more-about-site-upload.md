---
title: Hinzufügen und Aktualisieren von Daten für Speicherorte
author: tonysmit
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie in einer Website hoch.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4d1f66c9787cb64a3026f3783b3f5de884f86a1d
ms.sourcegitcommit: a9bf4de79c84d239488455575322188a03535f71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "24013523"
---
<a name="adding-and-updating-locations-data"></a>Hinzufügen und Aktualisieren von Daten für Speicherorte
============================

Speicherorte sind in Ihrer Organisation verwendet, um die physischen Standorten des Büros, Gebäude oder Organisationseinheit Websites anzugeben. Die Seite Speicherorte gibt Administratoren die Möglichkeit, eine Textdatei (CSV oder TSV) bereitstellen, enthält eine Liste der physischen Standorten und deren zugeordneten Netzwerksubnetzen. Diese Datei wird von Analytics aufrufen, und rufen Sie Qualitätsdashboard verwendet, Berichte zu erstellen. Wenn Kunden, deren Zuordnung Subnetz hochladen, enthalten die Berichte diese Dienste die Standortnamen auch erleichtern die Berichte zu verstehen und für Korrigieren von potenzielle Probleme beim verwenden.

Die Speicherorte Daten, die Sie bereitstellen, wird eine einzelne Datenstruktur – ist derzeit kein-Schnittstelle für die einzelne Bearbeitungsaufgaben für Standortdaten durchführen. 

**So bearbeiten Sie die Tabelle mit Subnetze und Standorten**

1. Klicken Sie auf **Standorte Daten ersetzen**.
2. Klicken Sie im Bereich **Speicherort Daten ersetzen** , **Wählen Sie eine Datei aus**, klicken Sie auf und navigieren Sie zu, und Hochladen Sie der bearbeiteten CSV- oder TSV-Datei. 
3. Klicken Sie auf **Hochladen**. 


Sie können eine Beispielvorlage herunterladen [hier](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.tsv?raw=true).

Im folgende Beispiel können Sie um Ihrer Datendatei zu erstellen. 

> [!IMPORTANT]
> Die Datendatei sollte keine Spaltenüberschriften (wie Netzwerk, Netzwerkname usw.) enthalten. Diese werden hier nur zu Informationszwecken verwendet. </br>

|Netzwerk|Netzwerkname|Netzwerk-Bereich|Erstellen von Namen|Besitzertyp|Erstellen von Typ|Erstellen von Office-Typ|Ort|PLZ|Land|Bundesland|Region|Innen Corp|Express-Route|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0 |SVC-1|32|USCAMTV001|Contoso geleaste RE & F|Office|RE & F|Mountain-Ansicht|94043|USA|CA|USA|1|1|
|10.0.130.0 |SVC-1|32|USCAMTV001|Contoso geleaste RE & F|Office|RE & F|Mountain-Ansicht|94043|USA|CA|USA|1|1|
|10.0.131.0 |SVC-1|32|USCAMTV001|Contoso geleaste RE & F|Office|RE & F|Mountain-Ansicht|94043|USA|CA|USA|1|1|
|10.0.132.0 |SVC-1|32|USCAMTV001|Contoso geleaste RE & F|Office|RE & F|Mountain-Ansicht|94043|USA|CA|USA|1|1|


Weitere Informationen zum Formatieren der Datendatei finden Sie unter [Mandantendaten file Format und Erstellen von Daten-Dateistruktur](turning-on-and-using-call-quality-dashboard.md#tenant-data-file-format-and-building-data-file-structure).


## <a name="related-topics"></a>Verwandte Themen

[Einrichten von Anrufen Analytics](set-up-call-analytics.md)