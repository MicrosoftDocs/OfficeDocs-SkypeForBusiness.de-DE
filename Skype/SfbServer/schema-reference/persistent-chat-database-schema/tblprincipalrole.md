---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: TblPrincipalRole enthält explizite Rollen, die Knoten zugewiesen.
ms.openlocfilehash: 7c144f2f531af58c7c5693b28b224a2ee4456783
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904181"
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
   

