---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: "\"TblActivePeers\" enthält die aktuellen Peer-zu-Peer-Verbindungen zwischen Chat-Dienste."
ms.openlocfilehash: 7d7f995b878d6e47878636bee6f9c16ac142352e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929875"
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
   

