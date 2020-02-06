---
title: UserSite-Tabelle
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
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: Die Tabelle UserSite ist eine unterstützende Tabelle. Jeder Datensatz steht für eine Benutzer Website, die in der Netzwerk Konfigurationseinstellung definiert ist.
ms.openlocfilehash: e1d6c4ddc3a756f2e5df0713d6abe1cb7b61295f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805003"
---
# <a name="usersite-table"></a>UserSite-Tabelle
 
Die Tabelle UserSite ist eine unterstützende Tabelle. Jeder Datensatz steht für eine Benutzer Website, die in der Netzwerk Konfigurationseinstellung definiert ist.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Nummer, die die Benutzer Website kennzeichnet.  <br/> |
|**UserSiteName** <br/> |nvarchar (128)  <br/> |Eindeutigen  <br/> |Name der Benutzer Website.  <br/> |
|**RegionKey** <br/> |int  <br/> |Fremd  <br/> |Referenziert aus der [Regions Tabelle](region.md).  <br/> |
   

