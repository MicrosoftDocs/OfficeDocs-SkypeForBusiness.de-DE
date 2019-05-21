---
title: tblPrincipalType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType enthält Prinzipaltypen, um zu kategorisieren, was in der tblPrincipal-Tabelle enthalten ist.
ms.openlocfilehash: 473b718a8a863432a71ff04d709bef4c0ac1327f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295244"
---
# <a name="tblprincipaltype"></a>tblPrincipalType
 
tblPrincipalType enthält Prinzipaltypen, um zu kategorisieren, was in der tblPrincipal-Tabelle enthalten ist.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|ptypeID  <br/> |smallint, nicht NULL  <br/> |Prinzipaltyp-ID.  <br/> |
|ptypeDesc  <br/> |nvarchar (256); nicht NULL  <br/> |Beschreibung des Typs.  <br/> |
|ptypeIsSystemUser  <br/> |Bit, nicht NULL  <br/> |"True", wenn der Typ den Prinzipalen entspricht, die für interne Zwecke verwendet werden.  <br/> |
|ptypeIsUser  <br/> |Bit, nicht NULL  <br/> |"True", wenn es sich bei dem Typ um einen Benutzertyp handelt.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|ptypeID  <br/> |Primärschlüssel  <br/> |
   
**Prinzipal Werte**

|**ID**|**Rolle**|**Beschreibung**|**Benutzer**|
|:-----|:-----|:-----|:-----|
|1  <br/> |Beliebig  <br/> |Generischer Prinzipal ohne bekannten Typ. Wird in der tblPrincipal-Tabelle nicht verwendet.  <br/> ||
|2  <br/> |AnyUser  <br/> |Generisches Prinzipal des Benutzertyps. Wird in der tblPrincipal-Tabelle nicht verwendet.  <br/> |Ja  <br/> |
|3  <br/> |AnyGroup  <br/> |Generischer Prinzipal mit Gruppen Semantik Wird in der tblPrincipal-Tabelle nicht verwendet.  <br/> ||
|4  <br/> |Multiswitch  <br/> |Prinzipal, der intern vom beständigen Chat Server verwendet wird.  <br/> ||
|5  <br/> |User  <br/> |Normaler Benutzer.  <br/> |Ja  <br/> |
|8  <br/> |DC  <br/> |Active Directory-Domänendienste-Domänencontroller.  <br/> ||
|9  <br/> |Gruppe  <br/> |Active Directory-Sicherheitsgruppe.  <br/> ||
|10  <br/> |Ordner  <br/> |Active Directory-Container oder-Organisationseinheit.  <br/> ||
   
## <a name="see-also"></a>Siehe auch

[tblPrincipal](tblprincipal.md)
