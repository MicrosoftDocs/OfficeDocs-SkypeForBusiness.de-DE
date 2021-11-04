---
title: MonitoredUserSiteLink-Tabelle
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.openlocfilehash: 3cc8c11f049e98223c80756eb2dc83f1b9354ec7
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768363"
---
# <a name="monitoredusersitelink-table"></a>MonitoredUserSiteLink-Tabelle
 
Bei der MonitoredUserSiteLink-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für eine Verknüpfung zwischen zwei Benutzerstandorten.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |Primär, Fremd  <br/> |Referenziert aus der [UserSite-Tabelle.](usersite.md)  <br/> |
|**UserSite2Key** <br/> |int  <br/> |Primär, Fremd  <br/> |Verweis aus der [UserSite-Tabelle](usersite.md).  <br/> |
   

