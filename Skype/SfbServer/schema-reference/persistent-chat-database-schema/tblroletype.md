---
title: tblRoleType
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType ist eine statische Nachschlagetabelle mit Rollentypen und den zugehörigen Berechtigungssätzen.
ms.openlocfilehash: f1e224857d7c5b427176d786fc87b28206419bfa
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745731"
---
# <a name="tblroletype"></a>tblRoleType
 
tblRoleType ist eine statische Nachschlagetabelle mit Rollentypen und den zugehörigen Berechtigungssätzen.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|rtypeID  <br/> |int, nicht NULL  <br/> |Rollentyp-ID.  <br/> |
|rtypeDesc  <br/> |nvarchar (256), not null  <br/> | Beschreibung des Rollentyps. Es gibt vier verfügbare Rollen: <br/>  Mitglied: Chatroommitglied <br/>  Manager: Chatroom-Manager <br/>  Sprachausgabe: Referent für einen Auditorium-Chatroom <br/>  Creator: Kann Chatrooms erstellen <br/> |
|rtypeAllowedPermSet  <br/> |bigint, nicht NULL  <br/> | Berechtigungssatz für die Rolle. Die verwendeten Bits sind: <br/>  2: True, wenn die Rolle Knoten verwalten kann. <br/>  4: True, wenn die Rolle untergeordnete Knoten erstellen kann. <br/>  7: "True", wenn die Rolle an einem Chatroom teilnehmen kann (oder an Chatrooms für Kinder einer Kategorie). <br/>  8: "True", wenn die Rolle in einem Chatroom (oder in Chatrooms für Kinder einer Kategorie) chatten kann. <br/>  10: "True", wenn die Rolle den Chatverlauf auch dann lesen kann, wenn sie nicht mit einem Chatroom verbunden ist. <br/>  11: "True", wenn die Rolle den Chatroom sehen kann. (Dies wird durch Faktoren wie Umfang und Sichtbarkeit weiter optimiert.) <br/>  12: "True", wenn die Rolle in einem Auditorium-Chatroom chatten kann. <br/>  13: "True", wenn die Rolle Beim Anzeigen von Knoten Sichtbarkeitsregeln umgehen kann. <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|rtypeID  <br/> |Primärschlüssel  <br/> |
   

