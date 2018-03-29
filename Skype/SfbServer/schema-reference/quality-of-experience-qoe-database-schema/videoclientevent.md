---
title: VideoClientEvent-Tabelle
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
ms.openlocfilehash: b0c73cb3bc07a3e258f66555993698c21a978250
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
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
   

