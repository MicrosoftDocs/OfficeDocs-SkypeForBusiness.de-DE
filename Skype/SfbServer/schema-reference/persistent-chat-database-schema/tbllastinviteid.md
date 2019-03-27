---
title: tblLastInviteId
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: "\"tbllastinviteid\" enthält die letzte einladungs-ID, die generierte (und in der TblPrincipalInvites-Tabelle verwendete) für jeden Benutzer."
ms.openlocfilehash: 977911150992b2e90b7dc344af0550a25ad77221
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873937"
---
# <a name="tbllastinviteid"></a>tblLastInviteId
 
"tbllastinviteid" enthält die letzte einladungs-ID, die generierte (und in der TblPrincipalInvites-Tabelle verwendete) für jeden Benutzer.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|prinID  <br/> |Int, nicht null  <br/> |Prinzipal-ID.  <br/> |
|lastInviteID  <br/> |Int, nicht null  <br/> |Zuletzt verwendete Invite-ID.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|prinID  <br/> |Primärschlüssel.  <br/> |
|prinID  <br/> |Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.  <br/> |
   
## <a name="see-also"></a>Siehe auch

[tblPrincipalInvites](tblprincipalinvites.md)
