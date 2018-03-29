---
title: VideoMetricsThreshold-Tabelle
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
description: Die Tabelle VideoMetricsThreshold enthält optimale und zulässige Werte für Quality of Experience-Metriken, die bei Videoanrufen verwendet.
ms.openlocfilehash: 7f9901151503889c57a74c6b49e5c9a84e276333
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="videometricsthreshold-table"></a>VideoMetricsThreshold-Tabelle
 
Die Tabelle VideoMetricsThreshold enthält optimale und zulässige Werte für Quality of Experience-Metriken, die bei Videoanrufen verwendet.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**CallType** <br/> |int  <br/> |Primary  <br/> |Typ des getätigten Anrufs.  <br/> |
|**VideoPostFECPLROptimal** <br/> |decimal(5,2)  <br/> ||Der Standardwert lautet 0,05.  <br/> |
|**VideoPostFECPLRAcceptable** <br/> |decimal(5,2)  <br/> ||Der Standardwert lautet 0,10.  <br/> |
|**VideoLocalFrameLostPercentageAverageOptimal** <br/> |decimal(5,2)  <br/> ||Der Standardwert lautet 5,0.  <br/> |
|**VideoLocalFrameLostPercentageAverageAcceptable** <br/> |decimal(5,2)  <br/> ||Der Standardwert lautet 10,0.  <br/> |
|**RecvFrameRateAverageOptimal** <br/> |decimal(9,4)  <br/> ||Der Standardwert lautet 12,0000.  <br/> |
|**RecvFramerateAverageAcceptable** <br/> |decimal(9,4)  <br/> ||Der Standardwert lautet 7,0000.  <br/> |
|**LowFrameRateCallPercentOptimal** <br/> |decimal(5,2)  <br/> ||Der Standardwert lautet 5,0.  <br/> |
|LowFrameRateCallPercentAcceptable *** <br/> |decimal(5,2)  <br/> ||Der Standardwert lautet 10,0 /  <br/> |
|**LowResolutionCallPercentOptimal** <br/> |decimal(5,2)  <br/> ||Der Standardwert lautet 5,0.  <br/> |
|**LowResolutionCallPercentAcceptable** <br/> |decimal(5,2)  <br/> ||Der Standardwert lautet 10,0.  <br/> |
|**VideoPacketLossRateOptimal** <br/> |foat  <br/> ||Der Standardwert lautet 0,05.  <br/> |
|**VideoPacketLossRateAcceptable** <br/> |float  <br/> ||Der Standardwert lautet 0,10.  <br/> |
|**VideoFrameRateAvgOptimal** <br/> |float  <br/> ||Der Standardwert lautet 12.  <br/> |
|**VideoFrameRateAvgAcceptable** <br/> |float  <br/> ||Der Standardwert ist 7.  <br/> |
|**DynamicCapabilityPercentOptimal** <br/> |decimal(5,2)  <br/> ||Der Standardwert lautet 5,00.  <br/> |
|**DynamicCapabilityPercentAcceptable** <br/> |decimal(5,2)  <br/> ||Der Standardwert lautet 10,00.  <br/> |
   

