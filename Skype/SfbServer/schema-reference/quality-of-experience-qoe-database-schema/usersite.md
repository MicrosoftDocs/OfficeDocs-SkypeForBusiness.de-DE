---
title: UserSite-Tabelle
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
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: Bei der UserSite-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für einen Benutzerstandort in der Netzwerkkonfigurationseinstellung.
ms.openlocfilehash: 01ab76218040d37176355d62768c6a8b8f4b7336d22ce7263c61ac9fc8c289ed
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54314331"
---
# <a name="usersite-table"></a>UserSite-Tabelle
 
Bei der UserSite-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für einen Benutzerstandort in der Netzwerkkonfigurationseinstellung.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |Ganzzahl  <br/> |Primary  <br/> |Eindeutige Zahl, die den Benutzerstandort identifiziert.  <br/> |
|**UserSiteName** <br/> |nvarchar(128)  <br/> |Eigen  <br/> |Name der Benutzerwebsite.  <br/> |
|**RegionKey** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |Referenziert aus [Region-Tabelle](region.md).  <br/> |
   

