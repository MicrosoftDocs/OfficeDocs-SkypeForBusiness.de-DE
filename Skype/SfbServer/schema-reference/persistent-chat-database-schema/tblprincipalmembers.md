---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: "\"tblprincipalmembers\" enthält prinzipalmitgliedschaften."
ms.openlocfilehash: be66ee6124c7b0306583bcb10f7d78b777fcf10c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904160"
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
   

