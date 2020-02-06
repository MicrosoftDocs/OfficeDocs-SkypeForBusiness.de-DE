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
ms.openlocfilehash: 46286f23a2f687d8c7464c2e131e4cef943a57c2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41806203"
---
# <a name="sample-qoe-database-queries"></a><span data-ttu-id="de2eb-103">Beispiele für QoE-Datenbankabfragen</span><span class="sxs-lookup"><span data-stu-id="de2eb-103">Sample QoE database queries</span></span>
 
<span data-ttu-id="de2eb-104">Dieser Abschnitt enthält Beispielabfragen für die QoE-Datenbank (Quality of Experience).</span><span class="sxs-lookup"><span data-stu-id="de2eb-104">This section contains sample queries for the Quality of Experience (QoE) database.</span></span> 
  
<span data-ttu-id="de2eb-105">Verwenden Sie das folgende Beispiel, um den Durchschnitt der Jitter-und Paketverluste für alle Audiostreams zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="de2eb-105">Use the following example to get the jitter and packet loss average for all audio streams.</span></span>
  
```
select avg(cast(JitterInterArrival as bigint)) as JitterAvg, avg(PacketLossRate) as PacketLossRateAvg from AudioStream
```

<span data-ttu-id="de2eb-106">Verwenden Sie das folgende Beispiel, um die Gesamtzahl der Konferenzen zu finden, die die Besprechungskonsole verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="de2eb-106">Use the following example to find the total numbers of conferences that used Meeting Console.</span></span>
  
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

<span data-ttu-id="de2eb-107">Verwenden Sie das folgende Beispiel, um ConversstionalMOS, SendingMOS und ListendingMOS pro Aufnahmegerät abzurufen.</span><span class="sxs-lookup"><span data-stu-id="de2eb-107">Use the following example to get ConversstionalMOS, SendingMOS and ListendingMOS per capture device.</span></span>
  
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
