---
title: tblScopePrincipal
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
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal enthält Bereiche, die Knoten zugewiesen sind.
ms.openlocfilehash: 24a38ef4acf3e0d500c7652f5ca418af585343b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812443"
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
tblScopePrincipal enthält Bereiche, die Knoten zugewiesen sind.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|scopeNodeID  <br/> |int, nicht NULL  <br/> |Knoten-ID, auf die sich der Bereich bezieht.  <br/> |
|scopePrinID  <br/> |int, nicht NULL  <br/> |Prinzipal-ID.  <br/> |
|scopeIsDenied  <br/> |Bit, nicht NULL  <br/> |"True", wenn der Typ des Bereichs "verweigern" lautet. False, wenn allow.  <br/> |
|scopeUpdatedBy  <br/> |int, nicht NULL  <br/> |Die ID des Prinzipals, der diesen Eintrag zuletzt aktualisiert hat.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|\<scopeNodeID, scopePrinID\>  <br/> |Primärschlüssel  <br/> |
|scopeNodeID  <br/> |Fremdschlüssel mit Lookup in der tblNode. Node-Tabelle  <br/> |
|scopePrinID  <br/> |Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.  <br/> |
   

