---
title: tblActivePeers
ms.reviewer: ''
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
ms.openlocfilehash: e921d6faa4f7bcf3e3c6f6dc9859f4bd0db16bc5
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212677"
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
   

