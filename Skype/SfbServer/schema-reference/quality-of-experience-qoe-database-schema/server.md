---
title: Servertabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: Die Server-Tabelle ist eine Tabelle. Jeder Datensatz steht für einen Server.
ms.openlocfilehash: c0031e7181bb39895edadc40748f61626621f00e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920131"
---
# <a name="server-table"></a>Servertabelle
 
Die Server-Tabelle ist eine Tabelle. Jeder Datensatz steht für einen Server. 
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die den Server identifiziert.  <br/> |
|**FQDNOrIP** <br/> |nvarchar(256)  <br/> |Index  <br/> |MAC-Adresszeichenfolge.  <br/> |
|**Servertyp** <br/> |int  <br/> |Ausländisch  <br/> |1: Vermittlungsserver  <br/> 2: A / V-konferenzserver16394: A / V-Edgedienst32769: Gateway  <br/> |
|**"Poolname"** <br/> |nvarchar(512)  <br/> ||Pool der Server gehört. Gilt nur für den A / V-Konferenzserver.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Nur zur internen Verwendung.  <br/> |
   

