---
title: Tabelle "AudioSignal"
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
ms.assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
description: Jeder Datensatz stellt Audiosignalmetriken für einen Endpunkt dar. In der Regel verfügt jeder Anruf über zwei Datensätze, einen für den Anrufer und einen für den Ankrufer.
ms.openlocfilehash: ab918941357b85c6bcb25dcbaeb93a7be9c55f2d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809655"
---
# <a name="audiosignal-table"></a>Tabelle "AudioSignal"
 
Jeder Datensatz stellt Audiosignalmetriken für einen Endpunkt dar. In der Regel verfügt jeder Anruf über zwei Datensätze, einen für den Anrufer und einen für den Ankrufer. 
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |Datum/Uhrzeit  <br/> |Primary  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0: Daten des Ankrufers  <br/> 1: Daten des Anrufers  <br/> |
|**SendSignalLevel** <br/> |int  <br/> | <br/> |Stellt die Audiosignalstufe der postanalogen Verstärkungssteuerung dar. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität sind mindestens 30 dBmo erforderlich. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.  <br/> |
|**RecvSignalLevel** <br/> |int  <br/> | <br/> |Siehe SendSignalLevel.  <br/> |
|**SendNoiseLevel** <br/> |int  <br/> | <br/> |Represents the Post-Analog Gain Control audio noise level. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität muss der Wert unter 35 dBmo liegen. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.  <br/> |
|**RecvNoiseLevel** <br/> |int  <br/> | <br/> |Siehe SendNoiseLevel.  <br/> |
|**EchoReturn** <br/> |int  <br/> | <br/> |Metrik "Echorücklaufverbesserung". Die Einheit für diese Metrik ist dB. Niedrigere Werte bedeuten weniger Echo. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.  <br/> |
|**AudioSpeakerGlitchRate** <br/> |int  <br/> | <br/> |Durchschnittliche Störungen pro fünf Minuten für das Lautsprecherrendering. Um eine gute Qualität zu erzielen, sollte höchstens eine Verzögerung pro fünf Minuten auftreten. Wird nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen berichtet.  <br/> |
|**AudioMicGlitchRate** <br/> |int  <br/> | <br/> |Durchschnittliche Störungen pro fünf Minuten für die Mikrofonaufnahme. Um eine gute Qualität zu erzielen, sollte höchstens eine Verzögerung pro fünf Minuten auftreten. Wird nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen berichtet.  <br/> |
|**AudioTimestampDriftRateMic** <br/> |decimal(9,2)  <br/> | <br/> |Driftrate des Mikrofongeräts, relativ zur CPU-Uhr.  <br/> |
|**AudioTimestampDriftRateSpk** <br/> |decimal(9,2)  <br/> | <br/> |Driftrate des Lautsprechergeräts, relativ zur CPU-Uhr.  <br/> |
|**AudioTimestampErrorMicMs** <br/> |decimal(9,2)  <br/> | <br/> |Driftrate des Lautsprechergeräts, relativ zur CPU-Uhr.  <br/> Durchschnittlicher Zeitstempelfehler des Mikrofonaufnahme-Datenstroms in Millisekunden, in den letzten 20 Sekunden des Anrufs.  <br/> |
|**AudioTimestampErrorSpkMs** <br/> |decimal(9,2)  <br/> | <br/> |Durchschnittlicher Zeitstempelfehler des Lautsprechers in Millisekunden in den letzten 20 Sekunden des Anrufs.  <br/> |
|**VsEntryCauses** <br/> |smallint  <br/> | <br/> |Bei der Sprachumschaltung handelt es sich um einen Halbduplexmodus mit der Fähigkeit, Unterbrechungen zu reduzieren. Ursachen für die Sprachumschalteingabe:  <br/> ENTER_VS_BADTS 0x01  <br/> ENTER_VS_ECHO 0x02  <br/> ENTER_VS_FORCEORCONVERGENCE 0x04  <br/> ENTER_VS_DNLP 0x08  <br/> Die Ursache kann eine Kombination dieser einzelnen Ursachen sein. ENTER_VS_FORCEORCONVERGENCE kann nur von einem Registrierungskey zu Testzwecken aktiviert werden.  <br/> Der Datentyp für diese Spalte wurde in Microsoft Lync Server 2013 geändert.  <br/> |
|**EchoEventCauses** <br/> |tinyint  <br/> | <br/> |Ursachen für ein Echoereignis:  <br/> ECHO_EVENT_BAD_TIMESTAMP 0x01  <br/> ECHO_EVENT_POSTAEC_ECHO 0x02  <br/> ECHO_EVENT_ANLP 0x04  <br/> ECHO_EVENT_DNLP 0x08  <br/> ECHO_EVENT_MIC_CLIPPING 0x10  <br/> ECHO_EVENT_BAD_STATE 0x20  <br/> Die Ursache kann eine Kombination dieser einzelnen Ursachen sein.  <br/> |
|**EchoPercentMicIn** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz der Zeit, in der echo im Mikrofonaufnahmedatenstrom erkannt wurde. In der Regel sind die Werte für Headsets oder Handsets niedrig und für Freisprechtelefone oder eigenständige Lautsprecher höher. Bei Geräten, die die Echounterdrückung an Bord unterstützen, weisen hohe Werte auf ein Echoleck hin. Bei anderen Geräten sollte diese Metrik nicht zum Bewerten der Gerätequalität verwendet werden.  <br/> |
|**EchoPercentSend** <br/> |decimal(5,2)  <br/> ||Prozentsatz der Zeit, in der echo im gesendeten Datenstrom erkannt wird. Ein hoher Echoprozentsatz in gesendeten Datenströmen deutet auf eine Beeinträchtigung durch Echo hin.  <br/> |
|**TxAGCSignalLevel** <br/> |int  <br/> | <br/> |Empfangene Signalstufe auf dem Vermittlungsserver vom Gateway; Dies gilt nur für den Vermittlungsserver. Die Einheit dieser Metrik ist dBoV. Zum Erzielen einer guten Qualität sollte der akzeptable Bereich zwischen [-30 und -18] dBoV liegen.  <br/> |
|**TxAGCNoiseLevel** <br/> |int  <br/> | <br/> |Empfangene Signalstufe auf dem Vermittlungsserver vom Gateway. Dies betrifft nur den Vermittlungsserver. Die Einheit dieser Metrik ist dBoV. Zum Erzielen einer guten Qualität sollte der akzeptable Bereich unter -50 dBoV liegen.  <br/> |
|**TxAvgAGCGain** <br/> |int  <br/> | <br/> |Automatische Verstärkungssteuerung (AGC) auf der Vermittlungsserverseite.  <br/> |
|**InitialSignalLevelRMS** <br/> |Gleitkommazahl  <br/> | <br/> |Das RmS (Root Mean Square) des eingehenden Signals von bis zu den ersten 30 Sekunden des Anrufs.  <br/> |
|**RecvSignalLevelCh1** <br/> |int  <br/> ||Signalstufe, die auf Kanal 1 empfangen wird.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvSignalLevelCh2** <br/> |int  <br/> ||Signalstufe, die in Kanal 2 empfangen wird.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvNoiseLevelCh1** <br/> |int  <br/> ||Rauschstufe wie in Kanal 1 empfangen.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvNoiseLevelCh2** <br/> |int  <br/> ||Rauschstufe wie in Kanal 2 empfangen.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SendSignalLevelCh1** <br/> |int  <br/> ||Signalstufe, die auf Kanal 1 gesendet wird.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SendSignalLevelCh2** <br/> |int  <br/> ||Signalstufe, die auf Kanal 2 gesendet wird.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SendNoiseLevelCh1** <br/> |int  <br/> ||Rauschstufe wie in Kanal 1 gesendet.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SendNoiseLevelCh2** <br/> |int  <br/> ||Rauschstufe wie in Kanal 2 gesendet.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RenderLoopbackSignalLevel** <br/> |int  <br/> ||Level in dBFS des Signals, das zur Wiedergabe an den Lautsprecher gesendet wird. Konten für alle Verstärkungsanpassungen, die am empfangenen Signal vorgenommen wurden. <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |   
|**RenderNoiseLevel** <br/> |int  <br/> ||Level in dBFS des Rauschinhalts im Signal, das zur Wiedergabe an die Lautsprecher gesendet wird <br/> |

