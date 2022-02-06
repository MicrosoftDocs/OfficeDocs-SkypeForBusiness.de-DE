---
title: Servertabelle
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
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: 'Bei der Server-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für einen Server.'
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
   

