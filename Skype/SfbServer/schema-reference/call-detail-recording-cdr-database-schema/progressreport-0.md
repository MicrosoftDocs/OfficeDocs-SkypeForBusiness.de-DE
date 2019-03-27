---
title: ProgressReport-Ansicht
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: ProgressReport-Ansicht speichert Informationen zu beendeten konferenzsitzungen. Fortschrittsberichte geschrieben werden nur für anrufen und Sitzungen, die Lync Server 2013 bestimmt um zu Diagnosezwecken hilfreich sein können. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 5f7cbba2580b83a65dbce00588f3c567317f4df4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891117"
---
# <a name="progressreport-view"></a>ProgressReport-Ansicht
 
ProgressReport-Ansicht speichert Informationen zu beendeten konferenzsitzungen. Fortschrittsberichte geschrieben werden nur für anrufen und Sitzungen, die Lync Server 2013 bestimmt um zu Diagnosezwecken hilfreich sein können. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
> [!NOTE]
> Die Felder ErrorTime, ErrorReportSeq und ProgressReportSeq verweisen nicht notwendigerweise auf Fehler, sondern auf Nachrichten, die den Status von Anrufen oder Nachrichten angeben. 
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**"ErrorTime"** <br/> |datetime  <br/> |Zeitpunkt der Fehler aufgetreten ist. In Verbindung mit "errorreportseq" verwendet, um einen Fehler eindeutig zu identifizieren.  <br/> |
|**"Errorreportseq"** <br/> |int  <br/> |ID-Nummer zur Identifikation des Fehlers. In Verbindung mit ErrorTime verwendet, um einen Fehler eindeutig zu identifizieren.  <br/> |
|**"Progressreportseq" verweisen** <br/> |int  <br/> |Identifizieren Sie den Fortschrittsbericht-ID. Verwendet, um Fortschrittsberichte des gleichen Fehlerberichts zu unterscheiden.  <br/> |
|**MsDiagId** <br/> |int  <br/> |Diagnose-ID für den Fehlerbericht.  <br/> |
|**Quelle** <br/> |nvarchar(256)  <br/> |Name des Servers, der den Fehler ausgelöst hat (falls der Bericht von einer Serverkomponente gesendet wurde).  <br/> |
|**Anwendung** <br/> |nvarchar(256)  <br/> |Name der Anwendung, die den Fehler ausgelöst hat (falls der Bericht von einer Serverkomponente gesendet wurde).  <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |Eindeutige ID zum korelieren für die verschiedenen Komponenten in einer Konferenz Beteiligten.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> |Zeit (in Millisekunden) für eine bestimmte Komponente zu einer Konferenz erforderlich.  <br/> |
|**MsDiagHeader** <br/> |varchar(max)  <br/> |Zusätzliche Fehlerinformationen.  <br/> |
   

