---
title: tblActivePeers
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
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: "\"tblActivePeers\" enthält die aktuellen Peer-zu-Peer-Verbindungen zwischen Chatdiensten."
ms.openlocfilehash: befba4086a78281fbfbec1e270b7c8e3f8174752
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812935"
---
# <a name="tblactivepeers"></a>tblActivePeers
 
"tblActivePeers" enthält die aktuellen Peer-zu-Peer-Verbindungen zwischen Chatdiensten.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|aplServerID  <br/> |int, nicht NULL  <br/> |ID des Servers, der den Eintrag bereitgestellt hat.  <br/> |
|aplPeerID  <br/> |int, nicht NULL  <br/> |ID des Peers, mit dem der bereitstellende Server verbunden ist.  <br/> |
   
**Keys**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |Primärschlüssel  <br/> |
|aplServerID  <br/> |Fremdschlüssel mit Abfrage der Tabelle "tblServerIdentity.serverID".  <br/> |
|aplPeerID  <br/> |Fremdschlüssel mit Abfrage der Tabelle "tblServerIdentity.serverID".  <br/> |
   

