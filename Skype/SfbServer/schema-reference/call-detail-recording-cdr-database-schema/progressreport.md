---
title: ProgressReport-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
description: Fortschrittsbericht basieren auf Daten, die vom Client in der Datenbank nach Abschluss eines Anrufs oder einer Sitzung hochgeladen werden. Fortschrittsberichte geschrieben werden nur für anrufen und Sitzungen, die Skype für Business Server 2015 bestimmt um zu Diagnosezwecken hilfreich sein können.
ms.openlocfilehash: 3ed5805b74a242003d8ce910fa5a01538789d626
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930595"
---
# <a name="progressreport-table"></a>ProgressReport-Tabelle
 
Fortschrittsbericht basieren auf Daten, die vom Client in der Datenbank nach Abschluss eines Anrufs oder einer Sitzung hochgeladen werden. Fortschrittsberichte geschrieben werden nur für anrufen und Sitzungen, die Skype für Business Server 2015 bestimmt um zu Diagnosezwecken hilfreich sein können.
  
Die Felder ErrorTime, ErrorReportSeq und ProgressReportSeq verweisen nicht notwendigerweise auf Fehler, sondern auf Nachrichten, die den Status von Anrufen oder Nachrichten angeben.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**"ErrorTime"** <br/> |datetime  <br/> |Primär, Fremd  <br/> |Datum und Uhrzeit des Fehlerberichts ausgeführt, die diese Fortschrittsbericht enthält. [ErrorReport-Tabelle in Skype für Business Server 2015](errorreport.md) Weitere Informationen finden Sie. <br/> |
|**Fehler-ID** <br/> |int  <br/> |Primär, Fremd  <br/> |ID-Nummer, die in Verbindung mit "ErrorTime", "progressreportseq" verweisen, um einen Fortschrittsbericht eindeutig zu identifizieren. [ErrorReport-Tabelle in Skype für Business Server 2015](errorreport.md) Weitere Informationen finden Sie. <br/> |
|**"Errorreportseq"** <br/> |int  <br/> |Primär, Fremd  <br/> |ID-Nummer, die den Fehlerbericht identifiziert. ErrorReporSeq wird in Verbindung mit ErrorTime verwendet, um einen Fehlerbericht eindeutig zu identifizieren. [ErrorReport-Tabelle in Skype für Business Server 2015](errorreport.md) Weitere Informationen finden Sie <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**"Progressreportseq" verweisen** <br/> |int  <br/> |Primary  <br/> |ID-Nummer, um den Bericht zu identifizieren. In Verbindung mit "ErrorTime" und "errorreportseq" verwendet, um einen Fortschrittsbericht eindeutig zu identifizieren.  <br/> |
|**MsDiagId** <br/> |int  <br/> ||Diagnose-ID des fortschrittberichts.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SourceId** <br/> |int  <br/> |Ausländisch  <br/> |Server, die den Fehlerbericht gesendet (wenn der Bericht von einer Serverkomponente gesendet wurde). Finden Sie weitere Informationen der [Server-Tabelle](servers.md) . Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt. <br/> |
|**ApplicationId** <br/> |int  <br/> ||Die Lync Server-Prozess, dem der Bericht zu ist. Siehe Tabelle Anwendung Weitere Informationen.  <br/> |
|**Detail** <br/> |Bild  <br/> ||Einzelheiten über den Fortschrittsbericht, gespeichert im Binärformat, um Speicherplatz einzusparen. Diese Daten können mit der folgenden Syntax Textformat konvertiert werden:  <br/> CAST (Cast (Detail as varbinary(max)) as varchar(max))  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||Eindeutige ID, die korreliert Uhrzeitinformationen für die verschiedenen Komponenten in einer Konferenz beteiligten teilnehmen.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Zeit (in Millisekunden) für eine bestimmte Komponente an einer Konferenz teilzunehmen.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
   

