---
title: Subnet-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Subnet-Tabelle ist eine Tabelle. Jeder Datensatz steht für ein Subnetz im Netzwerk Konfigurationseinstellung definiert.
ms.openlocfilehash: aa91202bfb46a96f86ea3a631be3b964a17a6058
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880476"
---
# <a name="subnet-table"></a>Subnet-Tabelle
 
Subnet-Tabelle ist eine Tabelle. Jeder Datensatz steht für ein Subnetz im Netzwerk Konfigurationseinstellung definiert.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |Primär, Fremd  <br/> |Ganzzahlige Darstellung der Subnetz-IP.  <br/> |
|**Subnetzmaske** <br/> |int  <br/> ||Subnetzmaske  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Ausländisch  <br/> |Verweis von der [UserSite-Tabelle](usersite.md).  <br/> |
|**SubnetDescription** <br/> |nvarchar(512)  <br/> ||Die Beschreibung des Subnetzes.  <br/> |
   

