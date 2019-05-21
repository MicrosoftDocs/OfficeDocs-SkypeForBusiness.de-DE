---
title: AudioSignal-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
description: Jeder Datensatz stellt die Metriken des Audiosignals für einen Endpunkt dar. In der Regel hat jeder Anruf zwei Datensätze, einer für den Anrufer und einer für den aufgerufenen.
ms.openlocfilehash: f8d617e96fe3427493bcb9e4cc70008fedae72e7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295076"
---
# <a name="audiosignal-table"></a>AudioSignal-Tabelle
 
Jeder Datensatz stellt die Metriken des Audiosignals für einen Endpunkt dar. In der Regel hat jeder Anruf zwei Datensätze, einer für den Anrufer und einer für den aufgerufenen. 
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |In der medialinie- [Tabelle](medialine-0.md)referenziert.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |In der medialinie- [Tabelle](medialine-0.md)referenziert.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |In der medialinie- [Tabelle](medialine-0.md)referenziert.  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0: Daten des angerufenen  <br/> 1: Daten des Anrufers  <br/> |
|**SendSignalLevel** <br/> |int  <br/> | <br/> |Stellt den Pegel des Audiosignals nach analoger Gain-Steuerung dar. Die Einheit für diese Metrik lautet dBmo. Für akzeptable Qualität sollte es mindestens 30 dBmo. Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.  <br/> |
|**RecvSignalLevel** <br/> |int  <br/> | <br/> |Siehe SendSignalLevel.  <br/> |
|**SendNoiseLevel** <br/> |int  <br/> | <br/> |Stellt den Audio-Rauschpegel nach analoger Gain-Steuerung dar. Die Einheit für diese Metrik lautet dBmo. Für akzeptable Qualität sollte es weniger als 35 dBmo. Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.  <br/> |
|**RecvNoiseLevel** <br/> |int  <br/> | <br/> |Siehe SendNoiseLevel.  <br/> |
|**EchoReturn** <br/> |int  <br/> | <br/> |Verbesserungs Metrik für ECHO-Rückerstattungs Verluste. Die Einheit für diese Metrik ist DB. Niedrigere Werte stellen weniger Echo dar. Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.  <br/> |
|**AudioSpeakerGlitchRate** <br/> |int  <br/> | <br/> |Durchschnittliche Störimpulse pro fünf Minuten für die Lautsprecher-Wiedergabe. Für eine gute Qualität sollte dies weniger als eins pro fünf Minuten sein. Nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen gemeldet.  <br/> |
|**AudioMicGlitchRate** <br/> |int  <br/> | <br/> |Durchschnittliche Störimpulse pro fünf Minuten für die Aufnahme des Mikrofons. Für eine gute Qualität sollte dies weniger als eine pro fünf Minuten sein. Nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen gemeldet.  <br/> |
|**AudioTimestampDriftRateMic** <br/> |Dezimal (9; 2)  <br/> | <br/> |Clock-Drift Rate des Mikrofon Geräts relativ zur CPU-Uhr.  <br/> |
|**AudioTimestampDriftRateSpk** <br/> |Dezimal (9; 2)  <br/> | <br/> |Clock-Drift Rate des Lautsprecher Geräts relativ zur CPU-Uhr.  <br/> |
|**AudioTimestampErrorMicMs** <br/> |Dezimal (9; 2)  <br/> | <br/> |Clock-Drift Rate des Lautsprecher Geräts relativ zur CPU-Uhr.  <br/> Durchschnittlicher Zeitstempel des Mikrofon-Datenstroms in Millisekunden in den letzten 20 Sekunden des Anrufs.  <br/> |
|**AudioTimestampErrorSpkMs** <br/> |Dezimal (9; 2)  <br/> | <br/> |Durchschnittlicher Render-Datenstrom-Zeitstempel Fehler in Millisekunden in den letzten 20 Sekunden des Anrufs.  <br/> |
|**VsEntryCauses** <br/> |smallint  <br/> | <br/> |Voice-Switch ist ein Halbduplex-Modus mit verminderter Unterbrechungs Fähigkeit. Ursachen für den Sprachwechsel Eintrag:  <br/> ENTER_VS_BADTS 0x01  <br/> ENTER_VS_ECHO 0x02  <br/> ENTER_VS_FORCEORCONVERGENCE 0x04  <br/> ENTER_VS_DNLP 0x08  <br/> Die Ursache kann eine Kombination dieser einzelnen Ursachen sein. ENTER_VS_FORCEORCONVERGENCE kann nur von der Registrierungsschlüssel für Testzwecke aktiviert werden.  <br/> Der Datentyp für diese Spalte wurde in Microsoft lync Server 2013 geändert.  <br/> |
|**EchoEventCauses** <br/> |tinyint  <br/> | <br/> |Ursachen für ein Echo-Ereignis:  <br/> ECHO_EVENT_BAD_TIMESTAMP 0x01  <br/> ECHO_EVENT_POSTAEC_ECHO 0x02  <br/> ECHO_EVENT_ANLP 0x04  <br/> ECHO_EVENT_DNLP 0x08  <br/> ECHO_EVENT_MIC_CLIPPING 0x10  <br/> ECHO_EVENT_BAD_STATE 0x20  <br/> Die Ursache kann eine Kombination dieser einzelnen Ursachen sein.  <br/> |
|**EchoPercentMicIn** <br/> |Dezimal (5; 2)  <br/> | <br/> |Prozentsatz der Zeit, in der im Mikrofonaufnahme-Datenstrom Echo festgestellt wurde. In der Regel weisen Headsets oder Hörer niedrige Werte und Freisprechvorrichtungen oder eigenständige Lautsprecher höhere Werte auf. Bei Geräten, die eine integrierte akustische Echounterdrückung unterstützen, weisen hohe Werte auf eine Echoausbreitung hin. Für andere Geräte sollte diese Metrik nicht verwendet werden, um die Gerätequalität zu evaluieren.  <br/> |
|**EchoPercentSend** <br/> |Dezimal (5; 2)  <br/> ||Prozentsatz der Zeit, zu der Echo in gesendetem Datenstrom erkannt wird. Ein großer Prozentsatz des Echos in Send-Streams zeigt einen Hinweis auf Echo Verluste.  <br/> |
|**RxAGCSignalLevel** <br/> |int  <br/> | <br/> |Empfangene Signalstufe auf dem Vermittlungs Server vom Gateway; Dies gilt nur für den Vermittlungs Server. Die Einheit dieser Metrik ist dBoV. Für eine gute Qualität sollte der zulässige Bereich [-30 bis-18] dBoV sein.  <br/> |
|**RxAGCNoiseLevel** <br/> |int  <br/> | <br/> |Empfangene Signalstufe auf dem Vermittlungs Server vom Gateway. Dies gilt nur für den Vermittlungs Server. Die Einheit dieser Metrik ist dBoV. Für eine gute Qualität sollte der zulässige Bereich kleiner als-50 dBoV sein.  <br/> |
|**RxAvgAGCGain** <br/> |int  <br/> | <br/> |Automatische Gain-Steuerung (AGC) auf der Mediation Server-Seite.  <br/> |
|**InitialSignalLevelRMS** <br/> |float  <br/> | <br/> |Das Stamm mittelquadrat (RMS) des eingehenden Signals von bis zu den ersten 30 Sekunden des Anrufs.  <br/> |
|**RecvSignalLevelCh1** <br/> |int  <br/> ||Signal Pegel, wie er auf Kanal 1 empfangen wurde.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RecvSignalLevelCh2** <br/> |int  <br/> ||Signal Pegel, wie er auf Kanal 2 empfangen wurde.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RecvNoiseLevelCh1** <br/> |int  <br/> ||Geräuschpegel, wie er auf Kanal 1 empfangen wurde.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RecvNoiseLevelCh2** <br/> |int  <br/> ||Rauschpegel, wie er auf Kanal 2 empfangen wurde.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**SendSignalLevelCh1** <br/> |int  <br/> ||Signal Pegel, wie er auf Kanal 1 gesendet wurde.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**SendSignalLevelCh2** <br/> |int  <br/> ||Signal Pegel, wie er auf Kanal 2 gesendet wurde.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**SendNoiseLevelCh1** <br/> |int  <br/> ||Rauschpegel, wie er auf Kanal 1 gesendet wurde.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**SendNoiseLevelCh2** <br/> |int  <br/> ||Rauschpegel, wie er auf Kanal 2 gesendet wurde.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RenderLoopbackSignalLevel** <br/> |int  <br/> ||Pegel in dBFS des Signals, das an den Lautsprecher zur Wiedergabe gesendet wird. Berücksichtigt alle Gain-Anpassungen, die am empfangenen Signal vorgenommen wurden. <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |   
|**RenderNoiseLevel** <br/> |int  <br/> ||Pegel in dBFS des Rausch Inhalts des Signals, das an den Lautsprecher zur Wiedergabe gesendet wird <br/> |

