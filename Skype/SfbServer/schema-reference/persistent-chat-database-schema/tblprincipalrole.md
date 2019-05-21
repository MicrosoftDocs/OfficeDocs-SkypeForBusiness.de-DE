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
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole enthält explizite Rollen, die Knoten zugewiesen sind.
ms.openlocfilehash: 9675713afba5753378f4d01b70489d0eee93b8bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295237"
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
   

