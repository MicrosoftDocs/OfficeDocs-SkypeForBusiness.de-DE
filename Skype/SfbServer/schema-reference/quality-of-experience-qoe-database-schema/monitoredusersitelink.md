---
title: Tabelle "MonitoredUserSiteLink"
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
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: Bei der MonitoredUserSiteLink-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für eine Verknüpfung zwischen zwei Benutzerstandorten.
ms.openlocfilehash: 88b4d385f3c96dc93a519274c584e1f99584982f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806355"
---
# <a name="monitoredusersitelink-table"></a>Tabelle "MonitoredUserSiteLink"
 
Bei der MonitoredUserSiteLink-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für eine Verknüpfung zwischen zwei Benutzerstandorten.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |Primär, Fremd  <br/> |Referenziert aus der [UserSite-Tabelle.](usersite.md)  <br/> |
|**UserSite2Key** <br/> |int  <br/> |Primär, Fremd  <br/> |Verweis aus der [UserSite -Tabelle](usersite.md).  <br/> |
   

