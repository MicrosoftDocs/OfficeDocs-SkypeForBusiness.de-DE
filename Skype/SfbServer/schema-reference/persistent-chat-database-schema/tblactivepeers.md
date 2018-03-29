---
title: tblActivePeers
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: "\"TblActivePeers\" enthält die aktuellen Peer-zu-Peer-Verbindungen zwischen Chat-Dienste."
ms.openlocfilehash: 5dc585a8db67c1bbdcc1c3933018b1296fd75484
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tblactivepeers"></a>tblActivePeers
 
"TblActivePeers" enthält die aktuellen Peer-zu-Peer-Verbindungen zwischen Chat-Dienste.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|aplServerID  <br/> |Int, nicht null  <br/> |ID des Servers, der den Eintrag bereitgestellt hat.  <br/> |
|aplPeerID  <br/> |Int, nicht null  <br/> |ID des Peers, die mit der bereitstellende Server verbunden ist.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|\<AplServerID aplPeerID\>  <br/> |Primärschlüssel.  <br/> |
|aplServerID  <br/> |Fremdschlüssel mit Abfrage der Tabelle "tblserveridentity.ServerID".  <br/> |
|aplPeerID  <br/> |Fremdschlüssel mit Abfrage der Tabelle "tblserveridentity.ServerID".  <br/> |
   

