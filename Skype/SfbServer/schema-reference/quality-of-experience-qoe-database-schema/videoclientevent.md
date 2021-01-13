---
title: Tabelle "VideoClientEvent"
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
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Jeder Datensatz enthält Clientereignis für einen Endpunkt in einem Videoanruf. In der Regel verfügt ein Anruf über zwei Datensätze, einen für den Anrufer und einen für den Anrufer.
ms.openlocfilehash: bb4a9feca562bed7bdb0080e7f9181003952f5d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821395"
---
# <a name="videoclientevent-table"></a>Tabelle "VideoClientEvent"
 
Jeder Datensatz enthält Clientereignis für einen Endpunkt in einem Videoanruf. In der Regel verfügt ein Anruf über zwei Datensätze, einen für den Anrufer und einen für den Anrufer.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |Datum/Uhrzeit  <br/> |Primary  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0: Daten des Ankrufers  <br/> 1: Daten des Anrufers  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |Prozentsatz der Sitzung, in der das Ereignis "LowBandwidth" für den Zustand "Schlecht" ausgelöst wurde. Die verfügbare Bandbreite reicht nicht aus, um eine akzeptable Spracherfahrung zu ermöglichen.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |Prozentsatz der Sitzung, in der das "ReceiveSendQuality"-Ereignis für den Zustand "Schlecht" ausgelöst wurde.  <br/> Die Netzwerkqualität im Hinblick auf Jitter oder Paketverlust ist stark und wirkt sich auf die Qualität der empfangenen Audiodaten aus.  <br/> |
   

