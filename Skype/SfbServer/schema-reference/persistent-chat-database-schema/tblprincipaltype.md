---
title: tblPrincipalType
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
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType enthält Prinzipaltypen zur Kategorisierung des Inhalts der tblPrincipal-Tabelle.
ms.openlocfilehash: 3fa86d3cfed058387681ff0fc5eb2b3ec7afb26d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743111"
---
# <a name="tblprincipaltype"></a>tblPrincipalType
 
tblPrincipalType enthält Prinzipaltypen zur Kategorisierung des Inhalts der tblPrincipal-Tabelle.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|ptypeID  <br/> |smallint, nicht NULL  <br/> |Prinzipaltyp-ID  <br/> |
|ptypeDesc  <br/> |nvarchar (256), nicht NULL  <br/> |Beschreibung des Typs.  <br/> |
|ptypeIsSystemUser  <br/> |bit, nicht NULL  <br/> |TRUE, wenn der Typ den Prinzipalen entspricht, die zu internen Zwecken verwendet werden.  <br/> |
|ptypeIsUser  <br/> |bit, nicht NULL  <br/> |TRUE, wenn es sich beim Typ um einen Benutzertyp handelt.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|ptypeID  <br/> |Primärschlüssel  <br/> |
   
**Prinzipalwerte**

|**ID**|**Rolle**|**Beschreibung**|**Benutzer**|
|:-----|:-----|:-----|:-----|
|1  <br/> |Any  <br/> |Allgemeiner Prinzipal ohne bekannten Typ. Keine Verwendung in tblPrincipal-Tabelle.  <br/> ||
|2  <br/> |AnyUser  <br/> |Allgemeiner Prinzipal vom Typ Benutzer. Keine Verwendung in tblPrincipal-Tabelle.  <br/> |Ja  <br/> |
|3  <br/> |AnyGroup  <br/> |Allgemeiner Prinzipal mit Gruppensemantik. Keine Verwendung in tblPrincipal-Tabelle.  <br/> ||
|4   <br/> |SystemUser  <br/> |Prinzipal, der intern vom Server für beständigen Chat verwendet wird.  <br/> ||
|5  <br/> |Benutzer  <br/> |Regelmäßiger Benutzer.  <br/> |Ja  <br/> |
|8   <br/> |Gleichstrom  <br/> |Active Directory Domain Services-Domänencontroller.  <br/> ||
|9   <br/> |Gruppe  <br/> |Active Directory-Sicherheitsgruppe  <br/> ||
|10  <br/> |Ordner  <br/> |Active Directory-Container oder Organisationseinheit  <br/> ||
   
## <a name="see-also"></a>Weitere Informationen

[tblPrincipal](tblprincipal.md)
