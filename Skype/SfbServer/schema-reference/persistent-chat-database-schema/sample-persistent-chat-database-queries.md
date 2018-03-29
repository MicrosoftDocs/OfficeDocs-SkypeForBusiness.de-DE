---
title: Beispieldatenbankabfragen für beständigen Chat
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
description: Dieser Abschnitt enthält Beispielabfragen für die Datenbank für beständigen Chat.
ms.openlocfilehash: 1e2d457a31061dcfb3c332a067069cbd4a8a9ebd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="sample-persistent-chat-database-queries"></a><span data-ttu-id="1de73-103">Beispieldatenbankabfragen für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="1de73-103">Sample Persistent Chat database queries</span></span>
 
<span data-ttu-id="1de73-104">Dieser Abschnitt enthält Beispielabfragen für die Datenbank für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="1de73-104">This section contains sample queries for the Persistent Chat database.</span></span>
  
<span data-ttu-id="1de73-105">Mithilfe des folgenden Beispiels können Sie eine Liste der aktivsten beständigen Chat Rooms nach einem bestimmten Datum abrufen.</span><span class="sxs-lookup"><span data-stu-id="1de73-105">Use the following example to get a list of your most active Persistent Chat rooms after a certain date.</span></span>
  
```
SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
  FROM tblChat, tblNode
  WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY nodeName
  ORDER BY ChatMessages DESC

```

<span data-ttu-id="1de73-106">Verwenden Sie das folgende Beispiel, um eine Liste der aktivsten Benutzer nach einem bestimmten Datum abrufen.</span><span class="sxs-lookup"><span data-stu-id="1de73-106">Use the following example to get a list of your most active users after a certain date.</span></span>
  
```
SELECT prinName as Name, count(*) as ChatMessages
  FROM tblChat, tblPrincipal
  WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY prinName
  ORDER BY ChatMessages DESC

```

<span data-ttu-id="1de73-107">Verwenden Sie das folgende Beispiel zum Abrufen einer Liste aller Benutzer, die jemals eine Nachricht mit "Hello World" gesendet.</span><span class="sxs-lookup"><span data-stu-id="1de73-107">Use the following example to get a list of everyone who ever sent a message with "Hello World" in it.</span></span>
  
```
SELECT nodeName as ChatRoom, prinName as Name, content as Message
  FROM tblChat, tblNode, tblPrincipal
  WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'
```

<span data-ttu-id="1de73-108">Verwenden Sie das folgende Beispiel, um eine Liste der Gruppenmitgliedschaften für einen bestimmten Prinzipal abrufen.</span><span class="sxs-lookup"><span data-stu-id="1de73-108">Use the following example to get a list of group memberships for a certain principal.</span></span>
  
```
SELECT prinName as Name    
  FROM tblPrincipalAffiliations as pa, tblPrincipal
  where principalID = 7 and affiliationID = prinID
```

<span data-ttu-id="1de73-109">Verwenden Sie im folgenden Beispiel wird eine Liste aller Chatrooms abrufen, die ein Benutzer, Jane Dow, direktes Mitglied ist.</span><span class="sxs-lookup"><span data-stu-id="1de73-109">Use the following example to get a list of every chat room that a user, Jane Dow, is a direct member of.</span></span>
  
```
SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
  FROM tblPrincipalRole, tblPrincipal, tblNode
  WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'
```

<span data-ttu-id="1de73-110">Verwenden Sie im folgenden Beispiel wird eine Liste von Einladungen abrufen, die ein Benutzer erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="1de73-110">Use the following example to get a list of invitations that a user has received.</span></span>
  
```
SELECT prinName
      ,nodeName
      ,invID   
      ,createdOn
  FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
  where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
  ORDER BY invID DESC
```


