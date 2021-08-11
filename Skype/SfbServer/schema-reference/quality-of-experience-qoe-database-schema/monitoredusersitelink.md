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
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: Bei der MonitoredUserSiteLink-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für eine Verknüpfung zwischen zwei Benutzerstandorten.
ms.openlocfilehash: 7c7edea00fdd680ece091d06aa7528fb0dc7fe25d5b5b4fa126c37c48b3ee81d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321607"
---
# <a name="monitoredusersitelink-table"></a>MonitoredUserSiteLink-Tabelle
 
Bei der MonitoredUserSiteLink-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für eine Verknüpfung zwischen zwei Benutzerstandorten.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |Ganzzahl  <br/> |Primär, Fremd  <br/> |Referenziert aus der [UserSite-Tabelle.](usersite.md)  <br/> |
|**UserSite2Key** <br/> |Ganzzahl  <br/> |Primär, Fremd  <br/> |Verweis aus der [UserSite-Tabelle](usersite.md).  <br/> |
   

