---
title: Servertabelle
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
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: Die Server Tabelle ist eine unterstützende Tabelle. Jeder Datensatz steht für einen Server.
ms.openlocfilehash: e57bb96fd715d67a5b6676a2399dc520f08bac96
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41806133"
---
# <a name="server-table"></a>Servertabelle
 
Die Server Tabelle ist eine unterstützende Tabelle. Jeder Datensatz steht für einen Server. 
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Nummer, die den Server identifiziert.  <br/> |
|**FQDNOrIP** <br/> |nvarchar(256)  <br/> |Index  <br/> |Mac-Adresszeichenfolge.  <br/> |
|**Servertyp** <br/> |int  <br/> |Fremd  <br/> |1: Vermittlungs Server  <br/> 2: a/v Conferencing Server16394: a/v Edge service32769: Gateway  <br/> |
|**Poolname** <br/> |nvarchar (512)  <br/> ||Pool, zu dem der Server gehört. Gilt nur für den A/V-Konferenz Server.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Nur für interne Verwendung.  <br/> |
   

