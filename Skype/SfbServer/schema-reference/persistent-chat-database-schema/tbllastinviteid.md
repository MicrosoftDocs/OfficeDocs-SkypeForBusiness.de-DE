---
title: tblLastInviteId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: "\"tbllastinviteid\" enthält die letzte einladungs-ID, die generierte (und in der TblPrincipalInvites-Tabelle verwendete) für jeden Benutzer."
ms.openlocfilehash: f57ca67a91b71b9245644a53eb3e5c5771ca6fb0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929903"
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
