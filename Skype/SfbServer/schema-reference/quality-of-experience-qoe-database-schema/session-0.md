---
title: Session-Ansicht
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
description: Session-Ansicht speichert Informationen über Sitzungen, die Datensätze in der Datenbank verfügen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: c72773b4ff87786ab5b4e73b67e89032dc393fa1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880221"
---
# <a name="session-view"></a>Session-Ansicht
 
Session-Ansicht speichert Informationen über Sitzungen, die Datensätze in der Datenbank verfügen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |Verwiesen von der MediaLine Table.  <br/> |
|ConferenceURI  <br/> |nvarchar(450)  <br/> |Konferenz-URI ist dies eine Konferenz ist, oder Dialogkennung, wenn dieser ist eine Peer-zu-Peer-Sitzung.  <br/> |
|Korrelation  <br/> |varchar(max)  <br/> |Korrelations-ID der Sitzung.  <br/> |
|DialogCategory  <br/> |bit  <br/> |Dialogfeld Kategorie. 0 ist Skype für Business Server Mediation Server Abschnitts. 1: Vermittlungsserver zum PSTN-Gateway-Abschnitt.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Gibt an, ob der Anruf umgangen wurde.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |Dieses Feld gibt, falls vorhanden, warum ein Anruf nicht umgangen wurde, auch wenn die Umgehung IDs übereinstimmen. Für Skype für Business Server wird nur ein Wert definiert:  <br/> 0 x 0001 – unbekannte umgehungs-ID für Standardnetzwerkadapter  <br/> |
|StartTime  <br/> |datetime  <br/> |Startzeit des Anrufs.  <br/> |
|EndTime  <br/> |datetime  <br/> |Die Endzeit des Anrufs.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |Anrufer-Pool FQDN.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |FQDN des angerufenenpools.  <br/> |
|CallerPAI  <br/> |nvarchar(450)  <br/> |Des Anrufers p-asserted-Identity-URI.  <br/> |
|CalleePAI  <br/> |nvarchar(450)  <br/> |Angerufenen p-asserted-Identity-URI.  <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Endpunktname des angerufenen.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Endpunktname des angerufenen.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Benutzeragentzeichenfolge des Anrufers.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Typ des Benutzer-Agent des Anrufers. [UserAgent-Tabelle](useragent.md) Details finden Sie. <br/> |
|CallerUserAgentCategory  <br/> |Nvarchar (64)  <br/> |Kategorie des Benutzer-Agent des Anrufers. [UserAgentDef-Tabelle (QoE)](useragentdef-qoe.md) ausführliche Informationen finden Sie. <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Benutzeragentzeichenfolge des angerufenen.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Typ des Benutzer-Agent für die des angerufenen. [UserAgent-Tabelle](useragent.md) Details finden Sie. <br/> |
|CalleeUserAgentCategory  <br/> |Nvarchar (64)  <br/> |Benutzer-Agent-Kategorie für des angerufenen. [UserAgentDef-Tabelle (QoE)](useragentdef-qoe.md) ausführliche Informationen finden Sie. <br/> |
|CallerURI  <br/> |nvarchar(450)  <br/> |URI des Anrufers.  <br/> |
|CalleeURI  <br/> |nvarchar(450)  <br/> |URI des angerufenen.  <br/> |
|CallPrioirty  <br/> |int  <br/> |Priorität des Anrufs.  <br/> |
   

