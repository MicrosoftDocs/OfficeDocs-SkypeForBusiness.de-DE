---
title: VideoClientEvent-Tabelle
ms.reviewer: ''
ms.author: v-cichur
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
ms.openlocfilehash: de088fb6f4bb5cd41c4f4be69fba2445c61c3e96
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595255"
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
   

