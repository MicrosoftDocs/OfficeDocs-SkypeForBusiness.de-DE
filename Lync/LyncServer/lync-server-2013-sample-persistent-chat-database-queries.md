---
title: 'Lync Server 2013: Beispieldatenbankabfragen für beständigen Chat'
TOCTitle: Beispieldatenbankabfragen für beständigen Chat
ms:assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558649(v=OCS.15)
ms:contentKeyID: 49294025
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Beispieldatenbankabfragen für beständigen Chat für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-06_

Dieser Abschnitt enthält Beispielabfragen für die Beständiger Chatdatenbank.

Mithilfe des folgenden Beispiels können Sie eine Liste der aktivsten Beständiger Chatrooms nach einem bestimmten Datum abrufen.

    SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
      FROM tblChat, tblNode
      WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
      GROUP BY nodeName
      ORDER BY ChatMessages DESC

Mithilfe des folgenden Beispiels können Sie eine Liste der aktivsten Benutzer nach einem bestimmten Datum abrufen.

    SELECT prinName as Name, count(*) as ChatMessages
      FROM tblChat, tblPrincipal
      WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
      GROUP BY prinName
      ORDER BY ChatMessages DESC

Mithilfe des folgenden Beispiels können Sie eine Liste aller Benutzer abrufen, die jemals eine Nachricht mit "Hello World" gesendet haben.

    SELECT nodeName as ChatRoom, prinName as Name, content as Message
      FROM tblChat, tblNode, tblPrincipal
      WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'

Mithilfe des folgenden Beispiels können Sie eine Liste der Gruppenmitgliedschaften für einen bestimmten Prinzipal abrufen.

    SELECT prinName as Name    
      FROM tblPrincipalAffiliations as pa, tblPrincipal
      where principalID = 7 and affiliationID = prinID

Mithilfe des folgenden Beispiels können Sie eine Liste aller Chatrooms abrufen, in denen der Benutzer "Jane Dow" direktes Mitglied ist.

    SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
      FROM tblPrincipalRole, tblPrincipal, tblNode
      WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'

Mithilfe des folgenden Beispiels können Sie eine Liste der empfangenen Einladungen eines Benutzers abrufen.

    SELECT prinName
          ,nodeName
          ,invID   
          ,createdOn
      FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
      where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
      ORDER BY invID DESC

