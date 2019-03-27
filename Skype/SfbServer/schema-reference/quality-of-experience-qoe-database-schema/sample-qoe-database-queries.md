---
title: Beispiele für QoE-Datenbankabfragen
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 04e6bdd3-bbd1-47ca-8114-94a3db6beeeb
description: Dieser Abschnitt enthält Beispielabfragen für die Quality of Experience (QoE)-Datenbank.
ms.openlocfilehash: b521986e4a7b91f211788922b55067622b48dac5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873808"
---
# <a name="sample-qoe-database-queries"></a><span data-ttu-id="67cc3-103">Beispiele für QoE-Datenbankabfragen</span><span class="sxs-lookup"><span data-stu-id="67cc3-103">Sample QoE database queries</span></span>
 
<span data-ttu-id="67cc3-104">Dieser Abschnitt enthält Beispielabfragen für die Quality of Experience (QoE)-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="67cc3-104">This section contains sample queries for the Quality of Experience (QoE) database.</span></span> 
  
<span data-ttu-id="67cc3-105">Mithilfe des folgenden Beispiels den Verlust Jitter und Paketverlust für alle Audiostreams durchschnittliche abgerufen.</span><span class="sxs-lookup"><span data-stu-id="67cc3-105">Use the following example to get the jitter and packet loss average for all audio streams.</span></span>
  
```
select avg(cast(JitterInterArrival as bigint)) as JitterAvg, avg(PacketLossRate) as PacketLossRateAvg from AudioStream
```

<span data-ttu-id="67cc3-106">Verwenden Sie das folgende Beispiel, um die Gesamtzahl der Konferenzen ermitteln, die die Meeting-Konsole.</span><span class="sxs-lookup"><span data-stu-id="67cc3-106">Use the following example to find the total numbers of conferences that used Meeting Console.</span></span>
  
```
select avg(ConversationalMOS)
from SessionView s
inner join MediaLineView m
on s.ConferenceDateTime = m.ConferenceDateTime
   and s.SessionSeq = m.SessionSeq
   and m.MediaLineLabel = 0 -- audio media line
   and s.CallerUserAgentType = 4 -- Lync
   and s.CalleeUserAgentType = 4 -- Lync
```

<span data-ttu-id="67cc3-107">Mithilfe des folgenden Beispiels können Sie Conversationalmos, SendingMOS und Listeningmos pro Aufnahmegerät abrufen.</span><span class="sxs-lookup"><span data-stu-id="67cc3-107">Use the following example to get ConversstionalMOS, SendingMOS and ListendingMOS per capture device.</span></span>
  
```
select t.DeviceName as Device, count(*) as SampleNum, avg(ConversationalMOS) as ConversationalMOS, avg(SendListenMOS) SendingMOS, avg(RecvListenMOS) as ListendingMOS
from
(
   select m.CallerCaptureDev as DeviceName, m.ConferenceDateTime, m.SessionSeq, a.StreamID, m.ConversationalMOS,a.SendListenMOS, a.RecvListenMOS
   from MediaLineView m
   inner join AudioStream a
   on m.ConferenceDateTime = a.ConferenceDateTime
      and m.SessionSeq = a.SessionSeq
      and m.MediaLineLabel = 0

   union

   select m.CalleeCaptureDev as DeviceName, m.ConferenceDateTime, m.SessionSeq, a.StreamID, m.ConversationalMOS,a.SendListenMOS, a.RecvListenMOS
   from MediaLineView m
   inner join AudioStream a
   on m.ConferenceDateTime = a.ConferenceDateTime
      and m.SessionSeq = a.SessionSeq
      and m.MediaLineLabel = 0

)as t
group by t.DeviceName
order by SampleNum desc
```
