---
title: MonitoredUserSiteLink-Tabelle
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
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: Bei der MonitoredUserSiteLink-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für eine Verknüpfung zwischen zwei Benutzerstandorten.
ms.openlocfilehash: a5a8802f3821fff3d08c2365d4f76655b5824606
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58610572"
---
# <a name="monitoredusersitelink-table"></a>MonitoredUserSiteLink-Tabelle
 
Bei der MonitoredUserSiteLink-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für eine Verknüpfung zwischen zwei Benutzerstandorten.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |Primär, Fremd  <br/> |Referenziert aus der [UserSite-Tabelle.](usersite.md)  <br/> |
|**UserSite2Key** <br/> |int  <br/> |Primär, Fremd  <br/> |Verweis aus der [UserSite-Tabelle](usersite.md).  <br/> |
   

