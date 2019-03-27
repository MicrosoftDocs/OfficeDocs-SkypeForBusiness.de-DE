---
title: tblPrincipalInvites
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: TblPrincipalInvites enthält Einladungen für alle bereitgestellten Benutzer aller Knoten Auto-INVITE aktiviert ist.
ms.openlocfilehash: fbf61265f4970b57ffa95a52c8bafa395fb3a331
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876690"
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
TblPrincipalInvites enthält Einladungen für alle bereitgestellten Benutzer aller Knoten Auto-INVITE aktiviert ist.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|prinID  <br/> |Int, nicht null  <br/> |Prinzipal-ID.  <br/> |
|invID  <br/> |Int, nicht null  <br/> |Eindeutige fortlaufende Zahl (pro Prinzipal-ID) generiert von der TblLastInviteId-Tabelle.  <br/> |
|nodeID  <br/> |Int, nicht null  <br/> |Knoten-ID (nur Chatroom).  <br/> |
|createdOn  <br/> |DateTime, nicht null  <br/> |Zeitpunkt der Erstellung.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|\<PrinID nodeID\>  <br/> |Primärschlüssel.  <br/> |
|prinID  <br/> |Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.  <br/> |
|nodeID  <br/> |Fremdschlüssel mit Abfrage der tblNode.nodeID-Tabelle.  <br/> |
   

