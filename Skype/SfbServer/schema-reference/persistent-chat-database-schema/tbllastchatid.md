---
title: tblLastChatId
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: '"LastChatId" enthält die zuletzt generierte (und in der tblChat-Tabelle verwendete) Chat-ID für jeden Benutzer.'
---

# <a name="tbllastchatid"></a>tblLastChatId
 
"LastChatId" enthält die zuletzt generierte (und in der tblChat-Tabelle verwendete) Chat-ID für jeden Benutzer.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, nicht NULL  <br/> |Knoten-ID (nur Chatroom).  <br/> |
|lastChatID  <br/> |bigint, nicht NULL  <br/> |Zuletzt verwendete Chat-ID.  <br/> |
   
**Keys**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|\<nodeID, lastChatID\>  <br/> |Primärschlüssel (für die Verarbeitung genügt nodeID).  <br/> |
|nodeID  <br/> |Fremdschlüssel mit Abfrage der Tabelle "Node.nodeID".  <br/> |
   
## <a name="see-also"></a>Siehe auch

[tblChat](tblchat.md)
