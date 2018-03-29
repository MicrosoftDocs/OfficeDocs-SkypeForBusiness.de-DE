---
title: Skippedaffiliations
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: "\"Skippedaffiliations\" enthält die zugehörigkeiten, die (gewöhnlich aufgrund von Active Directory-Domänendienste-Zugriffsfehlern) nicht gelesen werden konnten."
ms.openlocfilehash: 8809e75f7da7f08c3dee9a846cef332d9cba4371
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tblskippedaffiliations"></a>Skippedaffiliations
 
"Skippedaffiliations" enthält die zugehörigkeiten, die (gewöhnlich aufgrund von Active Directory-Domänendienste-Zugriffsfehlern) nicht gelesen werden konnten.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|prinID  <br/> |Int, nicht null  <br/> |Prinzipal-ID.  <br/> |
|affDescription  <br/> |Nvarchar (256), nicht null  <br/> |Eine Zeichenfolge, die die Zuordnung identifiziert.  <br/> Das Format lautet: Guid: _{0}_ Uri: _{1}_> Id: _{2}_ <br/> |
|updatedBy  <br/> |Int, nicht null  <br/> |ID des Prinzipals, der diese Zeile aktualisiert. Es ist immer 1 (Systembenutzer), da Active Directory-Synchronisierung die einzige Quelle für diese Einträge ist.  <br/> |
   
**Schlüssel**

|**Spalten**|**Beschreibung**|
|:-----|:-----|
|\<PrinID affDescription\>  <br/> |Primärschlüssel.  <br/> |
|prinID  <br/> |Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.  <br/> |
   

