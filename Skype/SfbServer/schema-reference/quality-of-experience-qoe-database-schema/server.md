---
title: Servertabelle
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: Die Server-Tabelle ist eine Tabelle. Jeder Datensatz steht für einen Server.
ms.openlocfilehash: be48b90cc727ebfd0320b38ac0d89a302dab6b07
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="server-table"></a>Servertabelle
 
Die Server-Tabelle ist eine Tabelle. Jeder Datensatz steht für einen Server. 
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die den Server identifiziert.  <br/> |
|**FQDNOrIP** <br/> |nvarchar(256)  <br/> |Index  <br/> |MAC-Adresszeichenfolge.  <br/> |
|**Servertyp** <br/> |int  <br/> |Fremdschlüssel  <br/> |1: Vermittlungsserver  <br/> 2: A / V-konferenzserver16394: A / V-Edgedienst32769: Gateway  <br/> |
|**"Poolname"** <br/> |nvarchar(512)  <br/> ||Pool der Server gehört. Gilt nur für den A / V-Konferenzserver.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Nur zur internen Verwendung.  <br/> |
   

