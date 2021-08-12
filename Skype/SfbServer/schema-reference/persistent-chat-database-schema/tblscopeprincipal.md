---
title: tblScopePrincipal
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
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: In "tblScopePrincipal" sind Bereiche enthalten, die Knoten zugeordnet sind.
ms.openlocfilehash: e86b259126ee58c26246e78e1afd44a5e5122cbdbaaabb7f0967bb2bba7e5d39
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337593"
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
In "tblScopePrincipal" sind Bereiche enthalten, die Knoten zugeordnet sind.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|scopeNodeID  <br/> |int, nicht NULL  <br/> |Knoten-ID, auf die sich der Bereich bezieht.  <br/> |
|scopePrinID  <br/> |int, nicht NULL  <br/> |Prinzipal-ID  <br/> |
|scopeIsDenied  <br/> |bit, nicht NULL  <br/> |True, wenn Bereichstyp "Verweigern" ist; False wenn "Zulassen".  <br/> |
|scopeUpdatedBy  <br/> |int, nicht NULL  <br/> |ID des Prinzipals, der diesen Eintrag zuletzt aktualisiert hat.  <br/> |
   
**Keys**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|\<scopeNodeID, scopePrinID\>  <br/> |Primärschlüssel  <br/> |
|scopeNodeID  <br/> |Fremdschlüssel mit Abfrage von Tabelle "tblNode.nodeID".  <br/> |
|scopePrinID  <br/> |Fremdschlüssel mit Abfrage von Tabelle "tblPrincipal.prinID".  <br/> |
   

