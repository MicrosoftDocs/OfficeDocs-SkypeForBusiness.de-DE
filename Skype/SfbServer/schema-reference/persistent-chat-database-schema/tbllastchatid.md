---
title: tblLastChatId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: "\"lastchatid\" enthält die letzte Chat-ID, die generierte (und in der TblChat-Tabelle verwendete) für jeden Benutzer."
ms.openlocfilehash: 9d19c6c873660683ff526eb144d74b6e8752bf80
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929966"
---
# <a name="tbllastchatid"></a>tblLastChatId
 
"lastchatid" enthält die letzte Chat-ID, die generierte (und in der TblChat-Tabelle verwendete) für jeden Benutzer.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|nodeID  <br/> |Int, nicht null  <br/> |Knoten-ID (nur Chatroom-Typ).  <br/> |
|lastChatID  <br/> |Bigint, nicht null  <br/> |Zuletzt verwendete Chat-ID.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|\<NodeID lastChatID\>  <br/> |Primärschlüssel (nur NodeID ist ausreichend für die Verarbeitung).  <br/> |
|nodeID  <br/> |Fremdschlüssel mit Abfrage der tblNode.nodeID-Tabelle.  <br/> |
   
## <a name="see-also"></a>Siehe auch

[tblChat](tblchat.md)
