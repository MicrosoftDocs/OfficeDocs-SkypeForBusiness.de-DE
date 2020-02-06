---
title: tblRoleType
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
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType ist eine statische Nachschlagetabelle mit Rollentypen und zugehörigen Berechtigungssätzen.
ms.openlocfilehash: 888628c1aca01e90694ed946569a81b1b7394b95
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812903"
---
# <a name="tblroletype"></a>tblRoleType
 
tblRoleType ist eine statische Nachschlagetabelle mit Rollentypen und zugehörigen Berechtigungssätzen.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|rtypeID  <br/> |int, nicht NULL  <br/> |ID des Rollentyps.  <br/> |
|rtypeDesc  <br/> |nvarchar (256); nicht NULL  <br/> | Beschreibung des Rollentyps. Es gibt vier verfügbare Rollen: <br/>  Mitglied: Chatroom-Mitglied <br/>  Manager: Chat Room Manager <br/>  Geäußert: Referent für einen Chatroom für Auditorium <br/>  Creator: kann Chatrooms erstellen <br/> |
|rtypeAllowedPermSet  <br/> |bigint, nicht NULL  <br/> | Der Berechtigungssatz für die Rolle. Die verwendeten Bits sind: <br/>  2: true, wenn die Rolle Knoten verwalten kann. <br/>  4: true, wenn die Rolle untergeordnete Knoten erstellen kann. <br/>  7: true, wenn die Rolle einem Chatroom (oder Chatrooms einer Kategorie) beitreten kann. <br/>  8: true, wenn die Rolle in einem Chatroom (oder in Chatrooms einer Kategorie) chatten kann. <br/>  10: true, wenn die Rolle das Chat-Protokoll lesen kann, selbst wenn Sie nicht zu einem Chatroom gehört. <br/>  11: true, wenn die Rolle den Chatroom sehen kann. (Dies wird durch Faktoren wie Bereich und Sichtbarkeit weiter verfeinert.) <br/>  12: true, wenn die Rolle in einem Auditorium-Chatroom chatten kann. <br/>  13: true, wenn die Rolle Sichtbarkeitsregeln beim Anzeigen von Knoten umgehen kann. <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|rtypeID  <br/> |Primärschlüssel  <br/> |
   

