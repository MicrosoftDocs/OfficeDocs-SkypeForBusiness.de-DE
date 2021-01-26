---
title: Tabelle "SessionCorrelation"
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
description: Die Tabelle "SessionCorrelation" ist eine Tabelle mit Unterstützung. Jeder Datensatz stellt eine CorrelationID dar, die verwendet wird, um mehrere Sitzungen zu korrelieren.
ms.openlocfilehash: 36b617517f3642a2150c72369db858eee62a4a87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802655"
---
# <a name="sessioncorrelation-table"></a>Tabelle "SessionCorrelation"
 
Die Tabelle "SessionCorrelation" ist eine Tabelle mit Unterstützung. Jeder Datensatz stellt eine CorrelationID dar, die verwendet wird, um mehrere Sitzungen zu korrelieren. 
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Prüfsumme** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Nummer, die diesen A/V-Konferenzserver identifiziert.  <br/> |
|**CorrelationID** <br/> |nvarchar(256)  <br/> |Eigen  <br/> |Sitzungen, die korreliert sind, haben dieselbe Korrelations-ID.  <br/> |
|**NextUpdateTS** <br/> |Datum/Uhrzeit  <br/> | <br/> |Ausschließlich für interne Zwecke.  <br/> |
   

