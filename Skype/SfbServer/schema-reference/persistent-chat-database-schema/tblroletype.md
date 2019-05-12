---
title: tblRoleType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: "\"tblroletype\" ist eine statische Nachschlagetabelle mit Rollentypen und deren zugeordneten Berechtigungssätzen."
ms.openlocfilehash: 074b65d3f701d122bbb311da3096e6727dd17264
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924963"
---
# <a name="tblroletype"></a>tblRoleType
 
"tblroletype" ist eine statische Nachschlagetabelle mit Rollentypen und deren zugeordneten Berechtigungssätzen.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|rtypeID  <br/> |Int, nicht null  <br/> |Rollentyps.  <br/> |
|rtypeDesc  <br/> |Nvarchar (256), nicht null  <br/> | Beschreibung der Rolle-Typ. Es gibt vier verfügbare Rollen: <br/>  Mitglied: chatroommitglied <br/>  Manager: chatroommanager <br/>  Leitend: Referent für einen auditoriumchatroom <br/>  Ersteller: Kann Chatrooms erstellen. <br/> |
|rtypeAllowedPermSet  <br/> |Bigint, nicht null  <br/> | Berechtigungssatz für die Rolle. Die verwendete Bits sind: <br/>  2: true, wenn die Rolle Knoten verwalten kann. <br/>  4: true, wenn die Rolle untergeordnete Knoten erstellen kann. <br/>  7: true, wenn die Rolle einen Chatroom (oder untergeordnete Chatrooms einer Kategorie) teilnehmen kann. <br/>  8: true, wenn die Rolle in einem Chatroom (oder untergeordnete Chatrooms einer Kategorie) chatten kann. <br/>  10: true, wenn die Rolle den Chatverlauf, auch wenn nicht in einem Chatroom beigetreten lesen kann. <br/>  11: true, wenn die Rolle den Chatroom sehen kann. (Dies wird durch Faktoren beeinflusst, beispielsweise von Bereich und Sichtbarkeit weiterentwickelte.) <br/>  12: true, wenn die Rolle in einem auditoriumchatroom chatten kann. <br/>  13: true, wenn die Rolle beim Anzeigen von Knoten Sichtbarkeitsregeln umgehen kann. <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|rtypeID  <br/> |Primärschlüssel.  <br/> |
   

