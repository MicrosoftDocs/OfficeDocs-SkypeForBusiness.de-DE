---
title: ProgressReport-Tabelle
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
description: Fortschrittsberichte basieren auf Daten, die vom Client nach Abschluss eines Anrufs oder einer Sitzung in die Datenbank hochgeladen werden. For progress reports will be written only for calls and sessions that Skype for Business Server 2015 determines might be useful for diagnostic purposes.
ms.openlocfilehash: 6429700f902caec80db02f3db6c78420b5c108ce6a39383da8914955df16f80d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54286224"
---
# <a name="progressreport-table"></a>ProgressReport-Tabelle
 
Fortschrittsberichte basieren auf Daten, die vom Client nach Abschluss eines Anrufs oder einer Sitzung in die Datenbank hochgeladen werden. For progress reports will be written only for calls and sessions that Skype for Business Server 2015 determines might be useful for diagnostic purposes.
  
Die Felder ErrorTime, ErrorReportSeq und ProgressReportSeq beziehen sich nicht unbedingt auf Fehler, sondern auf Nachrichten, die den Status von Aufrufen oder Nachrichten angeben.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |Datum/Uhrzeit  <br/> |Primär, Fremd  <br/> |Datum und Uhrzeit des Statusfehlerberichts, der diesen Statusbericht enthält. Weitere Informationen finden Sie in der [ErrorReport-Tabelle in Skype for Business Server 2015.](errorreport.md) <br/> |
|**Errorid** <br/> |Ganzzahl  <br/> |Primär, Fremd  <br/> |Id number used in conjunction with ErrorTime, ProgressReportSeq to uniquely identify a progress report. Weitere Informationen finden Sie in der [ErrorReport-Tabelle in Skype for Business Server 2015.](errorreport.md) <br/> |
|**ErrorReportSeq** <br/> |Ganzzahl  <br/> |Primär, Fremd  <br/> |ID-Nummer, die den Fehlerbericht identifiziert. ErrorReporSeq wird in Verbindung mit ErrorTime verwendet, um einen Fehlerbericht eindeutig zu identifizieren. Weitere Informationen finden Sie in der [ErrorReport-Tabelle in Skype for Business Server 2015.](errorreport.md) <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ProgressReportSeq** <br/> |Ganzzahl  <br/> |Primary  <br/> |ID zur Identifikation des Fortschrittsberichts. Wird zusammen mit ErrorTime und ErrorReportSeq zur eindeutigen Identifikation eines Fortschrittsberichts verwendet.  <br/> |
|**MsDiagId** <br/> |Ganzzahl  <br/> ||Die Diagnose-ID des Fortschrittberichts.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SourceId** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |Server, der den Fehlerbericht gesendet hat (wenn der Bericht von einer Serverkomponente gesendet wurde). Weitere Informationen finden Sie in der [Tabelle "Server".](servers.md) Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt. <br/> |
|**Applicationid** <br/> |Ganzzahl  <br/> ||Der Lync Server-Vorgang, auf den sich der Bericht bezieht. Weitere Informationen finden Sie in der Anwendungstabelle.  <br/> |
|**Detail** <br/> |Abbildung  <br/> ||Einzelheiten über den Fortschrittsbericht, gespeichert im Binärformat, um Speicherplatz einzusparen. Diese Daten können mit der folgenden Syntax in ein Textformat konvertiert werden.  <br/> cast(cast(Detail as varbinary(max)) as varchar(max))  <br/> |
|**Telemetrie-ID** <br/> |Uniqueidentifier  <br/> ||Eindeutige ID, die Informationen zum Zeitpunkt des Konferenzbeitritts für die verschiedenen an der Konferenz beteiligten Komponenten korreliert.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SessionSetupTime** <br/> |Ganzzahl  <br/> ||Zeit (in Millisekunden) für den Konferenzbeitritt einer bestimmten Komponente.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
   

