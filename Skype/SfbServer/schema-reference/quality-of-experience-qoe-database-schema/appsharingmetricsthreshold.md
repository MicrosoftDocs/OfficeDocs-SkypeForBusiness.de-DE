---
title: Tabelle "appsharingmetricsthreshold"
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
description: Die Tabelle "appsharingmetricsthreshold" enthält optimale und zulässige Werte für Quality of Experience-Metriken, die mit der Anwendungsfreigabe verwendet. Diese Schwellenwerte werden verwendet, um festzustellen, ob die Anwendungsfreigabe Erfahrung als schlecht klassifiziert werden sollen.
ms.openlocfilehash: bddad99803ab6683985b0f44ed5df509b84344f3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212327"
---
# <a name="appsharingmetricsthreshold-table"></a>Tabelle "appsharingmetricsthreshold"
 
Die Tabelle "appsharingmetricsthreshold" enthält optimale und zulässige Werte für Quality of Experience-Metriken, die mit der Anwendungsfreigabe verwendet. Diese Schwellenwerte werden verwendet, um festzustellen, ob die Anwendungsfreigabe Erfahrung als schlecht klassifiziert werden sollen.
  
Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**CallType** <br/> |int  <br/> |Primary  <br/> |Typ des getätigten Anrufs.  <br/> |
|**AppliedBandwidthLimitOptimal** <br/> |int  <br/> ||Optimale Bandbreite Beschränkung für die Anwendungsfreigabe. Der Standardwert ist 1000000.  <br/> |
|**AppliedBandwidthLimitAcceptable** <br/> |int  <br/> ||Zulässige Bandbreite Beschränkung für die Anwendungsfreigabe. Der Standardwert ist 500000.  <br/> |
|**SpoiledTilePercentTotalOptimal** <br/> |decimal(5,2)  <br/> ||Optimale Prozentsatz für "schlechte" Kacheln zum Klassifizieren von eine Anwendungsfreigabe Qualität. Dieser Wert ist der Prozentsatz des Inhalts von des mitbenutzenden Projekts, die den Viewer nicht erreicht hat. Inhalt möglicherweise verworfen (oder hat) beim des mitbenutzenden Projekts verwirft Kacheln aus der grafikquelle oder die ASMCU werden verworfen nebeneinander angeordnet werden nebeneinander angeordnet von mitbenutzenden fest. Der Standardwert beträgt 11 %.  <br/> |
|**SpoiledTilePercentTotalAcceptable** <br/> |decimal(5,2)  <br/> ||Akzeptabler Prozentsatz für "schlechte" Kacheln zum Klassifizieren von eine Anwendungsfreigabe Qualität. Dieser Wert ist der Prozentsatz des Inhalts von des mitbenutzenden Projekts, die den Viewer nicht erreicht hat. Inhalt möglicherweise verworfen (oder hat) beim des mitbenutzenden Projekts verwirft Kacheln aus der grafikquelle oder die ASMCU werden verworfen nebeneinander angeordnet werden nebeneinander angeordnet von mitbenutzenden fest. Der Standardwert ist 36 Prozent.  <br/> |
|**JitterInterArrivalOptimal** <br/> |int  <br/> ||Diese Spalte wird nicht in Microsoft Lync Server 2013 verwendet.  <br/> |
|**JitterInterArrivalAcceptable** <br/> |int  <br/> ||Diese Spalte wird nicht in Microsoft Lync Server 2013 verwendet.  <br/> |
|**RelativeOneWayBurstDensityOptimal** <br/> |float  <br/> ||Diese Spalte wird nicht in Microsoft Lync Server 2013 verwendet.  <br/> |
|**RelativeOneWayBurstDensityAcceptable** <br/> |float  <br/> ||Diese Spalte wird nicht in Microsoft Lync Server 2013 verwendet.  <br/> |
|**RDPTileProcessingLatencyBurstDensityOptimal** <br/> |float  <br/> ||Diese Spalte wird nicht in Microsoft Lync Server 2013 verwendet.  <br/> |
|**RDPTileProcessingLatencyBurstDensityAcceptable** <br/> |float  <br/> ||Diese Spalte wird nicht in Microsoft Lync Server 2013 verwendet.  <br/> |
|**RelativeOneWayAverageOptimal** <br/> |float  <br/> ||Optimale Wert für die relative unidirektionale Verzögerung zwischen den beiden Medien Endpunkten der Anwendungsfreigabe beteiligt. Dies ist ein Single-Hop-Latenzmaß. Der Standardwert ist 1,0 Sekunden.  <br/> Die Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RelativeOneWayAverageAcceptable** <br/> |float  <br/> ||Optimale Wert für die relative unidirektionale Verzögerung zwischen den beiden Medien Endpunkten der Anwendungsfreigabe beteiligt. Dies ist ein Single-Hop-Latenzmaß. Der Standardwert ist 1.75 Sekunden.  <br/> Die Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RDPTileProcessingLatencyAverageOptimal** <br/> |float  <br/> ||Optimale Wert, der die durchschnittliche Wartezeit in der AS-Konferenzserver für die Dauer der Sitzung anzeigen Verarbeitung RDP-Kachel. Wartezeit ist der Zeitunterschied zwischen beim Starten Frame auf dem Server (mitbenutzenden oder MCU je nach Szenario) codiert wird und den gleichen starten Frame wird auf den Viewer decodiert.  <br/> Ein hoher Durchschnitt zeigt eine längere Verzögerung bei der Anzeige an. Ein überlasteter Konferenzserver zeigt gegebenenfalls höhere durchschnittliche Verzögerungen an. Der Standardwert ist 200 ms.  <br/> Die Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**RDPTileProcessingLatencyAverageAcceptable** <br/> |float  <br/> ||Akzeptabler Wert für die durchschnittliche Wartezeit in der AS-Konferenzserver für die Dauer der Sitzung anzeigen Verarbeitung RDP-Kachel. Wartezeit ist der Zeitunterschied zwischen beim Starten Frame auf dem Server (mitbenutzenden oder MCU je nach Szenario) codiert wird und den gleichen starten Frame wird auf den Viewer decodiert.  <br/> Ein hoher Durchschnitt zeigt eine längere Verzögerung bei der Anzeige an. Ein überlasteter Konferenzserver zeigt gegebenenfalls höhere durchschnittliche Verzögerungen an. Der Standardwert ist 200 ms.  <br/> Die Spalte wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
   

