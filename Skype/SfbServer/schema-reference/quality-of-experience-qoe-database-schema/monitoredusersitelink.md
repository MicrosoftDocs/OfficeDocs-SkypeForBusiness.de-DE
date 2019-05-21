---
title: MonitoredUserSiteLink-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: Die Tabelle MonitoredUserSiteLink ist eine unterstützende Tabelle. Jeder Datensatz steht für einen Link zwischen zwei Benutzer Websites.
ms.openlocfilehash: 789c1a721e1a8c204ff6e214f419de77d1b7f7bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294852"
---
# <a name="monitoredusersitelink-table"></a>MonitoredUserSiteLink-Tabelle
 
Die Tabelle MonitoredUserSiteLink ist eine unterstützende Tabelle. Jeder Datensatz steht für einen Link zwischen zwei Benutzer Websites.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |Primär, fremd  <br/> |Wird in der [UserSite-Tabelle](usersite.md)referenziert.  <br/> |
|**UserSite2Key** <br/> |int  <br/> |Primär, fremd  <br/> |Verweis aus der [Tabelle "UserSite](usersite.md)"  <br/> |
   

