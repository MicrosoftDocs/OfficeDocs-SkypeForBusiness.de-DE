---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: "\"tblActivePeers\" enthält die aktuellen Peer-zu-Peer-Verbindungen zwischen Chatdiensten."
ms.openlocfilehash: 980364d2483d4418177d5eaeceeb9a7ec884871d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852859"
---
# <a name="tblactivepeers"></a>tblActivePeers
 
"tblActivePeers" enthält die aktuellen Peer-zu-Peer-Verbindungen zwischen Chatdiensten.
  
**Columns**

|**Spalte**|**Type**|**Beschreibung**|
|:-----|:-----|:-----|
|aplServerID  <br/> |int, nicht NULL  <br/> |ID des Servers, der den Eintrag bereitgestellt hat.  <br/> |
|aplPeerID  <br/> |int, nicht NULL  <br/> |ID des Peers, mit dem der bereitstellende Server verbunden ist.  <br/> |
   
**Keys**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |Primärschlüssel  <br/> |
|aplServerID  <br/> |Fremdschlüssel mit Abfrage der Tabelle "tblServerIdentity.serverID".  <br/> |
|aplPeerID  <br/> |Fremdschlüssel mit Abfrage der Tabelle "tblServerIdentity.serverID".  <br/> |
   

