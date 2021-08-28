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
ms.localizationpriority: medium
ms.assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
description: In der Sitzungsansicht werden Informationen über die Sitzungen gespeichert, die über einen Datensatz in der Datenbank verfügen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: e39f6c744280e96a6f0fd33c28125196f90ed7cc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58593349"
---
# <a name="session-view"></a>Sitzungsansicht
 
In der Sitzungsansicht werden Informationen über die Sitzungen gespeichert, die über einen Datensatz in der Datenbank verfügen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |Datum/Uhrzeit  <br/> |Verweis von der MediaLine-Tabelle.  <br/> |
|ConferenceURI  <br/> |nvarchar(450)  <br/> |Konferenz-URI bei einer Konferenz, DialogID bei einer Peer-zu-Peer-Sitzung.  <br/> |
|Correlation  <br/> |varchar(max)  <br/> |Korrelations-ID der Sitzung.  <br/> |
|DialogCategory  <br/> |Bit  <br/> |Dialogkategorie; 0 ist Skype for Business Server vermittlungsserver leg; 1 ist Vermittlungsserver zu PSTN-Gateway.  <br/> |
|MediationServerBypassFlag  <br/> |Bit  <br/> |Gibt an, ob der Anruf umgangen wurde.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |Dieses Feld gibt gegebenenfalls an, warum ein Anruf nicht umgangen wurde, auch wenn die Umgehungs-IDs übereinstimmen. Für Skype for Business Server wird nur ein Wert definiert:  <br/> 0x0001 – Unbekannte Umgehungs-ID für Standardnetzwerkadapter  <br/> |
|StartTime  <br/> |Datum/Uhrzeit  <br/> |Die Startzeit des Anrufs.  <br/> |
|EndTime  <br/> |Datum/Uhrzeit  <br/> |Die Endzeit des Anrufs.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |FQDN des Anruferpools.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |FQDN des Angerufenen-Pools.  <br/> |
|CallerPAI  <br/> |nvarchar(450)  <br/> |Der p-asserted Identity URI des Aufrufers.  <br/> |
|CalleePAI  <br/> |nvarchar(450)  <br/> |Der p-asserted Identity URI des Angerufenen.  <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Endpunktname des Anrufers.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Endpunktname des Anrufers.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Benutzer-Agent-Zeichenfolge des Aufrufers.  <br/> |
|CallerUserAgentType  <br/> |Smallint  <br/> |Typ des Benutzer-Agenten des Anrufers. Weitere Informationen finden Sie in der [UserAgent-Tabelle.](useragent.md) <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |Kategorie des Benutzer-Agenten des Anrufers. Weitere Informationen finden Sie in der [UserAgentDef-Tabelle (QoE).](useragentdef-qoe.md) <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Benutzer-Agent-Zeichenfolge des Angerufenen.  <br/> |
|CalleeUserAgentType  <br/> |Smallint  <br/> |Benutzeragenttyp des Angerufenen. Weitere Informationen finden Sie in der [UserAgent-Tabelle.](useragent.md) <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |Benutzeragentkategorie des Angerufenen. Weitere Informationen finden Sie in der [UserAgentDef-Tabelle (QoE).](useragentdef-qoe.md) <br/> |
|CallerURI  <br/> |nvarchar(450)  <br/> |Der URI des Aufrufers.  <br/> |
|CalleeURI  <br/> |nvarchar(450)  <br/> |Der URI des Angerufenen.  <br/> |
|CallPrioirty  <br/> |int  <br/> |Priorität des Anrufs.  <br/> |
   

