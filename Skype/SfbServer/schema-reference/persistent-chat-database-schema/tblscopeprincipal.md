---
title: tblScopePrincipal
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
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: In "tblScopePrincipal" sind Bereiche enthalten, die Knoten zugeordnet sind.
ms.openlocfilehash: 84fa792a6698a474e41c0e623b826fb0b8c48d65
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844028"
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
In "tblScopePrincipal" sind Bereiche enthalten, die Knoten zugeordnet sind.
  
**Columns**

|**Spalte**|**Type**|**Beschreibung**|
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
   

