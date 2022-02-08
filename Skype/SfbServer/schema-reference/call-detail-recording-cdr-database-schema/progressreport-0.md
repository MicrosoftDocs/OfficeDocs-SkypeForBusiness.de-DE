---
title: ProgressReport-Ansicht
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: Die ProgressReport-Ansicht speichert Informationen über abgeschlossene Sitzungen. Fortschrittsberichte werden nur für Anrufe geschrieben und für Sitzungen, die Lync Server 2013 als hilfreich für Diagnosezwecke ermittelt. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: c9a7d093cea7388f66129b94233e29c6e25f21ae
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2022
ms.locfileid: "62392267"
---
# <a name="progressreport-view"></a>ProgressReport-Ansicht
 
Die ProgressReport-Ansicht speichert Informationen über abgeschlossene Sitzungen. Fortschrittsberichte werden nur für Anrufe geschrieben und für Sitzungen, die Lync Server 2013 als hilfreich für Diagnosezwecke ermittelt. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
> [!NOTE]
> Die Felder ErrorTime, ErrorReportSeq und ProgressReportSeq beziehen sich nicht unbedingt auf Fehler, sondern auf Nachrichten, die den Status von Aufrufen oder Nachrichten angeben. 
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |Datum/Uhrzeit  <br/> |Zeitpunkt des Fehlers. Wird zusammen mit "ErrorReportSeq" verwendet, um einen Fehler eindeutig zu bestimmen.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |ID-Nummer zum Bestimmen des Fehlers. Wird zusammen mit "ErrorTime" verwendet, um einen Fehler eindeutig zu bestimmen.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |ID zum Bestimmen des Fortschrittsberichts. Wird zum Unterscheiden von Fortschrittsberichten desselben Fehlerberichts verwendet.  <br/> |
|**MsDiagId** <br/> |int  <br/> |Diagnose-ID für den Fehlerbericht.  <br/> |
|**Source** <br/> |nvarchar(256)  <br/> |Name des Servers, von dem der Fehler stammt (wenn der Bericht von einer Serverkomponente gesendet wurde).  <br/> |
|**Application** <br/> |nvarchar(256)  <br/> |Name der Anwendung, von der der Fehler stammt (wenn der Bericht von einer Serverkomponente gesendet wurde).  <br/> |
|**Telemetrie-ID** <br/> |Uniqueidentifier  <br/> |Eindeutiger Bezeichner, der die Informationen über den Zeitpunkt des Beitritts für verschiedene in einer Konferenz beteiligten Komponenten korreliert.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> |Für eine bestimmte Komponente erforderliche Zeit (in Millisekunden), um an einer Konferenz teilzunehmen.  <br/> |
|**MsDiagHeader** <br/> |varchar(max)  <br/> |Zusätzliche Fehlerinformationen.  <br/> |
   

