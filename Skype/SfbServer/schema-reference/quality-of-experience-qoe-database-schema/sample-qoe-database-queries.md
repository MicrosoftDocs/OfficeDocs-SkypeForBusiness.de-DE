---
title: Beispiele für QoE-Datenbankabfragen
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 04e6bdd3-bbd1-47ca-8114-94a3db6beeeb
description: In diesem Abschnitt sind Beispielabfragen für die QoE-Datenbank (Quality of Experience) enthalten.
ms.openlocfilehash: efc26064e52464ffc2e92e24d5af8dd848368b56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834365"
---
# <a name="sample-qoe-database-queries"></a>Beispiele für QoE-Datenbankabfragen
 
In diesem Abschnitt sind Beispielabfragen für die QoE-Datenbank (Quality of Experience) enthalten. 
  
Mithilfe des folgenden Beispiels können Sie die Jitterwerte und die Werte für den durchschnittlichen Paketverlust für alle Audiostreams abrufen.
  
```SQL
select avg(cast(JitterInterArrival as bigint)) as JitterAvg, avg(PacketLossRate) as PacketLossRateAvg from AudioStream
```

Mithilfe des folgenden Beispiels können Sie die Gesamtanzahl der Konferenzen ermitteln, die die Meeting-Konsole verwenden.
  
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

Mithilfe des folgenden Beispiels können Sie ConversationalMOS, SendingMOS und ListeningMOS pro Aufnahmegerät abrufen.
  
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
