---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations enthält die Zuordnungen, die nicht gelesen werden konnten (in der Regel aufgrund von Zugriffsfehlern in Active Directory-Domänendiensten).
ms.openlocfilehash: 8a138993e12a49f72842808d720a5f778195c6ff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812013"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations enthält die Zuordnungen, die nicht gelesen werden konnten (in der Regel aufgrund von Zugriffsfehlern in Active Directory-Domänendiensten).
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|prinID  <br/> |int, nicht NULL  <br/> |Prinzipal-ID.  <br/> |
|affDescription  <br/> |nvarchar (256); nicht NULL  <br/> |Eine Zeichenfolge, die die Zuordnung kennzeichnet.  <br/> Das Format lautet: GUID: _{0}_ URI: _{1}_>-ID:_{2}_ <br/> |
|updatedBy  <br/> |int, nicht NULL  <br/> |Die ID des Prinzipals, der diese Zeile aktualisiert hat. Es ist immer 1 (Systembenutzer), da die Active Directory-Synchronisierung die einzige Quelle für diese Einträge ist.  <br/> |
   
**Schlüssel**

|**Spalte (n)**|**Beschreibung**|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |Primärschlüssel  <br/> |
|prinID  <br/> |Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.  <br/> |
   

