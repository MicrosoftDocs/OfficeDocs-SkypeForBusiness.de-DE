---
title: tblLastChatId
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
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId enthält die letzte Chat-ID, die für jeden Benutzer generiert (und in der tblChat-Tabelle verwendet) wurde.
ms.openlocfilehash: 95498f077948e1b400d0a370762c121def703e8c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814583"
---
# <a name="tbllastchatid"></a>tblLastChatId
 
tblLastChatId enthält die letzte Chat-ID, die für jeden Benutzer generiert (und in der tblChat-Tabelle verwendet) wurde.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, nicht NULL  <br/> |Knoten-ID (nur Chatroom-Typ).  <br/> |
|lastChatID  <br/> |bigint, nicht NULL  <br/> |Zuletzt verwendete Chat-ID.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|\<Knoten-lastChatID\>  <br/> |Primärschlüssel (nur Knoten-Nr ist für die Verarbeitung ausreichend).  <br/> |
|nodeID  <br/> |Fremdschlüssel mit Lookup in der tblNode. Node-Tabelle  <br/> |
   
## <a name="see-also"></a>Siehe auch

[tblChat](tblchat.md)
