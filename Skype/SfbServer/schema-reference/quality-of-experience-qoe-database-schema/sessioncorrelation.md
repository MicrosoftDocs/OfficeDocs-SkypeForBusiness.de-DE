---
title: SessionCorrelation-Tabelle
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
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: Die SessionCorrelation-Tabelle ist eine Unterstützende Tabelle. Jeder Datensatz stellt eine CorrelationID dar, die verwendet wird, um mehrere Sitzungen zu korrelieren.
ms.openlocfilehash: 2029d78a0a083bcf8817b3a819cd28e74824995d79575036ecafd85998bd5218
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54314421"
---
# <a name="sessioncorrelation-table"></a>SessionCorrelation-Tabelle
 
Die SessionCorrelation-Tabelle ist eine Unterstützende Tabelle. Jeder Datensatz stellt eine CorrelationID dar, die verwendet wird, um mehrere Sitzungen zu korrelieren. 
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Prüfsumme** <br/> |Ganzzahl  <br/> |||
|**CorrelationKey** <br/> |Ganzzahl  <br/> |Primary  <br/> |Eindeutige Nummer, die diesen A/V-Konferenzserver identifiziert.  <br/> |
|**Correlationid** <br/> |nvarchar(256)  <br/> |Eigen  <br/> |Sitzungen, die korreliert sind, haben dieselbe Korrelations-ID.  <br/> |
|**NextUpdateTS** <br/> |Datum/Uhrzeit  <br/> | <br/> |Ausschließlich für interne Zwecke.  <br/> |
   

