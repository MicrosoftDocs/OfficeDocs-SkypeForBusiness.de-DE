---
title: Tabelle "VideoMetricsThreshold"
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
ms.assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
description: Die Tabelle VideoMetricsThreshold enthält optimale und zulässige Werte für Quality of Experience-Metriken, die bei Videoanrufen verwendet werden.
ms.openlocfilehash: 15bf482412973fe4b3a0178be6ecdcc593c762e7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821375"
---
# <a name="videometricsthreshold-table"></a>Tabelle "VideoMetricsThreshold"
 
Die Tabelle VideoMetricsThreshold enthält optimale und zulässige Werte für Quality of Experience-Metriken, die bei Videoanrufen verwendet werden.
  

| **Spalte**                                               | **Datentyp**       | **Schlüssel/Index**  | **Details**                          |
|:---------------------------------------------------------|:--------------------|:---------------|:-------------------------------------|
| **CallType** <br/>                                       | int  <br/>          | Primary  <br/> | Der Typ des getätigten Anrufs.  <br/> |
| **VideoPostFECPLROptimal** <br/>                         | decimal(5,2)  <br/> |                | Der Standardwert lautet 0,05.  <br/>    |
| **VideoPostFECPLRAcceptable** <br/>                      | decimal(5,2)  <br/> |                | Der Standardwert lautet 0,10.  <br/>    |
| **VideoLocalFrameLostPercentageAverageOptimal** <br/>    | decimal(5,2)  <br/> |                | Der Standardwert lautet 5,0.  <br/>     |
| **VideoLocalFrameLostPercentageAverageAcceptable** <br/> | decimal(5,2)  <br/> |                | Der Standardwert lautet 10,0.  <br/>    |
| **RecvFrameRateAverageOptimal** <br/>                    | decimal(9,4)  <br/> |                | Der Standardwert lautet 12,0000.  <br/> |
| **RecvFramerateAverageAcceptable** <br/>                 | decimal(9,4)  <br/> |                | Der Standardwert lautet 7,0000.  <br/>  |
| **LowFrameRateCallPercentOptimal** <br/>                 | decimal(5,2)  <br/> |                | Der Standardwert lautet 5,0.  <br/>     |
| \****LowFrameRateCallPercentAcceptable** _\_ <br/>        | decimal(5,2)  <br/> |                | Der Standardwert lautet 10,0.  <br/>    |
| **LowResolutionCallPercentOptimal** <br/>                | decimal(5,2)  <br/> |                | Der Standardwert lautet 5,0.  <br/>     |
| **LowResolutionCallPercentAcceptable** <br/>             | decimal(5,2)  <br/> |                | Der Standardwert lautet 10,0.  <br/>    |
| **VideoPacketLossRateOptimal** <br/>                     | foat  <br/>         |                | Der Standardwert lautet 0,05.  <br/>    |
| **VideoPacketLossRateAcceptable** <br/>                  | Gleitkommazahl  <br/>        |                | Der Standardwert lautet 0,10.  <br/>    |
| **VideoFrameRateAvgOptimal** <br/>                       | Gleitkommazahl  <br/>        |                | Der Standardwert lautet 12.  <br/>      |
| **VideoFrameRateAvgAcceptable** <br/>                    | Gleitkommazahl  <br/>        |                | Der Standardwert lautet 7.  <br/>       |
| **DynamicCapabilityPercentOptimal** <br/>                | decimal(5,2)  <br/> |                | Der Standardwert lautet 5,00.  <br/>    |
| **DynamicCapabilityPercentAcceptable** <br/>             | decimal(5,2)  <br/> |                | Der Standardwert lautet 10,00.  <br/>   |

