---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers enthält die aktuellen Peer-to-Peer-Verbindungen zwischen Chat Diensten.
ms.openlocfilehash: f45a04019cafc2304baf825b5000e96ca7a6cead
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295545"
---
# <a name="tblactivepeers"></a>tblActivePeers
 
tblActivePeers enthält die aktuellen Peer-to-Peer-Verbindungen zwischen Chat Diensten.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|aplServerID  <br/> |int, nicht NULL  <br/> |Die ID des Servers, der den Eintrag gepostet hat.  <br/> |
|aplPeerID  <br/> |int, nicht NULL  <br/> |Die ID des Peers, mit dem der Buchungsserver verbunden ist.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |Primärschlüssel  <br/> |
|aplServerID  <br/> |Fremdschlüssel mit Lookup in der tblServerIdentity. Server-Tabelle.  <br/> |
|aplPeerID  <br/> |Fremdschlüssel mit Lookup in der tblServerIdentity. Server-Tabelle.  <br/> |
   

