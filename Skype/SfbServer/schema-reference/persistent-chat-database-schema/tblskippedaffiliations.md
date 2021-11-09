---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: e5d72c132f0fa9440f5c03c56e51c569adce4edd
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60838417"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations enthält die Zuordnungen, die nicht gelesen werden konnten (in der Regel aufgrund von Zugriffsfehlern bei Active Directory Domain Services).
  
**Columns**

|**Spalte**|**Type**|**Beschreibung**|
|:-----|:-----|:-----|
|prinID  <br/> |int, nicht NULL  <br/> |Prinzipal-ID  <br/> |
|affDescription  <br/> |nvarchar (256), nicht NULL  <br/> |Zeichenfolge, die die Zuordnung identifiziert.  <br/> Das Format lautet: guid:  _{0}_ uri: _{1}_> ID:  _{2}_ <br/> |
|updatedBy  <br/> |int, nicht NULL  <br/> |ID des Prinzipals, der diese Zeile aktualisiert hat. Der Wert ist immer 1 (Systembenutzer), da die Active Directory-Synchronisierung die einzige Quelle für diese Einträge ist.  <br/> |
   
**Keys**

|**Spalten**|**Beschreibung**|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |Primärschlüssel  <br/> |
|prinID  <br/> |Fremdschlüssel mit Abfrage der "tblPrincipal.prinID"-Tabelle.  <br/> |
   

