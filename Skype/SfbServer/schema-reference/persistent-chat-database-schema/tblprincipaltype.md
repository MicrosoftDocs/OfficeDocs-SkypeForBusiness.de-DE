---
title: "\"tblprincipaltype\""
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: TblPrincipalType enthält Prinzipaltypen zur Kategorisierung in der TblPrincipal-Tabelle.
ms.openlocfilehash: 3d1ec9b83561f06d3f8b1871223aafdf5c0775cb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipaltype"></a>"tblprincipaltype"
 
TblPrincipalType enthält Prinzipaltypen zur Kategorisierung in der TblPrincipal-Tabelle.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|ptypeID  <br/> |Smallint, nicht null  <br/> |Prinzipaltyp-ID  <br/> |
|ptypeDesc  <br/> |Nvarchar (256), nicht null  <br/> |Beschreibung des Typs.  <br/> |
|ptypeIsSystemUser  <br/> |Bit, nicht null  <br/> |True, wenn der Typ den Prinzipalen entspricht, die zu internen Zwecken verwendet werden.  <br/> |
|ptypeIsUser  <br/> |Bit, nicht null  <br/> |True, wenn der Typ einen Benutzertyp handelt.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|ptypeID  <br/> |Primärschlüssel.  <br/> |
   
**Prinzipalwerte**

|**ID**|**Rolle**|**Beschreibung**|**User**|
|:-----|:-----|:-----|:-----|
|1  <br/> |Beliebig  <br/> |Generische Principal mit kein bekannter Typ. In der TblPrincipal-Tabelle verwendet nicht.  <br/> ||
|2  <br/> |AnyUser  <br/> |Generische Prinzipal vom Benutzertyp. In der TblPrincipal-Tabelle verwendet nicht.  <br/> |Ja  <br/> |
|3  <br/> |AnyGroup  <br/> |Generische Prinzipal semantische-Gruppe. In der TblPrincipal-Tabelle verwendet nicht.  <br/> ||
|4  <br/> |SystemUser  <br/> |Intern von Persistent Chat Server verwendeter Prinzipal.  <br/> ||
|5  <br/> |Benutzer  <br/> |Regelmäßiger Benutzer.  <br/> |Ja  <br/> |
|8  <br/> |DC  <br/> |Active Directory-Domänendienste-Domänencontroller.  <br/> ||
|9  <br/> |Gruppe  <br/> |Active Directory-Sicherheitsgruppe.  <br/> ||
|10  <br/> |Ordner  <br/> |Active Directory-Container oder Organisationseinheit.  <br/> ||
   
## <a name="see-also"></a>Siehe auch

#### 

[tblPrincipal](tblprincipal.md)

