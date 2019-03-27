---
title: tblLastChatId
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: "\"lastchatid\" enthält die letzte Chat-ID, die generierte (und in der TblChat-Tabelle verwendete) für jeden Benutzer."
ms.openlocfilehash: 3208ada77643957295f9894cb58187c2b4bc7493
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884929"
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
