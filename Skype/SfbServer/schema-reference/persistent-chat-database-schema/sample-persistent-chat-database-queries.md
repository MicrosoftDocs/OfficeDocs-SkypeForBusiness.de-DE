---
title: Beispieldatenbankabfragen für beständigen Chat
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
description: Dieser Abschnitt enthält Beispielabfragen für die Datenbank für beständigen Chat.
ms.openlocfilehash: 74cb6c1029cdeaabcd74a34898731b44c71f05a7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823105"
---
# <a name="sample-persistent-chat-database-queries"></a>Beispieldatenbankabfragen für beständigen Chat
 
Dieser Abschnitt enthält Beispielabfragen für die Datenbank für beständigen Chat.
  
Verwenden Sie das folgende Beispiel, um eine Liste der aktivsten Chatrooms für beständigen Chat nach einem bestimmten Datum zu erhalten.
  
```SQL
SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
  FROM tblChat, tblNode
  WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY nodeName
  ORDER BY ChatMessages DESC
```

Mithilfe des folgenden Beispiels können Sie eine Liste der aktivsten Benutzer nach einem bestimmten Datum abrufen.
  
```SQL
SELECT prinName as Name, count(*) as ChatMessages
  FROM tblChat, tblPrincipal
  WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY prinName
  ORDER BY ChatMessages DESC
```

Mithilfe des folgenden Beispiels können Sie eine Liste aller Benutzer abrufen, die jemals eine Nachricht mit "Hello World" gesendet haben.
  
```SQL
SELECT nodeName as ChatRoom, prinName as Name, content as Message
  FROM tblChat, tblNode, tblPrincipal
  WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'
```

Mithilfe des folgenden Beispiels können Sie eine Liste der Gruppenmitgliedschaften für einen bestimmten Prinzipal abrufen.
  
```SQL
SELECT prinName as Name    
  FROM tblPrincipalAffiliations as pa, tblPrincipal
  where principalID = 7 and affiliationID = prinID
```

Mithilfe des folgenden Beispiels können Sie eine Liste aller Chatrooms abrufen, in denen der Benutzer "Jane Dow" direktes Mitglied ist.
  
```SQL
SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
  FROM tblPrincipalRole, tblPrincipal, tblNode
  WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'
```

Mithilfe des folgenden Beispiels können Sie eine Liste der empfangenen Einladungen eines Benutzers abrufen.
  
```SQL
SELECT prinName
      ,nodeName
      ,invID   
      ,createdOn
  FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
  where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
  ORDER BY invID DESC
```
