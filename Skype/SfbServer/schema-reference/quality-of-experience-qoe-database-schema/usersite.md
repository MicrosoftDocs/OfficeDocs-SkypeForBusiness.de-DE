---
title: UserSite-Tabelle
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
ms.openlocfilehash: effc2404a91bf122dc9be9ad371372e8355b230f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="usersite-table"></a>UserSite-Tabelle
 
Die UserSite-Tabelle ist eine Tabelle. Jeder Datensatz steht für eine Website des Benutzers in der Einstellung der Netzwerk-Konfiguration.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die den Benutzerstandort identifiziert.  <br/> |
|**UserSiteName** <br/> |nvarchar(128)  <br/> |Eindeutige  <br/> |Name der Website des Benutzers.  <br/> |
|**RegionKey** <br/> |int  <br/> |Fremdschlüssel  <br/> |Verwiesen von der [Region Table](region.md).  <br/> |
   

