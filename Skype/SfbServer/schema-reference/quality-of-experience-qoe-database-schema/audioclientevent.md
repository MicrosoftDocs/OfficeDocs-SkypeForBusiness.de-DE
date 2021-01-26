---
title: Tabelle "AudioClientEvent"
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
ms.assetid: fef73d8f-7261-4e5b-9769-82435b007979
description: Jeder Datensatz enthält ein Clientereignis für einen Endpunkt in einem Audioanruf. In der Regel verfügt ein Anruf über zwei Datensätze, einen für den Anrufer und einen für den Anrufer.
ms.openlocfilehash: f5211d7f4ec3bc1d366d97def06edd325c448def
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809685"
---
# <a name="audioclientevent-table"></a>Tabelle "AudioClientEvent"
 
Jeder Datensatz enthält ein Clientereignis für einen Endpunkt in einem Audioanruf. In der Regel verfügt ein Anruf über zwei Datensätze, einen für den Anrufer und einen für den Anrufer.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |Datum/Uhrzeit  <br/> |Primary  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |Referenziert aus der [MediaLine-Tabelle.](medialine-0.md)  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0: Daten des Ankrufers  <br/> 1: Daten des Anrufers  <br/> |
|**NetworkSendQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz der Sitzung, in der das Ereignis "NetworkSendQuality" für den Zustand "Schlecht" ausgelöst wurde.  <br/> Die Netzwerkqualität im Hinblick auf Jitter oder Paketverlust ist stark und wirkt sich auf die Qualität der gesendeten Audiodaten aus.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz der Sitzung, in der das "ReceiveSendQuality"-Ereignis für den Zustand "Schlecht" ausgelöst wurde.  <br/> Die Netzwerkqualität im Hinblick auf Jitter oder Paketverlust ist stark und wirkt sich auf die Qualität der empfangenen Audiodaten aus.  <br/> |
|**NetworkDelayEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz der Sitzung, in der das Verzögerungsereignis für den Zustand "Schlecht" ausgelöst wurde. Die Netzwerklatenz ist stark und wirkt sich negativ auf die Erfahrung aus, indem die interaktive Kommunikation verhindert wird.  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz der Sitzung, in der das Ereignis "LowBandwidth" für den Zustand "Schlecht" ausgelöst wurde. Die verfügbare Bandbreite reicht nicht aus, um eine akzeptable Spracherfahrung zu ermöglichen.  <br/> |
|**CPUInsufficientEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz der Sitzung, in der das nicht ausreichende CPU-Ereignis für den Zustand "Schlecht" ausgelöst wurde. Es gibt nicht genügend CPU-Zyklen für die Verarbeitung mit den aktuellen Modalitäten und Anwendungen, die verwendet werden. Dies führt zu Fälschungen beim Audiokanal.  <br/> |
|**DeviceHalfDuplexAECEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz der Sitzung, in der das DeviceHalfDuplexAEC-Ereignis für den Zustand "Schlecht" ausgelöst wurde. Um Echo zu verhindern, hat das System die Halbduplextaste verwendet.  <br/> |
|**DeviceRenderNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz der Sitzung, in der das DeviceRenderNotFunctioning-Ereignis für den Zustand "Schlecht" ausgelöst wurde. Das derzeit für die Sitzung verwendete Rendergerät funktioniert nicht ordnungsgemäß. Dies kann zu one-way-Audioproblemen führen.  <br/> |
|**DeviceCaptureNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz der Sitzung, in der das DeviceCaptureNotFunctioning-Ereignis für den Zustand "Schlecht" ausgelöst wurde. Das derzeit für die Sitzung verwendete Aufnahmegerät funktioniert nicht ordnungsgemäß. Dies kann zu one-way-Audioproblemen führen.  <br/> |
|**DeviceGlitchesEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz der Sitzung, in der das DeviceGlitches -Ereignis für den Zustand "Schlecht" ausgelöst wurde. Es gibt schwerwiegende Störungen beim Rendern von Audio, was zu Fälschungen führt. Diese Störungen können durch Treiberprobleme, verzögerte Prozeduraufrufe (DPC)-Anstürze (Drivers) und eine hohe CPU-Auslastung verursacht werden.  <br/> |
|**DeviceLowSNREventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz der Sitzung, in der das DeviceLowSNR-Ereignis für den Zustand "Schlecht" ausgelöst wurde. Die Aufnahmequalität ist sehr schlecht, entweder sehr laut oder der Benutzer spricht zu weit vom Mikrofon entfernt. Dies führt zu Fälschungen.  <br/> |
|**DeviceLowSpeechLevelEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz der Sitzung, in der das DeviceLowSpeechLevel-Ereignis für den Zustand "Schlecht" ausgelöst wurde. Die Sprachstufe des Benutzers ist zu niedrig, und das System kann sie nicht weiter erhöhen. Dies kann entweder zu Fälschungen führen oder als ein-wege-Audio wahrgenommen werden.  <br/> |
|**DeviceClippingEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Prozentsatz der Sitzung, in der das DeviceClipping -Ereignis für den Zustand "Schlecht" ausgelöst wurde.  <br/> Wenn das Mikrofon von der Fast-End-Spracherkennung abgeschnitten wird, hört das Ende eine Verzerrung aufgrund von Clipping. Es ist wichtig, das Zuschneiden des Nah-End-Mikrofons zu vermeiden.  <br/> |
|**DeviceEchoEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz der Sitzung, in der das DeviceEchoEvent-Ereignis für den Zustand "Schlecht" ausgelöst wurde. Das Gerät oder setup verursacht Echo über die Fähigkeit des Systems, dies zu kompensieren.  <br/> |
|**DeviceNearEndToEchoRatioEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz der Sitzung, in der das DeviceNearEndToEchoRatio-Ereignis für den Zustand "Schlecht" ausgelöst wurde. Die Spracherkennung des Benutzers ist im Vergleich zum erfassten Echo zu niedrig, was sich auf die Benutzererfahrung ausdäht, da die Unterbrechung eines Benutzers dadurch begrenzt wird. Reduzieren Sie die Lautsprecherlautstärke, bewegen Sie das Mikrofon näher an den Talker.  <br/> |
|**DeviceMultipleEndpointsEventCount** <br/> |int  <br/> ||Gibt an, wie oft das DeviceMultipleEndpoints-Ereignis während der Sitzung für den Zustand "Schlecht" ausgelöst wurde. Mehrere Audioendpunkte in derselben Sitzung erkannt, und das System hat die Renderlautstärke reduziert.  <br/> |
|**DeviceHowlingEventCount** <br/> |int  <br/> | <br/> |Anzahl der Male während der Sitzung, mit der das DeviceHowlingEvent-Ereignis für den Zustand "Schlecht" ausgelöst wurde. Audiofeedbackschleife erkannt (verursacht durch mehrere Endpunkte, die den Audiopfad gemeinsam verwenden).  <br/> |
|**DeviceRenderZeroVolumeEventRatio** <br/> |decimal(5,2)  <br/> ||Prozentsatz der Sitzung, für die das Ereignis "DeviceRenderZeroVolume" im Zustand "Schlecht" ausgelöst wurde. Das Rendergerät wurde auf null Volume festgelegt.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**DeviceRenderMuteEventRatio** <br/> |decimal(5,2)  <br/> ||Prozentsatz der Sitzung, für die das DeviceRenderMute-Ereignis ausgelöst wurde, da es den Status "Schlecht" hat. Das Rendergerät wurde stummgeschaltet.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
   

