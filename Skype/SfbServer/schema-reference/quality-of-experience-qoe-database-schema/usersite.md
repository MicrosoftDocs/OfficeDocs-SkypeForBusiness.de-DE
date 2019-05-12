---
title: UserSite-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: Die UserSite-Tabelle ist eine Tabelle. Jeder Datensatz steht für eine Website des Benutzers in der Einstellung der Netzwerk-Konfiguration.
ms.openlocfilehash: 519cedc35c03fd9bcb5479ea3cecf75ec617917c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906953"
---
# <a name="usersite-table"></a>UserSite-Tabelle
 
Die UserSite-Tabelle ist eine Tabelle. Jeder Datensatz steht für eine Website des Benutzers in der Einstellung der Netzwerk-Konfiguration.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die den Benutzerstandort identifiziert.  <br/> |
|**UserSiteName** <br/> |nvarchar(128)  <br/> |Eindeutige  <br/> |Name der Website des Benutzers.  <br/> |
|**RegionKey** <br/> |int  <br/> |Ausländisch  <br/> |Verwiesen von der [Region Table](region.md).  <br/> |
   

