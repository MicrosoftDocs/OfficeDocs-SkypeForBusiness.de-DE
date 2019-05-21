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
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId enthält die letzte Chat-ID, die für jeden Benutzer generiert (und in der tblChat-Tabelle verwendet) wurde.
ms.openlocfilehash: f14d8090fd3252d88ef747de93a987f51870a63b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295398"
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
