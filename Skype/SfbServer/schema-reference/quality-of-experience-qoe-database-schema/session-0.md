---
title: Sitzungsansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
description: Die Sitzungsansicht speichert Informationen zu Sitzungen mit Datensätzen in der Datenbank. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: cd304123022e0d4d921ecb1cd2599c636aaa9013
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805903"
---
# <a name="session-view"></a>Sitzungsansicht
 
Die Sitzungsansicht speichert Informationen zu Sitzungen mit Datensätzen in der Datenbank. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |In der medialinie-Tabelle referenziert.  <br/> |
|ConferenceURI  <br/> |nvarchar (450)  <br/> |Konferenz-URI, wenn es sich um eine Konferenz handelt, oder wenn es sich um eine Peer-to-Peer-Sitzung handelt.  <br/> |
|Korrelation  <br/> |varchar (max)  <br/> |Korrelations-ID der Sitzung.  <br/> |
|DialogCategory  <br/> |bit  <br/> |Dialog Feld Kategorie; 0 ist Skype for Business Server to Mediation Server Leg; 1 ist Vermittlungs Server für das PSTN-Gateway-Bein.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Gibt an, ob der Anruf umgangen wurde.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |Dieses Feld, falls vorhanden, gibt an, warum ein Anruf nicht umgangen wurde, auch wenn die Bypass-IDs übereinstimmten. Für Skype for Business Server wird nur ein Wert definiert:  <br/> 0x0001-unbekannte Bypass-ID für den standardmäßigen Netzwerkadapter  <br/> |
|StartTime  <br/> |datetime  <br/> |Startzeit des Anrufs.  <br/> |
|EndTime  <br/> |datetime  <br/> |Endzeit des Anrufs.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |FQDN des anrufenden Pools.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |FQDN des aufgerufenen Pools.  <br/> |
|CallerPAI  <br/> |nvarchar (450)  <br/> |Identitäts-URI des Anrufers p-Assert  <br/> |
|CalleePAI  <br/> |nvarchar (450)  <br/> |P-Assert-Identitäts-URI des aufgerufenen.  <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Der Endpunktname des Anrufers.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Der Endpunktname des Anrufers.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Benutzer-Agent-Zeichenfolge des Anrufers.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Der Typ des Benutzer-Agents des Anrufers. Weitere Informationen finden Sie in der [userAgent-Tabelle](useragent.md) . <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |Kategorie des Benutzer-Agents des Anrufers. Weitere Informationen finden Sie in der [UserAgentDef-Tabelle (QoE)](useragentdef-qoe.md) . <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Benutzer-Agent-Zeichenfolge des Benutzers.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Der Typ des Benutzer-Agents für den aufgerufenen. Weitere Informationen finden Sie in der [userAgent-Tabelle](useragent.md) . <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |Benutzer-Agent-Kategorie für den aufgerufenen. Weitere Informationen finden Sie in der [UserAgentDef-Tabelle (QoE)](useragentdef-qoe.md) . <br/> |
|CallerURI  <br/> |nvarchar (450)  <br/> |URI des Anrufers.  <br/> |
|CalleeURI  <br/> |nvarchar (450)  <br/> |URI des aufgerufenen.  <br/> |
|CallPrioirty  <br/> |int  <br/> |Die Priorität des Anrufs.  <br/> |
   

