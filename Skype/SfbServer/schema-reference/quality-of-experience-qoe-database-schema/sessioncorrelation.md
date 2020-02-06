---
title: SessionCorrelation-Tabelle
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
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: Die Tabelle SessionCorrelation ist eine unterstützende Tabelle. Jeder Datensatz steht für einen CorrelationId, der für die Korrelation mehrerer Sitzungen verwendet wird.
ms.openlocfilehash: cd9f477ad71b836fb204aab651aceb7bbb5832f8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805743"
---
# <a name="sessioncorrelation-table"></a>SessionCorrelation-Tabelle
 
Die Tabelle SessionCorrelation ist eine unterstützende Tabelle. Jeder Datensatz steht für einen CorrelationId, der für die Korrelation mehrerer Sitzungen verwendet wird. 
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Prüfsumme** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Nummer, die diesen A/V-Konferenz Server kennzeichnet.  <br/> |
|**CorrelationId** <br/> |nvarchar(256)  <br/> |Eindeutigen  <br/> |Für Sitzungen, die korreliert sind, gibt es dieselbe Korrelations-ID.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |Nur für interne Verwendung.  <br/> |
   

