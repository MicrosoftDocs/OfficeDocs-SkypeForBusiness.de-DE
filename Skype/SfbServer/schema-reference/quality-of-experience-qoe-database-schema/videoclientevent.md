---
title: VideoClientEvent-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Jeder Datensatz enthält Clientereignis für einen Endpunkt in einen Videoanruf. In der Regel muss ein Anruf zwei Datensätze, einen für Anrufer und einen für des angerufenen.
ms.openlocfilehash: 314e4df9313a3d111d71b6eaa06565edcbb765d1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891238"
---
# <a name="videoclientevent-table"></a>VideoClientEvent-Tabelle
 
Jeder Datensatz enthält Clientereignis für einen Endpunkt in einen Videoanruf. In der Regel muss ein Anruf zwei Datensätze, einen für Anrufer und einen für des angerufenen.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Verweis von der [MediaLine-Tabelle](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Verweis von der [MediaLine-Tabelle](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |Verweis von der [MediaLine-Tabelle](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0: Daten des angerufenen  <br/> 1: Daten des Anrufers  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |Prozentsatz von Sitzungen, in denen das LowBandwidth-Ereignis ausgelöst wurde 'Beschädigten' Zustand. Die verfügbare Bandbreite ist für eine akzeptable VoIP wünschen unzureichend.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |Prozentsatz von Sitzungen, in denen das ReceiveSendQuality-Ereignis ausgelöst wurde 'Beschädigten' Zustand.  <br/> Netzwerkqualität in Bezug auf Jitter oder Paketverlusten ist erheblich und wirkt sich auf die Qualität der empfangenen Audiodaten.  <br/> |
   

