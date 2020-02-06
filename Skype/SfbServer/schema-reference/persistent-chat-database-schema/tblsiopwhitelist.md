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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList ist die Liste der registrierten Add-Ins, die Knoten zugeordnet werden können.
ms.openlocfilehash: ae287a1a32b09ce309c688dac2a042913383a263
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812113"
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
   

