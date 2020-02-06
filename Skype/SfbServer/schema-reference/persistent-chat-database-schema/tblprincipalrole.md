---
title: tblPrincipalRole
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
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole enthält explizite Rollen, die Knoten zugewiesen sind.
ms.openlocfilehash: 1cc606ec3825bb664d4123154e97fabb15678cfd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813363"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
tblPrincipalRole enthält explizite Rollen, die Knoten zugewiesen sind.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|prinRoleNodeID  <br/> |int, nicht NULL  <br/> |Die Knoten-ID, auf die sich die Rolle bezieht.  <br/> |
|prinRolePrinID  <br/> |int, nicht NULL  <br/> |Prinzipal-ID.  <br/> |
|prinRoleTypeID  <br/> |int, nicht NULL  <br/> |Rollentyp-ID (aus tblRoleType).  <br/> |
|prinRoleUpdatedBy  <br/> |int, nicht NULL  <br/> |Die ID des Prinzipals, der diesen Eintrag zuletzt aktualisiert hat.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |Primärschlüssel  <br/> |
|prinRoleNodeID  <br/> |Fremdschlüssel mit Lookup in der tblNode. Node-Tabelle  <br/> |
|prinRolePrinID  <br/> |Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.  <br/> |
|prinRoleTypeID  <br/> |Fremdschlüssel mit Lookup in der tblRoleType. rtypeID-Tabelle.  <br/> |
   

