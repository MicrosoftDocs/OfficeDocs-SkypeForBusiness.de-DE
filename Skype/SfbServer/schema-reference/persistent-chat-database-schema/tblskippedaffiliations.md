---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations enthält die Zuordnungen, die nicht gelesen werden konnten (in der Regel aufgrund von Zugriffsfehlern der Active Directory-Domänendienste).
ms.openlocfilehash: 3061a399de804898d3dc2c616fb3766206c2d624
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831425"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations enthält die Zuordnungen, die nicht gelesen werden konnten (in der Regel aufgrund von Zugriffsfehlern der Active Directory-Domänendienste).
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|prinID  <br/> |int, nicht NULL  <br/> |Prinzipal-ID  <br/> |
|affDescription  <br/> |nvarchar (256), nicht NULL  <br/> |Zeichenfolge, die die Zuordnung identifiziert.  <br/> Das Format ist: guid:  _{0}_ uri: _{1}_> ID:  _{2}_ <br/> |
|updatedBy  <br/> |int, nicht NULL  <br/> |ID des Prinzipals, der diese Zeile aktualisiert hat. Der Wert ist immer 1 (Systembenutzer), da die Active Directory-Synchronisierung die einzige Quelle für diese Einträge ist.  <br/> |
   
**Keys**

|**Column(s)**|**Beschreibung**|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |Primärschlüssel  <br/> |
|prinID  <br/> |Fremdschlüssel mit Abfrage der "tblPrincipal.prinID"-Tabelle.  <br/> |
   

