---
title: MonitoredUserSiteLink-Tabelle
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
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: 'Bei der MonitoredUserSiteLink-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für eine Verknüpfung zwischen zwei Benutzerstandorten.'
---

# <a name="monitoredusersitelink-table"></a>MonitoredUserSiteLink-Tabelle
 
Bei der MonitoredUserSiteLink-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für eine Verknüpfung zwischen zwei Benutzerstandorten.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |Primär, Fremd  <br/> |Referenziert aus der [UserSite-Tabelle](usersite.md).  <br/> |
|**UserSite2Key** <br/> |int  <br/> |Primär, Fremd  <br/> |Verweis aus der [UserSite-Tabelle](usersite.md).  <br/> |
   

