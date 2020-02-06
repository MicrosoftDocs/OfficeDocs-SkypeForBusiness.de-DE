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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers enthält die aktuellen Peer-to-Peer-Verbindungen zwischen Chat Diensten.
ms.openlocfilehash: 4604c13dbff9565748dd59e5917a5c133bd71947
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814713"
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
   

