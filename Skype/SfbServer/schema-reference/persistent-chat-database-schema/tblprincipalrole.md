---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole enthält explizite Rollen, die Knoten zugeordnet sind.
ms.openlocfilehash: 13c9c25db9ba1dbe281947468bbd834e80417899
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831555"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
tblPrincipalRole enthält explizite Rollen, die Knoten zugeordnet sind.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|prinRoleNodeID  <br/> |int, nicht NULL  <br/> |Knoten-ID, auf die sich die Rolle bezieht.  <br/> |
|prinRolePrinID  <br/> |int, nicht NULL  <br/> |Prinzipal-ID  <br/> |
|prinRoleTypeID  <br/> |int, nicht NULL  <br/> |Rollentyp-ID (von tblRoleType).  <br/> |
|prinRoleUpdatedBy  <br/> |int, nicht NULL  <br/> |ID des Prinzipals, der diesen Eintrag zuletzt aktualisiert hat.  <br/> |
   
**Keys**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |Primärschlüssel  <br/> |
|prinRoleNodeID  <br/> |Fremdschlüssel mit Abfrage der tblNode.nodeID-Tabelle.  <br/> |
|prinRolePrinID  <br/> |Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.  <br/> |
|prinRoleTypeID  <br/> |Fremdschlüssel mit Abfrage der tblRoleType.rtypeID-Tabelle.  <br/> |
   

