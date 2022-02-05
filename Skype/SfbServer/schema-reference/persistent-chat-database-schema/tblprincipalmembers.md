---
title: tblPrincipalMembers
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: '"tblPrincipalMembers" enthält Prinzipalmitgliedschaften.'
---

# <a name="tblprincipalmembers"></a>tblPrincipalMembers
 
"tblPrincipalMembers" enthält Prinzipalmitgliedschaften.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|prinID  <br/> |int, nicht NULL  <br/> |Prinzipal-ID  <br/> |
|memberADPath  <br/> |nvarchar (256), nicht NULL  <br/> |Distinguished Name (DN) eines Mitglieds. Ein Mitglied muss kein Prinzipal sein (in der Tabelle "tblPrincipal").  <br/> |
   
**Keys**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|\<prinID, memberADPath\>  <br/> |Primärschlüssel  <br/> |
|prinID  <br/> |Fremdschlüssel mit Abfrage von tblPrincipal.prinID.  <br/> |
   

