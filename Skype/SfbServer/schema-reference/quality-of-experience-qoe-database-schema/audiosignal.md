---
title: AudioSignal-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
description: Jeder Datensatz steht Audiosignal Metriken für einen Endpunkt. In der Regel jeden Anruf hat zwei Datensätze, einer für Anrufer ist und eine für angerufenen ist.
ms.openlocfilehash: 7a064f13b6f34f61dcfb72169a4b1620cd81b01f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212313"
---
# <a name="audiosignal-table"></a>AudioSignal-Tabelle
 
Jeder Datensatz steht Audiosignal Metriken für einen Endpunkt. In der Regel jeden Anruf hat zwei Datensätze, einer für Anrufer ist und eine für angerufenen ist. 
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Verweis von der [MediaLine-Tabelle](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Verweis von der [MediaLine-Tabelle](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |Verweis von der [MediaLine-Tabelle](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0: Daten des angerufenen  <br/> 1: Daten des Anrufers  <br/> |
|**"Sendsignallevel"** <br/> |int  <br/> | <br/> |Stellt die nach der analoge Geräte erhalten Sie die Kontrolle Audiosignal-Ebene dar. Die Einheit dieser Metrik ist dBmo. Für eine akzeptable Qualität sollte mindestens 30 dBmo sein. Diese Metrik wird nicht gemeldet, vom A / V-Konferenzserver oder IP-Telefone.  <br/> |
|**RecvSignalLevel** <br/> |int  <br/> | <br/> |Siehe "sendsignallevel".  <br/> |
|**"Sendnoiselevel"** <br/> |int  <br/> | <br/> |Stellt die nach der analoge Geräte erhalten Sie die Kontrolle audio Rauschen. Die Einheit dieser Metrik ist dBmo. Akzeptable Qualität sollten sie weniger als 35 dBmo sein. Diese Metrik wird nicht gemeldet, vom A / V-Konferenzserver oder IP-Telefone.  <br/> |
|**RecvNoiseLevel** <br/> |int  <br/> | <br/> |Siehe "sendnoiselevel".  <br/> |
|**EchoReturn** <br/> |int  <br/> | <br/> |Echo zurückgeben Verlust Erweiterung Metrik. Die Einheit dieser Metrik ist dB. Niedrigere Werte darstellen weniger Echo. Diese Metrik wird nicht gemeldet, vom A / V-Konferenzserver oder IP-Telefone.  <br/> |
|**AudioSpeakerGlitchRate** <br/> |int  <br/> | <br/> |Durchschnittliche Probleme pro fünf Minuten für das Rendering von Audiosignalen aufgeführt. Für die Qualität sollte dies weniger als eine pro fünf Minuten lang sein. Nicht berichtet von A / V-Konferenzserver, Vermittlungsserver oder IP-Telefone.  <br/> |
|**AudioMicGlitchRate** <br/> |int  <br/> | <br/> |Durchschnittliche Probleme pro fünf Minuten für die Aufnahme Mikrofon. Für guter Qualität sollte dies weniger als einer pro fünf Minuten lang sein. Nicht berichtet von A / V-Konferenzserver, Vermittlungsserver oder IP-Telefone.  <br/> |
|**AudioTimestampDriftRateMic** <br/> |decimal(9,2)  <br/> | <br/> |Uhr driftrate Mikrofons, relativ zum CPU-Takt.  <br/> |
|**AudioTimestampDriftRateSpk** <br/> |decimal(9,2)  <br/> | <br/> |Uhr driftrate Lautsprechers, relativ zum CPU-Takt.  <br/> |
|**AudioTimestampErrorMicMs** <br/> |decimal(9,2)  <br/> | <br/> |Uhr driftrate Lautsprechers, relativ zum CPU-Takt.  <br/> Durchschnittliche Mikrofon Capture Stream Zeitstempel Fehler in Millisekunden, in den letzten 20 Sekunden des Anrufs.  <br/> |
|**AudioTimestampErrorSpkMs** <br/> |decimal(9,2)  <br/> | <br/> |Durchschnittliche Lautsprecher Rendern Stream Zeitstempel Fehler in Millisekunden, in den letzten 20 Sekunden des Anrufs.  <br/> |
|**VsEntryCauses** <br/> |smallint  <br/> | <br/> |VoIP-Switch ist eine Halbduplexmodus reduzierte Unterbrechung Möglichkeit. Ursachen für VoIP-Switch-Eintrag:  <br/> 0 X 01 ENTER_VS_BADTS  <br/> 0 X 02 ENTER_VS_ECHO  <br/> 0 X 04 ENTER_VS_FORCEORCONVERGENCE  <br/> 0 X 08 ENTER_VS_DNLP  <br/> Die Ursache kann eine Kombination dieser einzelnen Ursachen sein. ENTER_VS_FORCEORCONVERGENCE können nur von Registrierungsschlüssels zu Testzwecken aktiviert werden.  <br/> Der Datentyp für diese Spalte wurde in Microsoft Lync Server 2013 geändert.  <br/> |
|**EchoEventCauses** <br/> |tinyint  <br/> | <br/> |Ursachen für echoereignis:  <br/> 0 X 01 ECHO_EVENT_BAD_TIMESTAMP  <br/> 0 X 02 ECHO_EVENT_POSTAEC_ECHO  <br/> 0 X 04 ECHO_EVENT_ANLP  <br/> 0 X 08 ECHO_EVENT_DNLP  <br/> 0 X 10 ECHO_EVENT_MIC_CLIPPING  <br/> ECHO_EVENT_BAD_STATE 0 X 20  <br/> Die Ursache kann eine Kombination dieser einzelnen Ursachen sein.  <br/> |
|**EchoPercentMicIn** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz der Zeit, in der im Mikrofonaufnahme-Datenstrom Echo festgestellt wurde. In der Regel weisen Headsets oder Hörer niedrige Werte und Freisprechvorrichtungen oder eigenständige Lautsprecher höhere Werte auf. Bei Geräten, die eine integrierte akustische Echounterdrückung unterstützen, weisen hohe Werte auf eine Echoausbreitung hin. Für andere Geräte sollte diese Metrik nicht verwendet werden, um die Gerätequalität zu evaluieren.  <br/> |
|**EchoPercentSend** <br/> |decimal(5,2)  <br/> ||Prozentsatz der Zeit, wenn Echo in gesendete Stream erkannt wird. Hohe Echo Prozentsatz im senden Datenströme Angabe des Echo Speicherverlusten.  <br/> |
|**RxAGCSignalLevel** <br/> |int  <br/> | <br/> |Empfangen Audiosignals auf dem Vermittlungsserver vom Gateway; Dies gilt nur für den Vermittlungsserver. Die Einheit dieser Metrik ist dBoV. Für guter Qualität des Gültigkeitsbereichs [-30,-18] werden sollte dBoV.  <br/> |
|**RxAGCNoiseLevel** <br/> |int  <br/> | <br/> |Empfangene Audiosignals auf dem Vermittlungsserver vom Gateway. Dies gilt nur für den Vermittlungsserver. Die Einheit dieser Metrik ist dBoV. Für guter Qualität sollte der zulässigen Bereich weniger als-50 dBoV sein.  <br/> |
|**RxAvgAGCGain** <br/> |int  <br/> | <br/> |Eingebauter Verstärker (AGC) auf der vermittlungsserverseite.  <br/> |
|**InitialSignalLevelRMS** <br/> |float  <br/> | <br/> |Quadratischer Mittelwert (RMS) des eingehenden Signals von bis zu den ersten 30 Sekunden des Anrufs.  <br/> |
|**RecvSignalLevelCh1** <br/> |int  <br/> ||Auf Kanal 1 empfangene Signalstärke.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvSignalLevelCh2** <br/> |int  <br/> ||Auf Kanal 2 empfangene Signalstärke.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvNoiseLevelCh1** <br/> |int  <br/> ||Empfangenes Rauschen auf Kanal 1.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvNoiseLevelCh2** <br/> |int  <br/> ||Empfangenes Rauschen auf Kanal 2.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SendSignalLevelCh1** <br/> |int  <br/> ||Auf Kanal 1 gesendete Signalstärke.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SendSignalLevelCh2** <br/> |int  <br/> ||Auf Kanal 2 gesendete Signalstärke.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SendNoiseLevelCh1** <br/> |int  <br/> ||Gesendetes Rauschen auf Kanal 1.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SendNoiseLevelCh2** <br/> |int  <br/> ||Gesendetes Rauschen auf Kanal 2.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RenderLoopbackSignalLevel** <br/> |int  <br/> ||Stufe in dBFS des Signals an den Lautsprecher für die Wiedergabe gesendet. Konten für alle Gewinn Korrekturen an der empfangenen Signal. <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |   
|**RenderNoiseLevel** <br/> |int  <br/> ||Stufe in dBFS des Inhalts Noise in das Signal an die Lautsprecher gesendet wird, für die Wiedergabe <br/> |

