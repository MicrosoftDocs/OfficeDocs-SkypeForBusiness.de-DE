---
title: tblConfig
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: TblConfig enthält einige Persistent Chat Server nicht unterstützte Konfiguration in einer Zeile.
ms.openlocfilehash: 9d28c0506b905975e2a72eeb83605fe4e32e7cfd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898937"
---
# <a name="tblconfig"></a>tblConfig
 
TblConfig enthält einige Persistent Chat Server nicht unterstützte Konfiguration in einer Zeile.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|Stellen configLabel  <br/> |Nvarchar (255), nicht null  <br/> |Enthält "Pool".  <br/> |
|configContent  <br/> |Nvarchar (Max.)  <br/> |Inhalt der Konfiguration.  <br/> |
|configPoolID  <br/> |GUID, nicht null  <br/> |Eindeutige ID der Datenbankinstanz.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|Stellen configLabel  <br/> |Primärschlüssel.  <br/> |
   

