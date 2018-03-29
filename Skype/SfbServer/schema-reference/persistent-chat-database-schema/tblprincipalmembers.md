---
title: "\"tblprincipalmembers\""
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
ms.openlocfilehash: 77151cc245b90fa22d9da426a1448c49866dccc2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmembers"></a>"tblprincipalmembers"
 
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
   

