---
title: 'Lync Server 2013: Beispiele für QoE-Datenbankabfragen'
TOCTitle: Beispiele für QoE-Datenbankabfragen
ms:assetid: 04e6bdd3-bbd1-47ca-8114-94a3db6beeeb
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398100(v=OCS.15)
ms:contentKeyID: 49293036
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Beispiele für QoE-Datenbankabfragen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-17_

Dieser Abschnitt enthält Beispielabfragen für die QoE-Datenbank (Quality of Experience) enthalten.

Mithilfe des folgenden Beispiels können Sie die Jitterwerte und die Werte für den durchschnittlichen Paketverlust für alle Audiostreams abrufen.

    select avg(cast(JitterInterArrival as bigint)) as JitterAvg, avg(PacketLossRate) as PacketLossRateAvg from AudioStream

Mithilfe des folgenden Beispiels können Sie die Gesamtzahl der Konferenzen ermitteln, die die Besprechungskonsole verwenden.

    select avg(ConversationalMOS)
    from SessionView s
    inner join MediaLineView m
    on s.ConferenceDateTime = m.ConferenceDateTime
       and s.SessionSeq = m.SessionSeq
       and m.MediaLineLabel = 0 -- audio media line
       and s.CallerUserAgentType = 4 -- Lync
       and s.CalleeUserAgentType = 4 -- Lync

Mithilfe des folgenden Beispiels können Sie ConversationalMOS, SendingMOS und ListeningMOS pro Aufnahmegerät abrufen.

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

