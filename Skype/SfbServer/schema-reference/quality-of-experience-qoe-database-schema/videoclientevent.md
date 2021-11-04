---
title: VideoClientEvent-Tabelle
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Jeder Datensatz enthält ein Clientereignis für einen Endpunkt in einem Videoanruf. In der Regel hat ein Anruf zwei Datensätze, einen für den Anrufer und einen für den Angerufenen.
ms.openlocfilehash: a5bfbd33a5416cf68e7df45caf389133eb517e20
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767273"
---
# <a name="videoclientevent-table"></a>VideoClientEvent-Tabelle
 
Jeder Datensatz enthält ein Clientereignis für einen Endpunkt in einem Videoanruf. In der Regel hat ein Anruf zwei Datensätze, einen für den Anrufer und einen für den Angerufenen.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |Datum/Uhrzeit  <br/> |Primary  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|**MediaLineLabel** <br/> |Tinyint  <br/> |Primary  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|**FromCaller** <br/> |Bit  <br/> |Primary  <br/> |0: Daten des Angerufenen  <br/> 1: Anruferdaten  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |Prozentsatz der Sitzung, in der das LowBandwidth-Ereignis für den Status "Ungültig" ausgelöst wurde. Die verfügbare Bandbreite reicht für eine akzeptable Spracherfahrung nicht aus.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |Prozentsatz der Sitzung, für die das ReceiveSendQuality-Ereignis für den Status "Ungültig" ausgelöst wurde.  <br/> Die Netzwerkqualität im Hinblick auf Jitter oder Paketverlust ist schwerwiegend und wirkt sich auf die Qualität der empfangenen Audiodaten aus.  <br/> |
   

