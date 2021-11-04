---
title: Servertabelle
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: Bei der Server-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für einen Server.
ms.openlocfilehash: e2a1007afa545a5b70b60f0e22f69826daebcda0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776035"
---
# <a name="server-table"></a>Servertabelle
 
Bei der Server-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für einen Server. 
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die den Server identifiziert.  <br/> |
|**FQDNOrIP** <br/> |nvarchar(256)  <br/> |Index  <br/> |MAC-Adresszeichenfolge.  <br/> |
|**Servertype** <br/> |int  <br/> |Ausländisch  <br/> |1: Vermittlungsserver  <br/> 2: A/V-Konferenzserver16394: A/V-Edgedienst32769: Gateway  <br/> |
|**PoolName** <br/> |nvarchar(512)  <br/> ||Pool, zu dem der Server gehört. Gilt nur für den A/V-Konferenzserver.  <br/> |
|**NextUpdateTS** <br/> |Datum/Uhrzeit  <br/> ||Ausschließlich für interne Zwecke.  <br/> |
   

