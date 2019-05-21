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
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: Die Tabelle SessionCorrelation ist eine unterstützende Tabelle. Jeder Datensatz steht für einen CorrelationId, der für die Korrelation mehrerer Sitzungen verwendet wird.
ms.openlocfilehash: 3c307b9542b9c1f37967a40ae63979d72e0504ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294656"
---
# <a name="sessioncorrelation-table"></a>SessionCorrelation-Tabelle
 
Die Tabelle SessionCorrelation ist eine unterstützende Tabelle. Jeder Datensatz steht für einen CorrelationId, der für die Korrelation mehrerer Sitzungen verwendet wird. 
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Prüfsumme** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Nummer, die diesen A/V-Konferenz Server kennzeichnet.  <br/> |
|**CorrelationId** <br/> |nvarchar(256)  <br/> |Eindeutigen  <br/> |Für Sitzungen, die korreliert sind, gibt es dieselbe Korrelations-ID.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |Nur für interne Verwendung.  <br/> |
   

