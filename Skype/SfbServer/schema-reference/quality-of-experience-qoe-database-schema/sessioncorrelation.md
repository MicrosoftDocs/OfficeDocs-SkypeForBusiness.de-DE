---
title: SessionCorrelation-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: Die SessionCorrelation-Tabelle ist eine Tabelle. Jeder Datensatz steht für eine CorrelationID die korrelieren mehrerer Sitzungen verwendet wird.
ms.openlocfilehash: 8c41ab5c52c6b4d06a3c3953e8d969488680e8d3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884663"
---
# <a name="sessioncorrelation-table"></a>SessionCorrelation-Tabelle
 
Die SessionCorrelation-Tabelle ist eine Tabelle. Jeder Datensatz steht für eine CorrelationID die korrelieren mehrerer Sitzungen verwendet wird. 
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Prüfsumme** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, identifiziert dieser A / V-Konferenzserver.  <br/> |
|**CorrelationID** <br/> |nvarchar(256)  <br/> |Eindeutige  <br/> |Korrelierte Sitzungen müssen dieselbe Korrelations-ID  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |Nur zur internen Verwendung.  <br/> |
   

