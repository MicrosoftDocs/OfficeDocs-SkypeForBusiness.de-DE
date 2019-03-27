---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: "\"tblprincipalmembers\" enthält prinzipalmitgliedschaften."
ms.openlocfilehash: 2b2b9616c76095ec27178887e69dd482bcf6da92
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874252"
---
# <a name="tblprincipalmembers"></a>tblPrincipalMembers
 
"tblprincipalmembers" enthält prinzipalmitgliedschaften.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|prinID  <br/> |Int, nicht null  <br/> |Prinzipal-ID.  <br/> |
|memberADPath  <br/> |Nvarchar (384), nicht null  <br/> |Distinguished Name eines Elements. Ein Element hat keinen zu einem Prinzipal (in der TblPrincipal-Tabelle).  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|\<PrinID memberADPath\>  <br/> |Primärschlüssel.  <br/> |
|prinID  <br/> |Fremdschlüssel mit Abfrage von tblprincipal.prinid.  <br/> |
   

