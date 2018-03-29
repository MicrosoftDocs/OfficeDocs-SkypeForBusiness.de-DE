---
title: tblConfig
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
ms.openlocfilehash: 099060f0957ae21c14b285eac1b753ad0b8c1719
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
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
   

