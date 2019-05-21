---
title: tblNode
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a31d2961-aa83-4286-a12e-15d279c95f19
description: tblNode enthält die Objektstruktur (mit Kategorien-oder Chatroom-Knoten), wie Sie in der Systemsteuerung und den administrativen Cmdlets verwaltet werden.
ms.openlocfilehash: fedb7f88cd9b5a634fe9a6b34f746e61e6ee9be7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295349"
---
# <a name="tblnode"></a>tblNode
 
tblNode enthält die Objektstruktur (mit Kategorien-oder Chatroom-Knoten), wie Sie in der Systemsteuerung und den administrativen Cmdlets verwaltet werden.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, nicht NULL  <br/> |Knoten-ID (eindeutige Nummer).  <br/> |
|nodeGuid  <br/> |GUID, nicht NULL  <br/> |Knoten-GUID.  <br/> |
|parentID  <br/> |int  <br/> |Knoten-ID des übergeordneten Elements. Der Stammknoten (mit ID 1) schließt sich ebenfalls als übergeordnetes Element ein.  <br/> |
|NodeType  <br/> |Bit, nicht NULL  <br/> |"True", wenn der Knoten eine Kategorie ist.  <br/> False, wenn es sich bei dem Knoten um einen Chatroom handelt.  <br/> |
|nodeName  <br/> |nvarchar (256); nicht NULL  <br/> |Knotenname  <br/> |
|nodeDesc  <br/> |nvarchar (256); nicht NULL  <br/> |Knotenbeschreibung.  <br/> |
|einladen  <br/> |bit  <br/> | Für Kategorien: <br/>  True, wenn Einladungen aktiviert sind. <br/>  False, wenn Einladungen deaktiviert sind. <br/>  Für Räume: <br/>  False, wenn Einladungen deaktiviert sind (überschreibt die übergeordnete Kategorie). <br/>  NULL, wenn die invites-Einstellung von der übergeordneten Kategorie geerbt wird. <br/> |
|angemeldet  <br/> |bit  <br/> | Für Kategorien: <br/>  "True", wenn das Chat-Protokoll aktiviert ist. <br/>  Falsch, wenn das Chat-Protokoll deaktiviert ist. <br/>  Für Räume: <br/>  NULL. <br/> |
|filePost  <br/> |bit  <br/> | Für Kategorien: <br/>  "True", wenn Dateiuploads zulässig sind. <br/>  False, wenn Dateiuploads nicht zulässig sind. <br/>  Für Räume: <br/>  NULL. <br/> |
|deaktiviert  <br/> |Bit, nicht NULL  <br/> |"True", wenn der Chatroom deaktiviert ist. Gilt nur für Chatrooms. (Falsch für Kategorien.)  <br/> |
|Verhalten  <br/> |smallint, nicht NULL  <br/> | Verhalten (in der EnumValue-Tabelle nachgeschlagen): <br/>  4: Normal (normale Chatrooms). <br/>  5: Auditorium (Auditorium-Chatrooms, nur Referenten können dazu beitragen). <br/>  Gilt nur für Chatrooms. <br/> |
|Sichtbarkeit  <br/> |smallint, nicht NULL  <br/> | Sichtbarkeit (in der EnumValue-Tabelle nachgeschlagen): <br/>  2: privat <br/>  3: Gültigkeitsbereich <br/>  6: Öffnen <br/>  Gilt nur für Chatrooms. <br/> |
|siopID  <br/> |GUID  <br/> |Add-in-GUID, wenn diesem Chatroom ein Add-in zugeordnet ist. (Kategorien verfügen nicht über Add-Ins.)  <br/> Die Add-in-Informationen werden in der SiopWhiteList-Tabelle nachgeschlagen.  <br/> |
|nodeAddedBy  <br/> |int, nicht NULL  <br/> |Die ID des Prinzipals, der diesen Knoten erstellt hat.  <br/> |
|nodeAddedOn  <br/> |bigint, nicht NULL  <br/> |Zeitstempel der Knotenerstellung.  <br/> |
|nodeUpdatedBy  <br/> |int, nicht NULL  <br/> |Die ID des Prinzipals, der das neueste Update dieses Knotens durchführte.  <br/> |
|nodeUpdatedOn  <br/> |bigint, nicht NULL  <br/> |Zeitstempel der letzten Aktualisierung dieses Knotens.  <br/> |
|purgedOn  <br/> |datetime  <br/> |Zeitpunkt des letzten Aufräumvorgangs (Entfernen von Bereichen aus tblScopedPrincipal-Tabelle und Rollen aus der tblPrincipalRole-Tabelle), die diesen Knoten betroffen haben. Dieser wird vom internen Cache Aktualisierungsmechanismus des Chat Diensts verwendet.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|nodeID  <br/> |Primärschlüssel  <br/> |
|Verhalten  <br/> |Fremdschlüssel mit Lookup in der Tabelle "tblEnumValue. Wert".  <br/> |
|Sichtbarkeit  <br/> |Fremdschlüssel mit Lookup in der Tabelle "tblEnumValue. Wert".  <br/> |
|parentID  <br/> |Fremdschlüssel mit Lookup in der tblNode. Node-Tabelle  <br/> |
|siopID  <br/> |Fremdschlüssel mit Lookup in der tblSiopWhiteList. siopId-Tabelle.  <br/> |
   

