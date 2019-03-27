---
title: AudioClientEvent-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fef73d8f-7261-4e5b-9769-82435b007979
description: Jeder Datensatz enthält ein Clientereignis für einen Endpunkt in einen Audioanruf. In der Regel muss ein Anruf zwei Datensätze, einen für Anrufer und einen für des angerufenen.
ms.openlocfilehash: 307406446d71adf462cdc8a0345aa823129a8f99
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895055"
---
# <a name="audioclientevent-table"></a>AudioClientEvent-Tabelle
 
Jeder Datensatz enthält ein Clientereignis für einen Endpunkt in einen Audioanruf. In der Regel muss ein Anruf zwei Datensätze, einen für Anrufer und einen für des angerufenen.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Verweis von der [MediaLine-Tabelle](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Verweis von der [MediaLine-Tabelle](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |Verweis von der [MediaLine-Tabelle](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0: Daten des angerufenen  <br/> 1: Daten des Anrufers  <br/> |
|**NetworkSendQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz von Sitzungen, in denen das NetworkSendQuality-Ereignis ausgelöst wurde 'Beschädigten' Zustand.  <br/> Netzwerkqualität in Bezug auf Jitter oder Paketverlusten erheblich ist und die Qualität der gesendeten Audiodaten beeinträchtigen.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz von Sitzungen, in denen das ReceiveSendQuality-Ereignis ausgelöst wurde 'Beschädigten' Zustand.  <br/> Netzwerkqualität in Bezug auf Jitter oder Paketverlusten erheblich ist und die Qualität der empfangenen Audiodaten beeinträchtigen.  <br/> |
|**NetworkDelayEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz von Sitzungen, in denen das Delay-Ereignis ausgelöst wurde 'Beschädigten' Zustand. Netzwerklatenz wird erheblich und Paketverlust beeinflusst die Erfahrung von interaktiven Kommunikation verhindern  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz von Sitzungen, in denen das LowBandwidth-Ereignis ausgelöst wurde 'Beschädigten' Zustand. Die verfügbare Bandbreite ist für eine akzeptable VoIP wünschen unzureichend.  <br/> |
|**CPUInsufficientEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz von Sitzungen, in denen das nicht genügend CPU-Ereignis ausgelöst wurde 'Beschädigten' Zustand. Es gibt nicht genügend CPU-Zyklen für die Verarbeitung mit den aktuellen Modalitäten und Clientanwendungen verwendet. Daraufhin wird die Verzerrungen mit der Audiokanal.  <br/> |
|**DeviceHalfDuplexAECEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz von Sitzungen, in denen das DeviceHalfDuplexAEC-Ereignis ausgelöst wurde 'Beschädigten' Zustand. Um Echoeffekte zu verhindern, dass das System hat Geben Sie Hälfte Duplex.  <br/> |
|**DeviceRenderNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz von Sitzungen, in denen das DeviceRenderNotFunctioning-Ereignis ausgelöst wurde 'Beschädigten' Zustand. Das aktuell für die Sitzung verwendete darstellungsgerät funktioniert nicht richtig. Dies kann unidirektionale Audioprobleme verursachen.  <br/> |
|**DeviceCaptureNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz von Sitzungen, in denen das DeviceCaptureNotFunctioning-Ereignis ausgelöst wurde 'Beschädigten' Zustand. Das aktuell für die Sitzung verwendete Aufnahmegerät ist nicht ordnungsgemäß funktionsfähig. Dies kann unidirektionale Audioprobleme verursachen.  <br/> |
|**DeviceGlitchesEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz von Sitzungen, in denen das DeviceGlitches-Ereignis ausgelöst wurde 'Beschädigten' Zustand. Schwerwiegender Fehler sind in das Rendering des Verzerrungen verursacht Audio vorhanden. Dieser Fehler können durch Treiberprobleme, zurückgestellte Verfahren Anrufe (DPC) Storm (Treiber) und hohe CPU-Auslastung verursacht werden.  <br/> |
|**DeviceLowSNREventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz von Sitzungen, in denen das DeviceLowSNR-Ereignis ausgelöst wurde 'Beschädigten' Zustand. Qualität der Aufnahme ist entweder sehr niedrige sehr laut oder Benutzer spricht zu weit vom Mikrofon. Dadurch werden Verzerrungen.  <br/> |
|**DeviceLowSpeechLevelEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz von Sitzungen, in denen das DeviceLowSpeechLevel-Ereignis ausgelöst wurde 'Beschädigten' Zustand. Sprachpegel des Benutzers ist zu niedrig, und das System nicht erhöht werden alle weiter. Dies kann entweder Verzerrungen oder als unidirektionale audioübertragung wahrgenommen.  <br/> |
|**DeviceClippingEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Prozentsatz von Sitzungen, in denen das DeviceClipping-Ereignis ausgelöst wurde 'Beschädigten' Zustand.  <br/> Wenn in Ihrer Nähe End-Spracherkennung das Mikrofon clips, hört weit End Distortion aufgrund Clipping. Es ist wichtig, in der Nähe End Mikrofon, Clipping zu vermeiden.  <br/> |
|**DeviceEchoEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz von Sitzungen, in denen das DeviceEchoEvent-Ereignis ausgelöst wurde 'Beschädigten' Zustand. Gerät oder Setup verursacht Echo des Systems nicht mehr auszugleichen.  <br/> |
|**DeviceNearEndToEchoRatioEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz von Sitzungen, in denen das DeviceNearEndToEchoRatio-Ereignis ausgelöst wurde 'Beschädigten' Zustand. Sprache des Benutzers ist zu niedrig im Vergleich zu das Echo aufgezeichnet werden, die die Benutzer-Erlebnis wirkt sich auf, da es wie einfach ist beschränkt, einen Benutzer zu unterbrechen. Reduzieren Sie die Lautstärke des Lautsprechers, führen Sie das Mikrofon näher an der Sprecher.  <br/> |
|**DeviceMultipleEndpointsEventCount** <br/> |int  <br/> ||Anzahl von Fehlern bei der Sitzungen, in denen das DeviceMultipleEndpoints-Ereignis ausgelöst wurde 'Beschädigten' Zustand. Mehrere audioendpunkte in derselben Sitzung erkannt und das System wurde durch die Reduzierung von Render Volume Vergütung.  <br/> |
|**DeviceHowlingEventCount** <br/> |int  <br/> | <br/> |Anzahl von Fehlern bei der Sitzungen, in denen das DeviceHowlingEvent-Ereignis ausgelöst wurde 'Beschädigten' Zustand. Audiorückkopplung Schleife entdeckt (verursacht durch mehrere Endpunkte, die Freigabe von audio Pfad).  <br/> |
|**DeviceRenderZeroVolumeEventRatio** <br/> |decimal(5,2)  <br/> ||Prozentsatz von Sitzungen das DeviceRenderZeroVolume-Ereignis wurde ausgelöst wird, der "fehlerhafte" Zustand. Das darstellungsgerät wurde ohne Lautstärke festgelegt.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**DeviceRenderMuteEventRatio** <br/> |decimal(5,2)  <br/> ||Prozentsatz von Sitzungen das DeviceRenderMute-Ereignis wurde ausgelöst wird, der "fehlerhafte" Zustand. Das darstellungsgerät wurde stumm geschaltet.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
   

