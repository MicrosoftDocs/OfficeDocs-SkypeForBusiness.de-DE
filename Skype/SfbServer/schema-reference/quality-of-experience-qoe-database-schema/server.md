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
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: Die Server Tabelle ist eine unterstützende Tabelle. Jeder Datensatz steht für einen Server.
ms.openlocfilehash: 93ba62c262b95b46b76cd445be04a0bc53c5a960
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294712"
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
   

