---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers enthält Prinzipal Mitgliedschaften.
ms.openlocfilehash: 12c3bf86b7416665f0f2355af0bfc9f98e3c1f1a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295286"
---
# <a name="tblprincipalmembers"></a>tblPrincipalMembers
 
tblPrincipalMembers enthält Prinzipal Mitgliedschaften.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|prinID  <br/> |int, nicht NULL  <br/> |Prinzipal-ID.  <br/> |
|memberADPath  <br/> |nvarchar (384); nicht NULL  <br/> |Distinguished Name eines Members. Ein Mitglied muss kein Prinzipal sein (in der tblPrincipal-Tabelle).  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|\<prinID, memberADPath\>  <br/> |Primärschlüssel  <br/> |
|prinID  <br/> |Fremdschlüssel mit Lookup in tblPrincipal. prinID.  <br/> |
   

