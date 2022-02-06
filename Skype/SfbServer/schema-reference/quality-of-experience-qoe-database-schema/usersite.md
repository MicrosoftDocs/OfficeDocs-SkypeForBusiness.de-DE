---
title: UserSite-Tabelle
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
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: 'Bei der UserSite-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für einen Benutzerstandort in der Netzwerkkonfigurationseinstellung.'
---

# <a name="usersite-table"></a>UserSite-Tabelle
 
Bei der UserSite-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für einen Benutzerstandort in der Netzwerkkonfigurationseinstellung.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die den Benutzerstandort identifiziert.  <br/> |
|**UserSiteName** <br/> |nvarchar(128)  <br/> |Eigen  <br/> |Name der Benutzerwebsite.  <br/> |
|**RegionKey** <br/> |int  <br/> |Ausländisch  <br/> |Referenziert aus [der Region-Tabelle](region.md).  <br/> |
   

