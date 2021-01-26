---
title: tblRoleType
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
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType ist eine statische Nachschlagetabelle mit Rollentypen und den zugehörigen Berechtigungssätzen.
ms.openlocfilehash: c440463d822b908a89c84eb9c85b70e9daf442be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831525"
---
# <a name="tblroletype"></a>tblRoleType
 
tblRoleType ist eine statische Nachschlagetabelle mit Rollentypen und den zugehörigen Berechtigungssätzen.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|rtypeID  <br/> |int, nicht NULL  <br/> |Rollentyp-ID.  <br/> |
|rtypeDesc  <br/> |nvarchar (256), not null  <br/> | Beschreibung des Rollentyps. Es gibt vier verfügbare Rollen: <br/>  Mitglied: Mitglied des Chatrooms <br/>  Manager: Chatroommanager <br/>  Sprachbefehl: Sprecher für einen Auditoriumchatroom <br/>  Ersteller: Kann Chatrooms erstellen <br/> |
|rtypeAllowedPermSet  <br/> |bigint, nicht NULL  <br/> | Berechtigungssatz für die Rolle. Die verwendeten Bits sind: <br/>  2: "True", wenn die Rolle Knoten verwalten kann. <br/>  4: "True", wenn die Rolle untergeordnete Knoten erstellen kann. <br/>  7: "True", wenn die Rolle an einem Chatroom (oder an einem Kinderchatroom einer Kategorie) teilnehmen kann. <br/>  8: "True", wenn die Rolle in einem Chatroom (oder in Kinderchatrooms einer Kategorie) chatten kann. <br/>  10: "True", wenn die Rolle den Chatverlauf auch dann lesen kann, wenn sie nicht mit einem Chatroom verbunden ist. <br/>  11: "True", wenn die Rolle den Chatroom sehen kann. (Dies wird durch Faktoren wie Umfang und Sichtbarkeit weiter verbessert.) <br/>  12: "True", wenn die Rolle in einem Auditoriumchatroom chatten kann. <br/>  13: "True", wenn die Rolle Sichtbarkeitsregeln beim Anzeigen von Knoten umgehen kann. <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|rtypeID  <br/> |Primärschlüssel  <br/> |
   

