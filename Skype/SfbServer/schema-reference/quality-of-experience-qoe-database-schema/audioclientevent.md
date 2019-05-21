---
title: AudioClientEvent-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fef73d8f-7261-4e5b-9769-82435b007979
description: Jeder Datensatz enthält ein Clientereignis für einen Endpunkt in einem Audioanruf. In der Regel verfügt ein Anruf über zwei Datensätze, einen für den Anrufer und einen für den aufgerufenen.
ms.openlocfilehash: 1f754f9b7ef19919503988d40347fdeb218830d5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295104"
---
# <a name="audioclientevent-table"></a>AudioClientEvent-Tabelle
 
Jeder Datensatz enthält ein Clientereignis für einen Endpunkt in einem Audioanruf. In der Regel verfügt ein Anruf über zwei Datensätze, einen für den Anrufer und einen für den aufgerufenen.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |In der medialinie- [Tabelle](medialine-0.md)referenziert.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |In der medialinie- [Tabelle](medialine-0.md)referenziert.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |In der medialinie- [Tabelle](medialine-0.md)referenziert.  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0: Daten des angerufenen  <br/> 1: Daten des Anrufers  <br/> |
|**NetworkSendQualityEventRatio** <br/> |Dezimal (5; 2)  <br/> | <br/> |Prozentsatz der Sitzung, für die das NetworkSendQuality-Ereignis für den Zustand "falsch" ausgelöst wurde.  <br/> Die Netzwerkqualität in Bezug auf Jitter oder Paketverlust ist schwerwiegend und beeinträchtigt die Qualität des gesendeten Audiosignals.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> |Dezimal (5; 2)  <br/> | <br/> |Prozentsatz der Sitzung, für die das ReceiveSendQuality-Ereignis für den Zustand "falsch" ausgelöst wurde.  <br/> Die Netzwerkqualität in Bezug auf Jitter oder Paketverlust ist schwerwiegend und beeinträchtigt die Qualität des empfangenen Audiosignals.  <br/> |
|**NetworkDelayEventRatio** <br/> |Dezimal (5; 2)  <br/> | <br/> |Prozentsatz der Sitzung, für die das Delay-Ereignis für den Zustand "falsch" ausgelöst wurde. Die Netzwerklatenz ist schwerwiegend und beeinträchtigt die Erfahrung, indem Sie die interaktive Kommunikation verhindert.  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> |Dezimal (5; 2)  <br/> | <br/> |Prozentsatz der Sitzung, für die das LowBandwidth-Ereignis für den Zustand "falsch" ausgelöst wurde. Die verfügbare Bandbreite reicht für ein akzeptables Spracherlebnis nicht aus.  <br/> |
|**CPUInsufficientEventRatio** <br/> |Dezimal (5; 2)  <br/> | <br/> |Prozentsatz der Sitzung das unzureichende CPU-Ereignis wurde für den Zustand "falsch" ausgelöst. Es gibt unzureichende CPU-Zyklen für die Verarbeitung mit den aktuellen Modalitäten und Anwendungen, die verwendet werden. Dies verursacht Verzerrungen beim Audiokanal.  <br/> |
|**DeviceHalfDuplexAECEventRatio** <br/> |Dezimal (5; 2)  <br/> | <br/> |Prozentsatz der Sitzung, für die das DeviceHalfDuplexAEC-Ereignis für den Zustand "falsch" ausgelöst wurde. Um Echo zu verhindern, hat das System die Eingabe Hälfte Duplex.  <br/> |
|**DeviceRenderNotFunctioningEventRatio** <br/> |Dezimal (5; 2)  <br/> | <br/> |Prozentsatz der Sitzung, für die das DeviceRenderNotFunctioning-Ereignis für den Zustand "falsch" ausgelöst wurde. Das Rendering-Gerät, das derzeit für die Sitzung verwendet wird, funktioniert nicht ordnungsgemäß. Dies kann zu einseitigen Audioproblemen führen.  <br/> |
|**DeviceCaptureNotFunctioningEventRatio** <br/> |Dezimal (5; 2)  <br/> | <br/> |Prozentsatz der Sitzung, für die das DeviceCaptureNotFunctioning-Ereignis für den Zustand "falsch" ausgelöst wurde. Das Aufnahmegerät, das derzeit für die Sitzung verwendet wird, funktioniert nicht ordnungsgemäß. Dies kann zu einseitigen Audioproblemen führen.  <br/> |
|**DeviceGlitchesEventRatio** <br/> |Dezimal (5; 2)  <br/> | <br/> |Prozentsatz der Sitzung, für die das DeviceGlitches-Ereignis für den Zustand "falsch" ausgelöst wurde. Bei der Wiedergabe von Audio, die zu Verzerrungen führt, gibt es schwere Störungen. Diese Störungen können durch Treiber Probleme, verzögerte Prozeduraufrufe (DPC) Storm (Treiber) und eine höhere CPU-Auslastung verursacht werden.  <br/> |
|**DeviceLowSNREventRatio** <br/> |Dezimal (5; 2)  <br/> | <br/> |Prozentsatz der Sitzung, für die das DeviceLowSNR-Ereignis für den Zustand "falsch" ausgelöst wurde. Die Aufnahmequalität ist sehr schlecht, entweder sehr laut oder der Nutzer spricht zu weit vom Mikrofon entfernt. Dies führt zu Verzerrungen.  <br/> |
|**DeviceLowSpeechLevelEventRatio** <br/> |Dezimal (5; 2)  <br/> | <br/> |Prozentsatz der Sitzung, für die das DeviceLowSpeechLevel-Ereignis für den Zustand "falsch" ausgelöst wurde. Der Sprachpegel des Benutzers ist zu gering, und das System kann ihn nicht weiter erhöhen. Dies kann entweder zu Verzerrungen führen oder als unidirektionale Audiowiedergabe wahrgenommen werden.  <br/> |
|**DeviceClippingEventRatio** <br/> |Dezimal (5; 2)  <br/> | <br/> |Prozentsatz der Sitzung, für die das DeviceClipping-Ereignis für den Zustand "falsch" ausgelöst wurde.  <br/> Wenn das Mikrofon in der Nähe von Sprachausgabe Clips abgespielt wird, hören Sie Verzerrungen durch Clipping. Es ist wichtig, das Mikrofon-Clipping in der Nähe zu vermeiden.  <br/> |
|**DeviceEchoEventRatio** <br/> |Dezimal (5; 2)  <br/> | <br/> |Prozentsatz der Sitzung, für die das DeviceEchoEvent-Ereignis für den Zustand "falsch" ausgelöst wurde. Gerät oder Setup verursacht Echo über die Fähigkeit des Systems hinaus, dies zu kompensieren.  <br/> |
|**DeviceNearEndToEchoRatioEventRatio** <br/> |Dezimal (5; 2)  <br/> | <br/> |Prozentsatz der Sitzung, für die das DeviceNearEndToEchoRatio-Ereignis für den Zustand "falsch" ausgelöst wurde. Die Sprache des Benutzers ist im Vergleich zu dem aufgenommenen Echo zu gering, was sich auf die Benutzererfahrung auswirkt, weil dadurch die Benutzerfreundlichkeit eingeschränkt wird. Verringern Sie die Lautstärke des Mikrofons, und bewegen Sie das Mikrofon näher an den Redner.  <br/> |
|**DeviceMultipleEndpointsEventCount** <br/> |int  <br/> ||Häufigkeit, mit der während der Sitzung das DeviceMultipleEndpoints-Ereignis für den Zustand "falsch" ausgelöst wurde. Mehrere Audio-Endpunkte in derselben Sitzung wurden erkannt, und das System hat durch Reduzieren der rendermenge kompensiert.  <br/> |
|**DeviceHowlingEventCount** <br/> |int  <br/> | <br/> |Häufigkeit, mit der während der Sitzung das DeviceHowlingEvent-Ereignis für den Zustand "falsch" ausgelöst wurde. Audiofeedback-Schleife erkannt (verursacht durch mehrere Endpunkte, die einen Audiopfad freigeben).  <br/> |
|**DeviceRenderZeroVolumeEventRatio** <br/> |Dezimal (5; 2)  <br/> ||Der Prozentsatz der Sitzung, für die das DeviceRenderZeroVolume-Ereignis ausgelöst wurde, weil es sich im Zustand "ungültig" befand. Das Render-Gerät wurde auf NULL Lautstärke eingestellt.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**DeviceRenderMuteEventRatio** <br/> |Dezimal (5; 2)  <br/> ||Der Prozentsatz der Sitzung, für die das DeviceRenderMute-Ereignis ausgelöst wurde, weil es sich im Zustand "ungültig" befand. Das Render-Gerät war stumm geschaltet.  <br/> Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
   

