---
title: SessionCorrelation-Tabelle
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
ms.openlocfilehash: 8a9c9661b10548bf3ebf402aa4654fced2ca709b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="sessioncorrelation-table"></a>SessionCorrelation-Tabelle
 
Die SessionCorrelation-Tabelle ist eine Tabelle. Jeder Datensatz steht für eine CorrelationID die korrelieren mehrerer Sitzungen verwendet wird. 
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Prüfsumme** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, identifiziert dieser A / V-Konferenzserver.  <br/> |
|**CorrelationID** <br/> |nvarchar(256)  <br/> |Eindeutige  <br/> |Korrelierte Sitzungen müssen dieselbe Korrelations-ID  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |Nur zur internen Verwendung.  <br/> |
   

