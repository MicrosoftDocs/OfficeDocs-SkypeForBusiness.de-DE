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
ms.openlocfilehash: 7ba8bb5730dc1c08a3d0f8aa13d1173192b7cc65134d90c75061ede0db5aa98d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336395"
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
   

