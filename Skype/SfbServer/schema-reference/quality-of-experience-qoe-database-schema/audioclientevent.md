---
title: AudioClientEvent-Tabelle
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: fef73d8f-7261-4e5b-9769-82435b007979
description: 'Jeder Datensatz enthält ein Clientereignis für einen Endpunkt in einem Audioanruf. In der Regel hat ein Anruf zwei Datensätze, einen für den Anrufer und einen für den Angerufenen.'
---

# <a name="audioclientevent-table"></a>AudioClientEvent-Tabelle
 
Jeder Datensatz enthält ein Clientereignis für einen Endpunkt in einem Audioanruf. In der Regel hat ein Anruf zwei Datensätze, einen für den Anrufer und einen für den Angerufenen.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |Datum/Uhrzeit  <br/> |Primary  <br/> |Referenziert aus der [MediaLine-Tabelle](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Referenziert aus der [MediaLine-Tabelle](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |Tinyint  <br/> |Primary  <br/> |Referenziert aus der [MediaLine-Tabelle](medialine-0.md).  <br/> |
|**FromCaller** <br/> |Bit  <br/> |Primary  <br/> |0: Daten des Angerufenen  <br/> 1: Anruferdaten  <br/> |
|**NetworkSendQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz der Sitzung, in der das NetworkSendQuality-Ereignis für den Status "Ungültig" ausgelöst wurde.  <br/> Die Netzwerkqualität im Hinblick auf Jitter oder Paketverlust ist schwerwiegend und wirkt sich auf die Qualität der gesendeten Audiodaten aus.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz der Sitzung, für die das ReceiveSendQuality-Ereignis für den Status "Ungültig" ausgelöst wurde.  <br/> Die Netzwerkqualität im Hinblick auf Jitter oder Paketverlust ist schwerwiegend und wirkt sich auf die Qualität der empfangenen Audiodaten aus.  <br/> |
|**NetworkDelayEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz der Sitzung, für die das Verzögerungsereignis für den Status "Ungültig" ausgelöst wurde. Die Netzwerklatenz ist schwerwiegend und wirkt sich auf die Benutzererfahrung aus, indem die interaktive Kommunikation verhindert wird.  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz der Sitzung, in der das LowBandwidth-Ereignis für den Status "Ungültig" ausgelöst wurde. Die verfügbare Bandbreite reicht für eine akzeptable Spracherfahrung nicht aus.  <br/> |
|**CPUInsufficientEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz der Sitzung, für die das unzureichende CPU-Ereignis für den Zustand "Ungültig" ausgelöst wurde. Es gibt unzureichende CPU-Zyklen für die Verarbeitung mit den aktuellen Verwendeten Modalitäten und Anwendungen. Dies führt zu Beeinträchtigungen beim Audiokanal.  <br/> |
|**DeviceHalfDuplexAECEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz der Sitzung, in der das DeviceHalfDuplexAEC-Ereignis für den Status "Ungültig" ausgelöst wurde. Um Echo zu verhindern, ist das System halbduplex.  <br/> |
|**DeviceRenderNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz der Sitzung, in der das DeviceRenderNotFunctioning-Ereignis für den Zustand "Ungültig" ausgelöst wurde. Das derzeit für die Sitzung verwendete Rendergerät funktioniert nicht ordnungsgemäß. Dies kann unidirektionale Audioprobleme verursachen.  <br/> |
|**DeviceCaptureNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz der Sitzung, in der das DeviceCaptureNotFunctioning-Ereignis für den Status "Ungültig" ausgelöst wurde. Das aufnahmegerät, das derzeit für die Sitzung verwendet wird, funktioniert nicht ordnungsgemäß. Dies kann unidirektionale Audioprobleme verursachen.  <br/> |
|**DeviceGlitchesEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz der Sitzung, für die das DeviceGlitches-Ereignis für den Status "Ungültig" ausgelöst wurde. Es gibt schwerwiegende Störungen beim Rendern von Audio, was zu Verzerrung führt. Diese Störungen können durch Treiberprobleme, verzögerte Prozeduraufrufe (DPC) (Treiber) und eine hohe CPU-Auslastung verursacht werden.  <br/> |
|**DeviceLowSNREventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz der Sitzung, in der das DeviceLowSNR-Ereignis für den Status "Ungültig" ausgelöst wurde. Die Aufnahmequalität ist sehr schlecht, entweder sehr laut oder der Benutzer spricht zu weit vom Mikrofon weg. Dies führt zu Verzerrung.  <br/> |
|**DeviceLowSpeechLevelEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz der Sitzung, in der das DeviceLowSpeechLevel-Ereignis für den Status "Ungültig" ausgelöst wurde. Die Sprachstufe des Benutzers ist zu niedrig, und das System kann sie nicht weiter erhöhen. Dies kann entweder zu Verzerrung führen oder als unidirektionales Audio wahrgenommen werden.  <br/> |
|**DeviceClippingEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Prozentsatz der Sitzung, in der das DeviceClipping-Ereignis für den Status "Ungültig" ausgelöst wurde.  <br/> Wenn die Fast-End-Spracherkennung das Mikrofon einklammert, hört far-end Verzerrung aufgrund des Zuschneidens. Es ist wichtig, dass Sie nah am Ende keine Mikrofonbeschneidung verwenden.  <br/> |
|**DeviceEchoEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz der Sitzung, in der das DeviceEchoEvent-Ereignis für den Status "Ungültig" ausgelöst wurde. Gerät oder Setup verursacht Echo, das über die Fähigkeit des Systems zum Ausgleich hinausgeht.  <br/> |
|**DeviceNearEndToEchoRatioEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Prozentsatz der Sitzung, in der das DeviceNearEndToEchoRatio-Ereignis für den Zustand "Schlecht" ausgelöst wurde. Die Spracherkennung des Benutzers ist zu niedrig im Vergleich zu dem erfassten Echo, was sich auf die Benutzerfreundlichkeit auswirkt, da es die Unterbrechung eines Benutzers einschränkt. Reduzieren Sie die Lautstärke des Lautsprechers, verschieben Sie das Mikrofon näher an den Talker.  <br/> |
|**DeviceMultipleEndpointsEventCount** <br/> |int  <br/> ||Gibt an, wie oft während der Sitzung das DeviceMultipleEndpoints-Ereignis für den Zustand "Ungültig" ausgelöst wurde. Es wurden mehrere Audioendpunkte in derselben Sitzung erkannt, und das System verfügt über einen Ausfall, indem die Renderlautstärke reduziert wird.  <br/> |
|**DeviceHowlingEventCount** <br/> |int  <br/> | <br/> |Gibt an, wie oft während der Sitzung das DeviceHowlingEvent-Ereignis für den Status "Ungültig" ausgelöst wurde. Audiofeedbackschleife erkannt (verursacht durch mehrere Endpunkte, die den Audiopfad teilen).  <br/> |
|**DeviceRenderZeroVolumeEventRatio** <br/> |decimal(5,2)  <br/> ||Prozentsatz der Sitzung, für die das DeviceRenderZeroVolume-Ereignis ausgelöst wurde, da es sich im Zustand "Schlecht" befindet. Das Rendergerät wurde auf null Volume festgelegt.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**DeviceRenderMuteEventRatio** <br/> |decimal(5,2)  <br/> ||Prozentsatz der Sitzung, für die das DeviceRenderMute-Ereignis ausgelöst wurde, um sich im Zustand "Schlecht" zu befinden. Das Rendergerät wurde stummgeschaltet.  <br/> Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
   

