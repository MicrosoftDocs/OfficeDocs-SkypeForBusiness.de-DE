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
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType ist eine statische Nachschlagetabelle mit Rollentypen und zugehörigen Berechtigungssätzen.
ms.openlocfilehash: 8d49e9f2c61b8672a01a9c77bcc825925a4e7b2b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295216"
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
   

