---
title: ProgressReport-Ansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: In der ProgressReport-Ansicht werden Informationen zu abgeschlossenen Sitzungen gespeichert. Fortschrittsberichte werden nur für Anrufe und Sitzungen geschrieben, die von lync Server 2013 für diagnostische Zwecke nützlich sein können. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: c07b9db8ebd9f898ab9d8feb5b07c4723209522c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814983"
---
# <a name="progressreport-view"></a>ProgressReport-Ansicht
 
In der ProgressReport-Ansicht werden Informationen zu abgeschlossenen Sitzungen gespeichert. Fortschrittsberichte werden nur für Anrufe und Sitzungen geschrieben, die von lync Server 2013 für diagnostische Zwecke nützlich sein können. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
  
> [!NOTE]
> Die Felder "Fehler", "ErrorReportSeq" und "ProgressReportSeq" beziehen sich nicht unbedingt auf Fehler, sondern auf Nachrichten, die den Status von anrufen oder Nachrichten angeben. 
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**Fehlerzeit** <br/> |datetime  <br/> |Zeitpunkt des Fehlers. Wird in Verbindung mit ErrorReportSeq verwendet, um einen Fehler eindeutig zu identifizieren.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Die ID-Nummer, um den Fehler zu identifizieren. Wird in Verbindung mit Fehlerzeit verwendet, um einen Fehler eindeutig zu identifizieren.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |ID zum Identifizieren des Statusberichts Wird verwendet, um Fortschrittsberichte desselben Fehlerberichts zu unterscheiden.  <br/> |
|**MsDiagId** <br/> |int  <br/> |Diagnose-ID für den Fehlerbericht.  <br/> |
|**Quelle** <br/> |nvarchar(256)  <br/> |Name des Servers, der den Fehler verursacht hat (wenn der Bericht von einer Serverkomponente gesendet wurde).  <br/> |
|**Anwendung** <br/> |nvarchar(256)  <br/> |Der Name der Anwendung, die den Fehler verursacht hat (wenn der Bericht von einer Serverkomponente gesendet wurde).  <br/> |
|**Telemetrie** <br/> |uniqueidentifier  <br/> |Eindeutiger Bezeichner, in dem die Verknüpfungszeit Informationen für die verschiedenen an einer Konferenz beteiligten Komponenten korreliert werden.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> |Zeit (in Millisekunden), die für eine bestimmte Komponente erforderlich ist, um an einer Konferenz teilzunehmen.  <br/> |
|**MsDiagHeader** <br/> |varchar (max)  <br/> |Weitere Fehlerinformationen.  <br/> |
   

