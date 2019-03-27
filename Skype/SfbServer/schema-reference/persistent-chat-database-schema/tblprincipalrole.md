---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: TblPrincipalRole enthält explizite Rollen, die Knoten zugewiesen.
ms.openlocfilehash: 69cfb0cb2b821064801a07510758514bb5d33128
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890769"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
TblPrincipalRole enthält explizite Rollen, die Knoten zugewiesen.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|prinRoleNodeID  <br/> |Int, nicht null  <br/> |Knoten-ID, die für die Rolle gilt.  <br/> |
|prinRolePrinID  <br/> |Int, nicht null  <br/> |Prinzipal-ID.  <br/> |
|prinRoleTypeID  <br/> |Int, nicht null  <br/> |Rollentyp-ID (von TblRoleType).  <br/> |
|prinRoleUpdatedBy  <br/> |Int, nicht null  <br/> |ID des Prinzipals, der diesen Eintrag zuletzt aktualisiert.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|\<PrinRoleNodeID, PrinRolePrinID, prinRoleTypeID\>  <br/> |Primärschlüssel.  <br/> |
|prinRoleNodeID  <br/> |Fremdschlüssel mit Abfrage der tblNode.nodeID-Tabelle.  <br/> |
|prinRolePrinID  <br/> |Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.  <br/> |
|prinRoleTypeID  <br/> |Fremdschlüssel mit Abfrage der tblRoleType.rtypeID-Tabelle.  <br/> |
   

