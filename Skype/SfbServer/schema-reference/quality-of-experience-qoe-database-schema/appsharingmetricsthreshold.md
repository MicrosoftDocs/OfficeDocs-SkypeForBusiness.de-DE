---
title: AppSharingMetricsThreshold-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
description: Die AppSharingMetricsThreshold-Tabelle enthält optimale und akzeptable Werte für die Qualität der Erfahrungs Metrik, die bei der Anwendungsfreigabe verwendet wird. Diese Schwellenwerte werden verwendet, um festzustellen, ob die Anwendungsfreigabe Erfahrung als "schlecht" klassifiziert werden soll.
ms.openlocfilehash: d3e7bab384c5fffea59e165d5fdf4e6b3d0c09a9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295125"
---
# <a name="appsharingmetricsthreshold-table"></a>AppSharingMetricsThreshold-Tabelle
 
Die AppSharingMetricsThreshold-Tabelle enthält optimale und akzeptable Werte für die Qualität der Erfahrungs Metrik, die bei der Anwendungsfreigabe verwendet wird. Diese Schwellenwerte werden verwendet, um festzustellen, ob die Anwendungsfreigabe Erfahrung als "schlecht" klassifiziert werden soll.
  
Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**CallType** <br/> |int  <br/> |Primary  <br/> |Der Typ des Anrufs, der getätigt wurde.  <br/> |
|**AppliedBandwidthLimitOptimal** <br/> |int  <br/> ||Optimale Bandbreitenbeschränkung bei der Anwendungsfreigabe. Der Standardwert ist 1 Million.  <br/> |
|**AppliedBandwidthLimitAcceptable** <br/> |int  <br/> ||Zulässige Bandbreitenbeschränkung für die Anwendungsfreigabe. Der Standardwert ist 500000.  <br/> |
|**SpoiledTilePercentTotalOptimal** <br/> |Dezimal (5; 2)  <br/> ||Optimaler Prozentsatz für "verwöhnte" Kacheln für die Klassifizierung einer Anwendungsfreigabe Qualität. Dieser Wert ist der Prozentsatz des Inhalts des mitbenutzenden, der den Betrachter nicht erreicht hat. Inhalte werden möglicherweise verworfen (oder verdorben), wenn der mitbenutzende die Kacheln aus der grafikquelle abwirft oder die ASMCU-Kacheln Kacheln von Sharer abwirft. Der Standardwert ist 11 Prozent.  <br/> |
|**SpoiledTilePercentTotalAcceptable** <br/> |Dezimal (5; 2)  <br/> ||Akzeptabler Prozentsatz für "verdorbene" Kacheln für die Klassifizierung einer Anwendungsfreigabe Qualität. Dieser Wert ist der Prozentsatz des Inhalts des mitbenutzenden, der den Betrachter nicht erreicht hat. Inhalte werden möglicherweise verworfen (oder verdorben), wenn der mitbenutzende die Kacheln aus der grafikquelle abwirft oder die ASMCU-Kacheln Kacheln von Sharer abwirft. Der Standardwert ist 36 Prozent.  <br/> |
|**JitterInterArrivalOptimal** <br/> |int  <br/> ||Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.  <br/> |
|**JitterInterArrivalAcceptable** <br/> |int  <br/> ||Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.  <br/> |
|**RelativeOneWayBurstDensityOptimal** <br/> |float  <br/> ||Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.  <br/> |
|**RelativeOneWayBurstDensityAcceptable** <br/> |float  <br/> ||Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.  <br/> |
|**RDPTileProcessingLatencyBurstDensityOptimal** <br/> |float  <br/> ||Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.  <br/> |
|**RDPTileProcessingLatencyBurstDensityAcceptable** <br/> |float  <br/> ||Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.  <br/> |
|**RelativeOneWayAverageOptimal** <br/> |float  <br/> ||Optimaler Wert für die relative unidirektionale Verzögerung zwischen den beiden Medien Endpunkten, die an der Anwendungsfreigabe beteiligt sind. Dies ist ein Single-Hop-Latenzmaß. Der Standardwert ist 1,0 Sekunden.  <br/> Die Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayAverageAcceptable** <br/> |float  <br/> ||Optimaler Wert für die relative unidirektionale Verzögerung zwischen den beiden Medien Endpunkten, die an der Anwendungsfreigabe beteiligt sind. Dies ist ein Single-Hop-Latenzmaß. Der Standardwert ist 1,75 Sekunden.  <br/> Die Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RDPTileProcessingLatencyAverageOptimal** <br/> |float  <br/> ||Optimaler Wert der durchschnittlichen Verarbeitungs Wartezeit für RDP-Kacheln auf dem AS-Konferenz Server über die Dauer der Anzeige Sitzung. Latenz ist der Zeitunterschied zwischen dem Codieren des Start Frames auf dem Server (Sharer oder MCU, je nach Szenario) und dem gleichen Start Frame im Viewer.  <br/> Ein hoher Durchschnitt zeigt eine längere Verzögerung bei der Anzeige an. Ein überlasteter Konferenzserver zeigt gegebenenfalls höhere durchschnittliche Verzögerungen an. Der Standardwert ist 200M.  <br/> Die Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**RDPTileProcessingLatencyAverageAcceptable** <br/> |float  <br/> ||Akzeptabler Wert der durchschnittlichen Verarbeitungs Wartezeit für RDP-Kacheln auf dem AS-Konferenz Server über die Dauer der Anzeige Sitzung. Latenz ist der Zeitunterschied zwischen dem Codieren des Start Frames auf dem Server (Sharer oder MCU, je nach Szenario) und dem gleichen Start Frame im Viewer.  <br/> Ein hoher Durchschnitt zeigt eine längere Verzögerung bei der Anzeige an. Ein überlasteter Konferenzserver zeigt gegebenenfalls höhere durchschnittliche Verzögerungen an. Der Standardwert ist 200M.  <br/> Die Spalte wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
   

