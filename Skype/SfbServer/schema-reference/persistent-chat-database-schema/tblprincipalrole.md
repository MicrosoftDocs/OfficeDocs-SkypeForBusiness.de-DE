---
title: tblPrincipalRole
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
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole enthält explizite Rollen, die Knoten zugeordnet sind.
ms.openlocfilehash: bedb7025605dc5cd3e5808ac265931d8623060b3
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767323"
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
   

