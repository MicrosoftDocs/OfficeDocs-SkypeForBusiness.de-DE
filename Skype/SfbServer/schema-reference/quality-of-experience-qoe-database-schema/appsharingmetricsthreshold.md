---
title: Tabelle "AppSharingMetricsThreshold"
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
ms.assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
description: In der AppSharingMetricsThreshold-Tabelle sind die optimalen und zulässigen Werte für die QoE-Daten (Quality of Experience) enthalten, die für die Anwendungsfreigabe verwendet werden. Diese Schwellenwerte werden verwendet, um zu ermitteln, ob die Anwendungsfreigabemöglichkeiten als schlecht klassifiziert werden.
ms.openlocfilehash: 747497affbf561976bc6dd626bdce060efc1eca8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809695"
---
# <a name="appsharingmetricsthreshold-table"></a>Tabelle "AppSharingMetricsThreshold"
 
In der AppSharingMetricsThreshold-Tabelle sind die optimalen und zulässigen Werte für die QoE-Daten (Quality of Experience) enthalten, die für die Anwendungsfreigabe verwendet werden. Diese Schwellenwerte werden verwendet, um zu ermitteln, ob die Anwendungsfreigabemöglichkeiten als schlecht klassifiziert werden.
  
Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**CallType** <br/> |int  <br/> |Primary  <br/> |Anruftyp, der getätigt wurde.  <br/> |
|**AppliedBandwidthLimitOptimal** <br/> |int  <br/> ||Optimale Bandbreitenbeschränkung für die Anwendungsfreigabe. Der Standardwert lautet 1000000.  <br/> |
|**AppliedBandwidthLimitAcceptable** <br/> |int  <br/> ||Zulässige Bandbreitenbeschränkung für die Anwendungsfreigabe. Der Standardwert lautet 500000.  <br/> |
|**SpoiledTilePercentTotalOptimal** <br/> |decimal(5,2)  <br/> ||Optimaler Prozentsatz für "verqualmte" Kacheln zum Klassifizieren einer Anwendungsfreigabequalität. Dieser Wert gibt den Prozentsatz des Inhalts an, der vom freigebenden Benutzer nicht an den anzeigenden Benutzer weitergegeben wurde. Inhalt kann gelöscht (oder beschädigt) werden, wenn der freigebende Benutzer Kacheln aus der Grafikquelle löscht oder wenn ASMCU-Kacheln die Kacheln des freigebenden Benutzers löschen. Der Standardwert lautet 11 Prozent  <br/> |
|**SpoiledTilePercentTotalAcceptable** <br/> |decimal(5,2)  <br/> ||Akzeptabler Prozentsatz für "verqualmte" Kacheln zum Klassifizieren einer Anwendungsfreigabequalität. Dieser Wert gibt den Prozentsatz des Inhalts an, der vom freigebenden Benutzer nicht an den anzeigenden Benutzer weitergegeben wurde. Inhalt kann gelöscht (oder beschädigt) werden, wenn der freigebende Benutzer Kacheln aus der Grafikquelle löscht, oder wenn ASMCU-Kacheln die Kacheln des freigebenden Benutzers löschen. Der Standardwert lautet 36 Prozent  <br/> |
|**JitterInterArrivalOptimal** <br/> |int  <br/> ||Diese Spalte wird in Microsoft Lync Server 2013 nicht verwendet.  <br/> |
|**JitterInterArrivalAcceptable** <br/> |int  <br/> ||Diese Spalte wird in Microsoft Lync Server 2013 nicht verwendet.  <br/> |
|**RelativeOneWayBurstDensityOptimal** <br/> |Gleitkommazahl  <br/> ||Diese Spalte wird in Microsoft Lync Server 2013 nicht verwendet.  <br/> |
|**RelativeOneWayBurstDensityAcceptable** <br/> |Gleitkommazahl  <br/> ||Diese Spalte wird in Microsoft Lync Server 2013 nicht verwendet.  <br/> |
|**RDPTileProcessingLatencyBurstDensityOptimal** <br/> |Gleitkommazahl  <br/> ||Diese Spalte wird in Microsoft Lync Server 2013 nicht verwendet.  <br/> |
|**RDPTileProcessingLatencyBurstDensityAcceptable** <br/> |Gleitkommazahl  <br/> ||Diese Spalte wird in Microsoft Lync Server 2013 nicht verwendet.  <br/> |
|**RelativeOneWayAverageOptimal** <br/> |Gleitkommazahl  <br/> ||Optimaler Wert für die relative unidirektionale Verzögerung zwischen den beiden Medienendpunkten, die in die Anwendungsfreigabe eingebunden sind. Dieser Wert stellt den Latenzwert für einen einzelnen Hop dar. Der Standardwert beträgt 1,0 Sekunden.  <br/> Die Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayAverageAcceptable** <br/> |Gleitkommazahl  <br/> ||Optimaler Wert für die relative unidirektionale Verzögerung zwischen den beiden Medienendpunkten, die in die Anwendungsfreigabe eingebunden sind. Dieser Wert stellt den Latenzwert für einen einzelnen Hop dar. Der Standardwert beträgt 1,75 Sekunden.  <br/> Die Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RDPTileProcessingLatencyAverageOptimal** <br/> |Gleitkommazahl  <br/> ||Optimaler Wert für die durchschnittliche Verarbeitungslatenz für RDP-Kacheln im AS-Konferenzserver für die Dauer der Anzeigesitzung. Wartezeit ist der Zeitunterschied zwischen dem Codieren des Startframes auf dem Server (je nach Szenario freigaber oder MCU) und dem Decodieren desselben Startframes auf dem Viewer.  <br/> Ein hoher Durchschnittswert gibt eine längere Verzögerung bei der Darstellung an. Bei einem überlasteten Konferenzserver können längere durchschnittliche Verzögerungen auftreten. Der Standardwert beträgt 200 ms.  <br/> Die Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RDPTileProcessingLatencyAverageAcceptable** <br/> |Gleitkommazahl  <br/> ||Zulässiger Wert für die durchschnittliche Verarbeitungslatenz für RDP-Kacheln im AS-Konferenzserver für die Dauer der Anzeigesitzung. Wartezeit ist der Zeitunterschied zwischen dem Codieren des Startframes auf dem Server (je nach Szenario freigaber oder MCU) und dem Decodieren desselben Startframes auf dem Viewer.  <br/> Ein hoher Durchschnittswert gibt eine längere Verzögerung bei der Darstellung an. Bei einem überlasteten Konferenzserver können längere durchschnittliche Verzögerungen auftreten. Der Standardwert beträgt 200 ms.  <br/> Die Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
   

