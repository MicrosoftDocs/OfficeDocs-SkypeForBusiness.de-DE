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
localization_priority: Normal
ms.assetid: 04e6bdd3-bbd1-47ca-8114-94a3db6beeeb
description: Dieser Abschnitt enthält Beispielabfragen für die QoE-Datenbank (Quality of Experience).
ms.openlocfilehash: 42000bfe28acde629165009bbb7b6c33d15f8cdb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294705"
---
# <a name="sample-qoe-database-queries"></a><span data-ttu-id="2d060-103">Beispiele für QoE-Datenbankabfragen</span><span class="sxs-lookup"><span data-stu-id="2d060-103">Sample QoE database queries</span></span>
 
<span data-ttu-id="2d060-104">Dieser Abschnitt enthält Beispielabfragen für die QoE-Datenbank (Quality of Experience).</span><span class="sxs-lookup"><span data-stu-id="2d060-104">This section contains sample queries for the Quality of Experience (QoE) database.</span></span> 
  
<span data-ttu-id="2d060-105">Verwenden Sie das folgende Beispiel, um den Durchschnitt der Jitter-und Paketverluste für alle Audiostreams zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2d060-105">Use the following example to get the jitter and packet loss average for all audio streams.</span></span>
  
```
select avg(cast(JitterInterArrival as bigint)) as JitterAvg, avg(PacketLossRate) as PacketLossRateAvg from AudioStream
```

<span data-ttu-id="2d060-106">Verwenden Sie das folgende Beispiel, um die Gesamtzahl der Konferenzen zu finden, die die Besprechungskonsole verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="2d060-106">Use the following example to find the total numbers of conferences that used Meeting Console.</span></span>
  
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

<span data-ttu-id="2d060-107">Verwenden Sie das folgende Beispiel, um ConversstionalMOS, SendingMOS und ListendingMOS pro Aufnahmegerät abzurufen.</span><span class="sxs-lookup"><span data-stu-id="2d060-107">Use the following example to get ConversstionalMOS, SendingMOS and ListendingMOS per capture device.</span></span>
  
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
