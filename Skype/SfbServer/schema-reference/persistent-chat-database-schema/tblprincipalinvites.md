---
title: tblPrincipalInvites
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
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites enthält Einladungen für alle bereitgestellten Benutzer aller Knoten, für die die Funktion der automatischen Einladung (Auto-Invite) aktiviert ist.
ms.openlocfilehash: d7993cba89474fe5d7343cd25f39c3363b8be866
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864582"
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
tblPrincipalInvites enthält Einladungen für alle bereitgestellten Benutzer aller Knoten, für die die Funktion der automatischen Einladung (Auto-Invite) aktiviert ist.
  
**Columns**

|**Spalte**|**Type**|**Beschreibung**|
|:-----|:-----|:-----|
|prinID  <br/> |int, nicht NULL  <br/> |Prinzipal-ID  <br/> |
|invID  <br/> |int, nicht NULL  <br/> |Eindeutige fortlaufende Zahl (pro Prinzipal-ID), generiert von der tblLastInviteId-Tabelle.  <br/> |
|nodeID  <br/> |int, nicht NULL  <br/> |Knoten-ID (nur Chatroom).  <br/> |
|createdOn  <br/> |datetime, nicht NULL  <br/> |Zeitpunkt des Erstellens.  <br/> |
   
**Keys**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|\<prinID, nodeID\>  <br/> |Primärschlüssel  <br/> |
|prinID  <br/> |Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.  <br/> |
|nodeID  <br/> |Fremdschlüssel mit Abfrage der tblNode.nodeID-Tabelle.  <br/> |
   

