---
title: Beispieldatenbankabfragen für beständigen Chat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
description: Dieser Abschnitt enthält Beispielabfragen für die Datenbank des beständigen Chats.
ms.openlocfilehash: fef40c2f36547fb0772d2e938bf8259246ec2055
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295608"
---
# <a name="sample-persistent-chat-database-queries"></a><span data-ttu-id="8f162-103">Beispieldatenbankabfragen für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="8f162-103">Sample Persistent Chat database queries</span></span>
 
<span data-ttu-id="8f162-104">Dieser Abschnitt enthält Beispielabfragen für die Datenbank des beständigen Chats.</span><span class="sxs-lookup"><span data-stu-id="8f162-104">This section contains sample queries for the Persistent Chat database.</span></span>
  
<span data-ttu-id="8f162-105">Verwenden Sie das folgende Beispiel, um nach einem bestimmten Datum eine Liste Ihrer aktivsten beständigen Chatrooms abzurufen.</span><span class="sxs-lookup"><span data-stu-id="8f162-105">Use the following example to get a list of your most active Persistent Chat rooms after a certain date.</span></span>
  
```
SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
  FROM tblChat, tblNode
  WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY nodeName
  ORDER BY ChatMessages DESC
```

<span data-ttu-id="8f162-106">Verwenden Sie das folgende Beispiel, um nach einem bestimmten Datum eine Liste Ihrer aktivsten Benutzer abzurufen.</span><span class="sxs-lookup"><span data-stu-id="8f162-106">Use the following example to get a list of your most active users after a certain date.</span></span>
  
```
SELECT prinName as Name, count(*) as ChatMessages
  FROM tblChat, tblPrincipal
  WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY prinName
  ORDER BY ChatMessages DESC
```

<span data-ttu-id="8f162-107">Verwenden Sie das folgende Beispiel, um eine Liste aller Personen abzurufen, die jemals eine Nachricht mit "Hello World" gesendet haben.</span><span class="sxs-lookup"><span data-stu-id="8f162-107">Use the following example to get a list of everyone who ever sent a message with "Hello World" in it.</span></span>
  
```
SELECT nodeName as ChatRoom, prinName as Name, content as Message
  FROM tblChat, tblNode, tblPrincipal
  WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'
```

<span data-ttu-id="8f162-108">Verwenden Sie das folgende Beispiel, um eine Liste der Gruppenmitgliedschaften für einen bestimmten Prinzipal abzurufen.</span><span class="sxs-lookup"><span data-stu-id="8f162-108">Use the following example to get a list of group memberships for a certain principal.</span></span>
  
```
SELECT prinName as Name    
  FROM tblPrincipalAffiliations as pa, tblPrincipal
  where principalID = 7 and affiliationID = prinID
```

<span data-ttu-id="8f162-109">Verwenden Sie das folgende Beispiel, um eine Liste aller Chatrooms abzurufen, bei denen ein Benutzer, Jane Dow, ein direktes Mitglied ist.</span><span class="sxs-lookup"><span data-stu-id="8f162-109">Use the following example to get a list of every chat room that a user, Jane Dow, is a direct member of.</span></span>
  
```
SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
  FROM tblPrincipalRole, tblPrincipal, tblNode
  WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'
```

<span data-ttu-id="8f162-110">Verwenden Sie das folgende Beispiel, um eine Liste der Einladungen abzurufen, die ein Benutzer erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="8f162-110">Use the following example to get a list of invitations that a user has received.</span></span>
  
```
SELECT prinName
      ,nodeName
      ,invID   
      ,createdOn
  FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
  where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
  ORDER BY invID DESC
```
