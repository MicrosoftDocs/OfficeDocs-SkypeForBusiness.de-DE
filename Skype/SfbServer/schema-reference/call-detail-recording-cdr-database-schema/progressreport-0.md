---
title: ProgressReport-Ansicht
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 8e21b83b1ca6c4856ba31a579e4a7999ba8b31a6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623537"
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
|**Anwendung** <br/> |nvarchar(256)  <br/> |Name der Anwendung, von der der Fehler stammt (wenn der Bericht von einer Serverkomponente gesendet wurde).  <br/> |
|**Telemetrie-ID** <br/> |Uniqueidentifier  <br/> |Eindeutiger Bezeichner, der die Informationen über den Zeitpunkt des Beitritts für verschiedene in einer Konferenz beteiligten Komponenten korreliert.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> |Für eine bestimmte Komponente erforderliche Zeit (in Millisekunden), um an einer Konferenz teilzunehmen.  <br/> |
|**MsDiagHeader** <br/> |varchar(max)  <br/> |Zusätzliche Fehlerinformationen.  <br/> |
   

