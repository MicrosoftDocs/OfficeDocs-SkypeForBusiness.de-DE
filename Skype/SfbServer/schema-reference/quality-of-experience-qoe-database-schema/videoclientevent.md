---
title: VideoClientEvent-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Jeder Datensatz enthält ein Clientereignis für einen Endpunkt in einem Videoanruf. In der Regel verfügt ein Anruf über zwei Datensätze, einen für den Anrufer und einen für den aufgerufenen.
ms.openlocfilehash: b8e93206ea30622baa82adcec5ee9a80235521c5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294552"
---
# <a name="videoclientevent-table"></a>VideoClientEvent-Tabelle
 
Jeder Datensatz enthält ein Clientereignis für einen Endpunkt in einem Videoanruf. In der Regel verfügt ein Anruf über zwei Datensätze, einen für den Anrufer und einen für den aufgerufenen.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |In der medialinie- [Tabelle](medialine-0.md)referenziert.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |In der medialinie- [Tabelle](medialine-0.md)referenziert.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |In der medialinie- [Tabelle](medialine-0.md)referenziert.  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0: Daten des angerufenen  <br/> 1: Daten des Anrufers  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |Prozentsatz der Sitzung, für die das LowBandwidth-Ereignis für den Zustand "falsch" ausgelöst wurde. Die verfügbare Bandbreite reicht für ein akzeptables Spracherlebnis nicht aus.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |Prozentsatz der Sitzung, für die das ReceiveSendQuality-Ereignis für den Zustand "falsch" ausgelöst wurde.  <br/> Die Netzwerkqualität in Bezug auf Jitter oder Paketverlust ist schwerwiegend und beeinträchtigt die Qualität des empfangenen Audiosignals.  <br/> |
   

