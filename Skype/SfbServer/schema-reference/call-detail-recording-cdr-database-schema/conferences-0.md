---
title: Konferenz Ansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
description: In der Ansicht "Konferenzen" werden Informationen zu den Konferenzen gespeichert. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 2e49a60be1651c34fb874c62bbee8c993eb00983
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296462"
---
# <a name="conferences-view"></a>Konferenz Ansicht
 
In der Ansicht "Konferenzen" werden Informationen zu den Konferenzen gespeichert. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**SessionID** <br/> |datetime  <br/> |Uhrzeit der Sitzungsanforderung. Wird in Verbindung mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Die ID-Nummer, um die Sitzung zu identifizieren. Wird in Verbindung mit SessionID-Mal verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> |URI für die Konferenz.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Der Typ des Konferenz-URIs. Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |Wird für wiederkehrende Konferenzen verwendet. Jede Instanz einer Besprechungsserie hat dieselbe ConferenceUri, aber eine andere ConfInstance.  <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> |Startzeit für die Konferenz.  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> |Endzeit für die Konferenz.  <br/> |
|**OrganizerUri** <br/> |nvarchar (450)  <br/> |Der URI des Benutzers, der die Konferenz organisiert hat.  <br/> |
|**Organizer** <br/> |nvarchar(256)  <br/> |Der Typ des URIs des Benutzers, der die Konferenz organisiert hat. Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**OrganizerTenant** <br/> |nvarchar(256)  <br/> |Der Mandant des Benutzers, der die Konferenz organisiert hat. Weitere Informationen finden Sie in der [Tabelle Mandanten](tenants.md) . <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Vollständig qualifizierter Domänenname des Pools, in dem die Konferenz gehostet wurde.  <br/> |
|**Kennzeichnen** <br/> |smallint  <br/> |Bitmaske, die Konferenz Attribute enthält. Mögliche Werte:  <br/> 0X01-synthetische Transaktion  <br/> |
   

