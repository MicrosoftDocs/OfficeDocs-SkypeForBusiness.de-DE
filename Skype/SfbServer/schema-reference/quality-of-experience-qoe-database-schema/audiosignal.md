---
title: AudioSignal-Tabelle
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
ms.localizationpriority: medium
ms.assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
description: Jeder Datensatz stellt Audiosignalmetriken für einen Endpunkt dar. In der Regel hat jeder Anruf zwei Datensätze, einen für den Anrufer und einen für den Angerufenen.
ms.openlocfilehash: 0f021b438fe31bf180ee06ce83dad86e01c04070
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58592399"
---
# <a name="audiosignal-table"></a>AudioSignal-Tabelle
 
Jeder Datensatz stellt Audiosignalmetriken für einen Endpunkt dar. In der Regel hat jeder Anruf zwei Datensätze, einen für den Anrufer und einen für den Angerufenen. 
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |Datum/Uhrzeit  <br/> |Primary  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|**MediaLineLabel** <br/> |Tinyint  <br/> |Primary  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|**FromCaller** <br/> |Bit  <br/> |Primary  <br/> |0: Daten des Angerufenen  <br/> 1: Anruferdaten  <br/> |
|**SendSignalLevel** <br/> |int  <br/> | <br/> |Stellt die Post-Analog Gain Control-Audiosignalstufe dar. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität sind mindestens 30 dBmo erforderlich. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.  <br/> |
|**RecvSignalLevel** <br/> |int  <br/> | <br/> |Siehe SendSignalLevel.  <br/> |
|**SendNoiseLevel** <br/> |int  <br/> | <br/> |Stellt das Audiorauschen nach der analogen Verstärkungssteuerung dar. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität muss der Wert unter 35 dBmo liegen. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.  <br/> |
|**RecvNoiseLevel** <br/> |int  <br/> | <br/> |Siehe SendNoiseLevel.  <br/> |
|**EchoReturn** <br/> |int  <br/> | <br/> |Metrik zur Verbesserung des Echorücklaufs. Die Einheit für diese Metrik ist dB. Niedrigere Werte bedeuten weniger Echo. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.  <br/> |
|**AudioSpeakerGlitchRate** <br/> |int  <br/> | <br/> |Durchschnittliche Störungen pro fünf Minuten für das Rendern des Renderings. Um eine gute Qualität zu erzielen, sollte höchstens eine Verzögerung pro fünf Minuten auftreten. Wird nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen berichtet.  <br/> |
|**AudioMicGlitchRate** <br/> |int  <br/> | <br/> |Durchschnittliche Störungen pro fünf Minuten für die Mikrofonaufnahme. Um eine gute Qualität zu erzielen, sollte höchstens eine Verzögerung pro fünf Minuten auftreten. Wird nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen berichtet.  <br/> |
|**AudioTimestampDriftRateMic** <br/> |decimal(9,2)  <br/> | <br/> |Taktfrequenz des Mikrofongeräts, relativ zur CPU-Uhr.  <br/> |
|**AudioTimestampDriftRateSpk** <br/> |decimal(9,2)  <br/> | <br/> |Taktfrequenz des Lautsprechergeräts, relativ zur CPU-Uhr.  <br/> |
|**AudioTimestampErrorMicMs** <br/> |decimal(9,2)  <br/> | <br/> |Taktfrequenz des Lautsprechergeräts, relativ zur CPU-Uhr.  <br/> Durchschnittlicher Zeitstempelfehler des Mikrofonaufnahme-Datenstroms in Millisekunden, in den letzten 20 Sekunden des Anrufs.  <br/> |
|**AudioTimestampErrorSpkMs** <br/> |decimal(9,2)  <br/> | <br/> |Durchschnittlicher Fehler beim Rendern des Zeitstempels des Lautsprechers in Millisekunden in den letzten 20 Sekunden des Anrufs.  <br/> |
|**VsEntryCauses** <br/> |Smallint  <br/> | <br/> |Bei der Sprachumschaltung handelt es sich um einen Halbduplexmodus mit der Fähigkeit, Unterbrechungen zu reduzieren. Ursachen für die Sprachumschaltung:  <br/> ENTER_VS_BADTS 0x01  <br/> ENTER_VS_ECHO 0x02  <br/> ENTER_VS_FORCEORCONVERGENCE 0x04  <br/> ENTER_VS_DNLP 0x08  <br/> Die Ursache kann eine Kombination dieser einzelnen Ursachen sein. ENTER_VS_FORCEORCONVERGENCE können nur mithilfe eines Registrierungsschlüssels zu Testzwecken aktiviert werden.  <br/> Der Datentyp für diese Spalte wurde in Microsoft Lync Server 2013 geändert.  <br/> |
|**EchoEventCauses** <br/> |Tinyint  <br/> | <br/> |Ursachen eines Echoereignisses:  <br/> ECHO_EVENT_BAD_TIMESTAMP 0x01  <br/> ECHO_EVENT_POSTAEC_ECHO 0x02  <br/> ECHO_EVENT_ANLP 0x04  <br/> ECHO_EVENT_DNLP 0x08  <br/> ECHO_EVENT_MIC_CLIPPING 0x10  <br/> ECHO_EVENT_BAD_STATE 0x20  <br/> Die Ursache kann eine Kombination dieser einzelnen Ursachen sein.  <br/> |
|**EchoPercentMicIn** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz der Zeit, in der echo im Mikrofonaufnahmedatenstrom erkannt wurde. In der Regel sind die Werte für Headsets oder Handsets niedrig und für Lautsprechertelefone oder eigenständige Lautsprecher höher. Bei Geräten, die die lokale akustische Echounterdrückung unterstützen, deuten hohe Werte auf einen Echoverlust hin. Bei anderen Geräten sollte diese Metrik nicht verwendet werden, um die Gerätequalität zu bewerten.  <br/> |
|**EchoPercentSend** <br/> |decimal(5,2)  <br/> ||Prozentsatz der Zeit, in der Echo im gesendeten Datenstrom erkannt wird. Ein hoher Echoprozentsatz in gesendeten Datenströmen deutet auf eine Beeinträchtigung durch Echo hin.  <br/> |
|**RxAGCSignalLevel** <br/> |int  <br/> | <br/> |Empfangene Signalstufe auf dem Vermittlungsserver vom Gateway; dies gilt nur für den Vermittlungsserver. Die Einheit dieser Metrik ist dBoV. Zum Erzielen einer guten Qualität sollte der akzeptable Bereich zwischen [-30 und -18] dBoV liegen.  <br/> |
|**RxAGCNoiseLevel** <br/> |int  <br/> | <br/> |Empfangene Signalstufe auf dem Vermittlungsserver vom Gateway. Dies betrifft nur den Vermittlungsserver. Die Einheit dieser Metrik ist dBoV. Zum Erzielen einer guten Qualität sollte der akzeptable Bereich unter -50 dBoV liegen.  <br/> |
|**RxAvgAGCGain** <br/> |int  <br/> | <br/> |Automatische Verstärkungssteuerung (Automatic Gain Control, AGC) auf der Seite des Vermittlungsservers.  <br/> |
|**InitialSignalLevelRMS** <br/> |Gleitkommazahl  <br/> | <br/> |Das Stammmittelmittelquadrat (RMS) des eingehenden Signals von bis zu den ersten 30 Sekunden des Anrufs.  <br/> |
|**RecvSignalLevelCh1** <br/> |int  <br/> ||Signalstufe wie in Kanal 1 empfangen.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvSignalLevelCh2** <br/> |int  <br/> ||Signalstufe wie in Kanal 2 empfangen.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvNoiseLevelCh1** <br/> |int  <br/> ||Rauschen, wie er in Kanal 1 empfangen wurde.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RecvNoiseLevelCh2** <br/> |int  <br/> ||Rauschen, wie er in Kanal 2 empfangen wurde.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SendSignalLevelCh1** <br/> |int  <br/> ||Signalstufe wie in Kanal 1 gesendet.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SendSignalLevelCh2** <br/> |int  <br/> ||Signalstufe wie in Kanal 2 gesendet.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SendNoiseLevelCh1** <br/> |int  <br/> ||Rauschen, wie er in Kanal 1 gesendet wird.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SendNoiseLevelCh2** <br/> |int  <br/> ||Rauschen, wie in Kanal 2 gesendet.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RenderLoopbackSignalLevel** <br/> |int  <br/> ||Ebene in dBFS des Signals, das an die Wiedergabe gesendet wird. Konten für alle Verstärkungsanpassungen, die am empfangenen Signal vorgenommen wurden. <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |   
|**RenderNoiseLevel** <br/> |int  <br/> ||Level in dBFS des Rauschinhalts im Signal, das für die Wiedergabe an die Wiedergabe gesendet wird <br/> |

