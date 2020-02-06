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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
description: Die VideoMetricsThreshold-Tabelle enthält die optimalen und akzeptablen Werte für die Qualität der bei Videoanrufen verwendeten Metriken für die Erfahrung.
ms.openlocfilehash: 89d3095ef7222cacc7633116c43d66cbcc2be2e2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804735"
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

