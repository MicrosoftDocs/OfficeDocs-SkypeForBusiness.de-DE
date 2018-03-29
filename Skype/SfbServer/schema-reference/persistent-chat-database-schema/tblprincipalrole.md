---
title: tblPrincipalRole
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
ms.openlocfilehash: 0e6c7f60f372bc14542567ccaa1b1b1a837c6c6d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
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
   

