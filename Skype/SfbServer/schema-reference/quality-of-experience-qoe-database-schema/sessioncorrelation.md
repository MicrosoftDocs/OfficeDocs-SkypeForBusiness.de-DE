---
title: SessionCorrelation-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: Die SessionCorrelation-Tabelle ist eine Tabelle. Jeder Datensatz steht für eine CorrelationID die korrelieren mehrerer Sitzungen verwendet wird.
ms.openlocfilehash: 4efd1aeba45fb12aee646c401f492450f375aa20
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907080"
---
# <a name="sessioncorrelation-table"></a>SessionCorrelation-Tabelle
 
Die SessionCorrelation-Tabelle ist eine Tabelle. Jeder Datensatz steht für eine CorrelationID die korrelieren mehrerer Sitzungen verwendet wird. 
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Prüfsumme** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, identifiziert dieser A / V-Konferenzserver.  <br/> |
|**CorrelationID** <br/> |nvarchar(256)  <br/> |Eindeutige  <br/> |Korrelierte Sitzungen müssen dieselbe Korrelations-ID  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |Nur zur internen Verwendung.  <br/> |
   

