---
title: VideoMetricsThreshold-Tabelle
ms.reviewer: ''
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
ms.openlocfilehash: 560012374ab6a9ef5ea741d2046afb095336d3c3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893789"
---
# <a name="videometricsthreshold-table"></a>VideoMetricsThreshold-Tabelle
 
Die Tabelle VideoMetricsThreshold enthält optimale und zulässige Werte für Quality of Experience-Metriken, die bei Videoanrufen verwendet.
  

| **Spalte**                                               | **Datentyp**       | **Schlüssel/Index**  | **Details**                          |
|:---------------------------------------------------------|:--------------------|:---------------|:-------------------------------------|
| **CallType** <br/>                                       | int  <br/>          | Primary  <br/> | Typ des getätigten Anrufs.  <br/> |
| **VideoPostFECPLROptimal** <br/>                         | decimal(5,2)  <br/> |                | Der Standardwert lautet 0,05.  <br/>    |
| **VideoPostFECPLRAcceptable** <br/>                      | decimal(5,2)  <br/> |                | Der Standardwert lautet 0,10.  <br/>    |
| **VideoLocalFrameLostPercentageAverageOptimal** <br/>    | decimal(5,2)  <br/> |                | Der Standardwert lautet 5,0.  <br/>     |
| **VideoLocalFrameLostPercentageAverageAcceptable** <br/> | decimal(5,2)  <br/> |                | Der Standardwert lautet 10,0.  <br/>    |
| **RecvFrameRateAverageOptimal** <br/>                    | decimal(9,4)  <br/> |                | Der Standardwert lautet 12,0000.  <br/> |
| **RecvFramerateAverageAcceptable** <br/>                 | decimal(9,4)  <br/> |                | Der Standardwert lautet 7,0000.  <br/>  |
| **LowFrameRateCallPercentOptimal** <br/>                 | decimal(5,2)  <br/> |                | Der Standardwert lautet 5,0.  <br/>     |
| \****LowFrameRateCallPercentAcceptable***\* <br/>        | decimal(5,2)  <br/> |                | Der Standardwert lautet 10,0 /  <br/>    |
| **LowResolutionCallPercentOptimal** <br/>                | decimal(5,2)  <br/> |                | Der Standardwert lautet 5,0.  <br/>     |
| **LowResolutionCallPercentAcceptable** <br/>             | decimal(5,2)  <br/> |                | Der Standardwert lautet 10,0.  <br/>    |
| **VideoPacketLossRateOptimal** <br/>                     | foat  <br/>         |                | Der Standardwert lautet 0,05.  <br/>    |
| **VideoPacketLossRateAcceptable** <br/>                  | float  <br/>        |                | Der Standardwert lautet 0,10.  <br/>    |
| **VideoFrameRateAvgOptimal** <br/>                       | float  <br/>        |                | Der Standardwert lautet 12.  <br/>      |
| **VideoFrameRateAvgAcceptable** <br/>                    | float  <br/>        |                | Der Standardwert ist 7.  <br/>       |
| **DynamicCapabilityPercentOptimal** <br/>                | decimal(5,2)  <br/> |                | Der Standardwert lautet 5,00.  <br/>    |
| **DynamicCapabilityPercentAcceptable** <br/>             | decimal(5,2)  <br/> |                | Der Standardwert lautet 10,00.  <br/>   |

