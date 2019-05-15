---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: "\"Skippedaffiliations\" enthält die zugehörigkeiten, die (gewöhnlich aufgrund von Active Directory-Domänendienste-Zugriffsfehlern) nicht gelesen werden konnten."
ms.openlocfilehash: 85fe836e75409a0a6aae22583358f9f88dc8d4e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924941"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
"Skippedaffiliations" enthält die zugehörigkeiten, die (gewöhnlich aufgrund von Active Directory-Domänendienste-Zugriffsfehlern) nicht gelesen werden konnten.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|prinID  <br/> |Int, nicht null  <br/> |Prinzipal-ID.  <br/> |
|affDescription  <br/> |Nvarchar (256), nicht null  <br/> |Eine Zeichenfolge, die die Zuordnung identifiziert.  <br/> Das Format lautet: Guid: _{0}_ Uri: _{1}_>-Id:_{2}_ <br/> |
|updatedBy  <br/> |Int, nicht null  <br/> |ID des Prinzipals, der diese Zeile aktualisiert. Es ist immer 1 (Systembenutzer), da Active Directory-Synchronisierung die einzige Quelle für diese Einträge ist.  <br/> |
   
**Schlüssel**

|**Spalten**|**Beschreibung**|
|:-----|:-----|
|\<PrinID affDescription\>  <br/> |Primärschlüssel.  <br/> |
|prinID  <br/> |Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.  <br/> |
   

