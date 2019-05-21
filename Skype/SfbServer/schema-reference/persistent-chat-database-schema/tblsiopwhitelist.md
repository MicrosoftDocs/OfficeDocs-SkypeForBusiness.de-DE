---
title: tblSiopWhiteList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList ist die Liste der registrierten Add-Ins, die Knoten zugeordnet werden können.
ms.openlocfilehash: 3277ec3a2d4fe11000b2eda60fa2327547c77d2b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295174"
---
# <a name="tblsiopwhitelist"></a>tblSiopWhiteList
 
tblSiopWhiteList ist die Liste der registrierten Add-Ins, die Knoten zugeordnet werden können.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|siopID  <br/> |GUID, nicht NULL  <br/> |GUID des Add-Ins.  <br/> |
|siopName  <br/> |nvarchar (50); nicht NULL  <br/> |Anzeigename des Add-Ins.  <br/> |
|siopUrl  <br/> |nvarchar (255); nicht NULL  <br/> |Die URL des Add-Ins.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|siopID  <br/> |Primärschlüssel  <br/> |
   

