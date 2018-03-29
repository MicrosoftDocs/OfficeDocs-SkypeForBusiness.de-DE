---
title: tblPrincipalInvites
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
ms.openlocfilehash: ae33d45e14340b6374299343f13c8352db1a5021
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
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
   

