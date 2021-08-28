---
title: UserSite-Tabelle
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
ms.localizationpriority: medium
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: Bei der UserSite-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für einen Benutzerstandort in der Netzwerkkonfigurationseinstellung.
ms.openlocfilehash: 5e7ae6f304d836fc2413cbbaf696200c3f514bd1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595265"
---
# <a name="usersite-table"></a>UserSite-Tabelle
 
Bei der UserSite-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für einen Benutzerstandort in der Netzwerkkonfigurationseinstellung.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die den Benutzerstandort identifiziert.  <br/> |
|**UserSiteName** <br/> |nvarchar(128)  <br/> |Eigen  <br/> |Name der Benutzerwebsite.  <br/> |
|**RegionKey** <br/> |int  <br/> |Ausländisch  <br/> |Referenziert aus [Region-Tabelle](region.md).  <br/> |
   

