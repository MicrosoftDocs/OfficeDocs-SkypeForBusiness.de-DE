---
title: SessionCorrelation-Tabelle
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: 'Die SessionCorrelation-Tabelle ist eine Unterstützende Tabelle. Jeder Datensatz stellt eine CorrelationID dar, die verwendet wird, um mehrere Sitzungen zu korrelieren.'
---

# <a name="sessioncorrelation-table"></a>SessionCorrelation-Tabelle
 
Die SessionCorrelation-Tabelle ist eine Unterstützende Tabelle. Jeder Datensatz stellt eine CorrelationID dar, die verwendet wird, um mehrere Sitzungen zu korrelieren. 
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Prüfsumme** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Nummer, die diesen A/V-Konferenzserver identifiziert.  <br/> |
|**Correlationid** <br/> |nvarchar(256)  <br/> |Eigen  <br/> |Sitzungen, die korreliert sind, haben dieselbe Korrelations-ID.  <br/> |
|**NextUpdateTS** <br/> |Datum/Uhrzeit  <br/> | <br/> |Ausschließlich für interne Zwecke.  <br/> |
   

