---
title: tblPrincipalInvites
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
ms.localizationpriority: medium
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites enthält Einladungen für alle bereitgestellten Benutzer aller Knoten, für die die Funktion der automatischen Einladung (Auto-Invite) aktiviert ist.
ms.openlocfilehash: c2f61f4edcbf82faf7e2f7b4af06ce18bd6afc70
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604624"
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
tblPrincipalInvites enthält Einladungen für alle bereitgestellten Benutzer aller Knoten, für die die Funktion der automatischen Einladung (Auto-Invite) aktiviert ist.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
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
   

