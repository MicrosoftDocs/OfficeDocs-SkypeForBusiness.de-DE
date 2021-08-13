---
title: Servertabelle
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
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: Bei der Server-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für einen Server.
ms.openlocfilehash: e43e245e62b1b40f318d1920ae93d82ae9e8bad0e28436f31d9cc2f0fe54bac1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341620"
---
# <a name="server-table"></a>Servertabelle
 
Bei der Server-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für einen Server. 
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |Ganzzahl  <br/> |Primary  <br/> |Eindeutige Zahl, die den Server identifiziert.  <br/> |
|**FQDNOrIP** <br/> |nvarchar(256)  <br/> |Index  <br/> |MAC-Adresszeichenfolge.  <br/> |
|**Servertype** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |1: Vermittlungsserver  <br/> 2: A/V-Konferenzserver16394: A/V-Edgedienst32769: Gateway  <br/> |
|**PoolName** <br/> |nvarchar(512)  <br/> ||Pool, zu dem der Server gehört. Gilt nur für den A/V-Konferenzserver.  <br/> |
|**NextUpdateTS** <br/> |Datum/Uhrzeit  <br/> ||Ausschließlich für interne Zwecke.  <br/> |
   

