---
title: tblSiopWhiteList
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: Bei "tblSiopWhiteList" handelt es sich um die Liste der registrierten Add-Ins, die mit Knoten verknüpft werden können.
ms.openlocfilehash: 7a84170ccf79e3cb84c876a1bc1828c4eabf4e78
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743101"
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
   

