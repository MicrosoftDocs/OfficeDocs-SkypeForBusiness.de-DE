---
title: Sitzungsansicht
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
ms.assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
description: In der Sitzungsansicht werden Informationen über die Sitzungen gespeichert, die über einen Datensatz in der Datenbank verfügen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 34619c1555fac5935563dd72895f52d045c388ae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802695"
---
# <a name="session-view"></a>Sitzungsansicht
 
In der Sitzungsansicht werden Informationen über die Sitzungen gespeichert, die über einen Datensatz in der Datenbank verfügen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |Datum/Uhrzeit  <br/> |Verweis von der MediaLine-Tabelle.  <br/> |
|ConferenceURI  <br/> |nvarchar(450)  <br/> |Konferenz-URI bei einer Konferenz, DialogID bei einer Peer-zu-Peer-Sitzung.  <br/> |
|Correlation  <br/> |varchar(max)  <br/> |Korrelations-ID der Sitzung.  <br/> |
|DialogCategory  <br/> |bit  <br/> |Dialogkategorie; 0 ist die Skype for Business Server-zu-Vermittlungsserver-Leg; 1 ist die Vermittlungsserver-zu-PSTN-Gateway-Leg.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Gibt an, ob der Anruf umgangen wurde.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |Dieses Feld gibt an, warum ein Anruf nicht umgangen wurde, selbst wenn die Umgehungs-IDs übereinstimmen. Für Skype for Business Server ist nur ein Wert definiert:  <br/> 0x0001 – Unbekannte Umgehungs-ID für Standardnetzwerkadapter  <br/> |
|StartTime  <br/> |Datum/Uhrzeit  <br/> |Die Startzeit des Anrufs.  <br/> |
|EndTime  <br/> |Datum/Uhrzeit  <br/> |Die Endzeit des Anrufs.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |FQDN des Anruferpools.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |FQDN des Angerufenen-Pools.  <br/> |
|CallerPAI  <br/> |nvarchar(450)  <br/> |Der P-Asserted Identity-URI des Anrufers.  <br/> |
|CalleePAI  <br/> |nvarchar(450)  <br/> |Der p-asserted identity-URI des Ankrufers.  <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Name des Endpunkts des Anrufers.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Name des Endpunkts des Anrufers.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Benutzer-Agent-Zeichenfolge des Anrufers.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Typ des Benutzer-Agents des Anrufers. Weitere Informationen finden [Sie in der Tabelle "UserAgent".](useragent.md) <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |Kategorie des Benutzeragenten des Anrufers. Weitere Informationen [finden Sie in der Tabelle "UserAgentDef" (QoE).](useragentdef-qoe.md) <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Benutzer-Agent-Zeichenfolge des Ankrufers.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Benutzeragenttyp des Angerufenen. Weitere Informationen finden [Sie in der Tabelle "UserAgent".](useragent.md) <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |Benutzeragentkategorie des Angerufenen. Weitere Informationen [finden Sie in der Tabelle "UserAgentDef" (QoE).](useragentdef-qoe.md) <br/> |
|CallerURI  <br/> |nvarchar(450)  <br/> |URI des Anrufers.  <br/> |
|CalleeURI  <br/> |nvarchar(450)  <br/> |URI des Ankrufers.  <br/> |
|CallPrioirty  <br/> |int  <br/> |Priorität des Anrufs.  <br/> |
   

