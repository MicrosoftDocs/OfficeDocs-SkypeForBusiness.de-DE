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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: Die Tabelle MonitoredUserSiteLink ist eine unterstützende Tabelle. Jeder Datensatz steht für einen Link zwischen zwei Benutzer Websites.
ms.openlocfilehash: 2cf229947da143fb01b3009020cfa432a4b558a0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807793"
---
# <a name="monitoredusersitelink-table"></a>MonitoredUserSiteLink-Tabelle
 
Die Tabelle MonitoredUserSiteLink ist eine unterstützende Tabelle. Jeder Datensatz steht für einen Link zwischen zwei Benutzer Websites.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |Primär, fremd  <br/> |Wird in der [UserSite-Tabelle](usersite.md)referenziert.  <br/> |
|**UserSite2Key** <br/> |int  <br/> |Primär, fremd  <br/> |Verweis aus der [Tabelle "UserSite](usersite.md)"  <br/> |
   

