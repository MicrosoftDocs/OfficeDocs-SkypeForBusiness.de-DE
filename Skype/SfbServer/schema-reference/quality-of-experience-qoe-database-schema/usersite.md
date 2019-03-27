---
title: UserSite-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: Die UserSite-Tabelle ist eine Tabelle. Jeder Datensatz steht für eine Website des Benutzers in der Einstellung der Netzwerk-Konfiguration.
ms.openlocfilehash: a52f5cd9aa7059e2b545dec3bcc7ccb86191347a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885888"
---
# <a name="usersite-table"></a>UserSite-Tabelle
 
Die UserSite-Tabelle ist eine Tabelle. Jeder Datensatz steht für eine Website des Benutzers in der Einstellung der Netzwerk-Konfiguration.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die den Benutzerstandort identifiziert.  <br/> |
|**UserSiteName** <br/> |nvarchar(128)  <br/> |Eindeutige  <br/> |Name der Website des Benutzers.  <br/> |
|**RegionKey** <br/> |int  <br/> |Ausländisch  <br/> |Verwiesen von der [Region Table](region.md).  <br/> |
   

