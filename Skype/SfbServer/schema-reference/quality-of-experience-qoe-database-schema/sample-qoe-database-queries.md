---
title: Beispiele für QoE-Datenbankabfragen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 04e6bdd3-bbd1-47ca-8114-94a3db6beeeb
description: Dieser Abschnitt enthält Beispielabfragen für die QoE-Datenbank (Quality of Experience).
ms.openlocfilehash: 099e0ed179ab22e3610aaf8b00d3745a315bb734
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888654"
---
# <a name="sample-qoe-database-queries"></a><span data-ttu-id="a494d-103">Beispiele für QoE-Datenbankabfragen</span><span class="sxs-lookup"><span data-stu-id="a494d-103">Sample QoE database queries</span></span>
 
<span data-ttu-id="a494d-104">Dieser Abschnitt enthält Beispielabfragen für die QoE-Datenbank (Quality of Experience).</span><span class="sxs-lookup"><span data-stu-id="a494d-104">This section contains sample queries for the Quality of Experience (QoE) database.</span></span> 
  
<span data-ttu-id="a494d-105">Verwenden Sie das folgende Beispiel, um den Durchschnitt der Jitter-und Paketverluste für alle Audiostreams zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a494d-105">Use the following example to get the jitter and packet loss average for all audio streams.</span></span>
  
```SQL
select avg(cast(JitterInterArrival as bigint)) as JitterAvg, avg(PacketLossRate) as PacketLossRateAvg from AudioStream
```

<span data-ttu-id="a494d-106">Verwenden Sie das folgende Beispiel, um die Gesamtzahl der Konferenzen zu finden, die die Besprechungskonsole verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="a494d-106">Use the following example to find the total numbers of conferences that used Meeting Console.</span></span>
  
```SQL
select avg(ConversationalMOS)
from SessionView s
inner join MediaLineView m
on s.ConferenceDateTime = m.ConferenceDateTime
   and s.SessionSeq = m.SessionSeq
   and m.MediaLineLabel = 0 -- audio media line
   and s.CallerUserAgentType = 4 -- Lync
   and s.CalleeUserAgentType = 4 -- Lync
```

<span data-ttu-id="a494d-107">Verwenden Sie das folgende Beispiel, um ConversstionalMOS, SendingMOS und ListendingMOS pro Aufnahmegerät abzurufen.</span><span class="sxs-lookup"><span data-stu-id="a494d-107">Use the following example to get ConversstionalMOS, SendingMOS and ListendingMOS per capture device.</span></span>
  
```SQL
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
