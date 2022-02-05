---
title: tblSiopWhiteList
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: 'Bei "tblSiopWhiteList" handelt es sich um die Liste der registrierten Add-Ins, die mit Knoten verknüpft werden können.'
---

# <a name="tblsiopwhitelist"></a>tblSiopWhiteList
 
Bei "tblSiopWhiteList" handelt es sich um die Liste der registrierten Add-Ins, die mit Knoten verknüpft werden können.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|siopID  <br/> |GUID, nicht NULL  <br/> |GUID des Add-Ins.  <br/> |
|siopName  <br/> |nvarchar (50), nicht NULL  <br/> |Anzeigename des Add-Ins.  <br/> |
|siopUrl  <br/> |nvarchar (255), nicht NULL  <br/> |URL des Add-Ins.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|siopID  <br/> |Primärschlüssel  <br/> |
   

