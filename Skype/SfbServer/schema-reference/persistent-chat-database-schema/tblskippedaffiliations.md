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
ms.localizationpriority: medium
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations enthält die Zuordnungen, die nicht gelesen werden konnten (in der Regel aufgrund von Zugriffsfehlern bei Active Directory Domain Services).
ms.openlocfilehash: 3869107cf98251100ec7fa483bc403e1c19239a0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58622067"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations enthält die Zuordnungen, die nicht gelesen werden konnten (in der Regel aufgrund von Zugriffsfehlern bei Active Directory Domain Services).
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|prinID  <br/> |int, nicht NULL  <br/> |Prinzipal-ID  <br/> |
|affDescription  <br/> |nvarchar (256), nicht NULL  <br/> |Zeichenfolge, die die Zuordnung identifiziert.  <br/> Das Format lautet: guid:  _{0}_ uri: _{1}_> ID:  _{2}_ <br/> |
|updatedBy  <br/> |int, nicht NULL  <br/> |ID des Prinzipals, der diese Zeile aktualisiert hat. Der Wert ist immer 1 (Systembenutzer), da die Active Directory-Synchronisierung die einzige Quelle für diese Einträge ist.  <br/> |
   
**Keys**

|**Spalten**|**Beschreibung**|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |Primärschlüssel  <br/> |
|prinID  <br/> |Fremdschlüssel mit Abfrage der "tblPrincipal.prinID"-Tabelle.  <br/> |
   

