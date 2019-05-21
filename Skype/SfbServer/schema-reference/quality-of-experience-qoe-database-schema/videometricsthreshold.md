---
title: VideoMetricsThreshold-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
description: Die VideoMetricsThreshold-Tabelle enthält die optimalen und akzeptablen Werte für die Qualität der bei Videoanrufen verwendeten Metriken für die Erfahrung.
ms.openlocfilehash: a923334596ea6b3e6b56c43682be0f0f6a640f15
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294537"
---
# <a name="videometricsthreshold-table"></a>VideoMetricsThreshold-Tabelle
 
Die VideoMetricsThreshold-Tabelle enthält die optimalen und akzeptablen Werte für die Qualität der bei Videoanrufen verwendeten Metriken für die Erfahrung.
  

| **Spalte**                                               | **Datentyp**       | **Schlüssel/Index**  | **Details**                          |
|:---------------------------------------------------------|:--------------------|:---------------|:-------------------------------------|
| **CallType** <br/>                                       | int  <br/>          | Primary  <br/> | Der Typ des Anrufs, der getätigt wurde.  <br/> |
| **VideoPostFECPLROptimal** <br/>                         | Dezimal (5; 2)  <br/> |                | Der Standardwert ist 0,05.  <br/>    |
| **VideoPostFECPLRAcceptable** <br/>                      | Dezimal (5; 2)  <br/> |                | Der Standardwert ist 0,10.  <br/>    |
| **VideoLocalFrameLostPercentageAverageOptimal** <br/>    | Dezimal (5; 2)  <br/> |                | Der Standardwert ist 5,0.  <br/>     |
| **VideoLocalFrameLostPercentageAverageAcceptable** <br/> | Dezimal (5; 2)  <br/> |                | Der Standardwert ist 10,0.  <br/>    |
| **RecvFrameRateAverageOptimal** <br/>                    | Dezimal (9; 4)  <br/> |                | Der Standardwert ist 12,0000.  <br/> |
| **RecvFramerateAverageAcceptable** <br/>                 | Dezimal (9; 4)  <br/> |                | Der Standardwert ist 7,0000.  <br/>  |
| **LowFrameRateCallPercentOptimal** <br/>                 | Dezimal (5; 2)  <br/> |                | Der Standardwert ist 5,0.  <br/>     |
| \****LowFrameRateCallPercentAcceptable***\* <br/>        | Dezimal (5; 2)  <br/> |                | Der Standardwert ist 10.0/  <br/>    |
| **LowResolutionCallPercentOptimal** <br/>                | Dezimal (5; 2)  <br/> |                | Der Standardwert ist 5,0.  <br/>     |
| **LowResolutionCallPercentAcceptable** <br/>             | Dezimal (5; 2)  <br/> |                | Der Standardwert ist 10,0.  <br/>    |
| **VideoPacketLossRateOptimal** <br/>                     | foat  <br/>         |                | Der Standardwert ist 0,05.  <br/>    |
| **VideoPacketLossRateAcceptable** <br/>                  | float  <br/>        |                | Der Standardwert ist 0,10.  <br/>    |
| **VideoFrameRateAvgOptimal** <br/>                       | float  <br/>        |                | Der Standardwert ist 12.  <br/>      |
| **VideoFrameRateAvgAcceptable** <br/>                    | float  <br/>        |                | Der Standardwert ist 7.  <br/>       |
| **DynamicCapabilityPercentOptimal** <br/>                | Dezimal (5; 2)  <br/> |                | Der Standardwert ist 5,00.  <br/>    |
| **DynamicCapabilityPercentAcceptable** <br/>             | Dezimal (5; 2)  <br/> |                | Der Standardwert ist 10,00.  <br/>   |

