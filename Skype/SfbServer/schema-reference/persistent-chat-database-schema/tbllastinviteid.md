---
title: tblLastInviteId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId enthält die letzte Einladungs-ID, die für jeden Benutzer generiert (und in der tblPrincipalInvites-Tabelle verwendet) wurde.
ms.openlocfilehash: f36b0824bb8e9dbf2cb0aa14575cc1649bde708a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295356"
---
# <a name="tbllastinviteid"></a>tblLastInviteId
 
tblLastInviteId enthält die letzte Einladungs-ID, die für jeden Benutzer generiert (und in der tblPrincipalInvites-Tabelle verwendet) wurde.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|prinID  <br/> |int, nicht NULL  <br/> |Prinzipal-ID.  <br/> |
|lastInviteID  <br/> |int, nicht NULL  <br/> |Zuletzt verwendete Einladungs-ID.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|prinID  <br/> |Primärschlüssel  <br/> |
|prinID  <br/> |Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.  <br/> |
   
## <a name="see-also"></a>Siehe auch

[tblPrincipalInvites](tblprincipalinvites.md)
