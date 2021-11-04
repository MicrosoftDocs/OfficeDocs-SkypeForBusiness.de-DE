---
title: tblNode
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: a31d2961-aa83-4286-a12e-15d279c95f19
description: tblNode enthält die Objektstruktur (mit Kategorie- oder Chatroomknoten), wie sie in der Systemsteuerung und in administrativen Cmdlets verwaltet wird.
ms.openlocfilehash: 0935e5cdec8db7f7ce33b07dcf287c1a8bd5d749
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776145"
---
# <a name="tblnode"></a>tblNode
 
tblNode enthält die Objektstruktur (mit Kategorie- oder Chatroomknoten), wie sie in der Systemsteuerung und in administrativen Cmdlets verwaltet wird.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, not null  <br/> |Knoten-ID (eindeutige Nummer).  <br/> |
|nodeGuid  <br/> |GUID, nicht NULL  <br/> |Knoten-GUID.  <br/> |
|Parentid  <br/> |int  <br/> |Knoten-ID des übergeordneten Elements. Der Stammknoten (mit ID 1) gilt selbst als übergeordnetes Element.  <br/> |
|Nodetype  <br/> |bit, not null  <br/> |"True" wenn der Knoten eine Kategorie ist.  <br/> "False" wenn der Knoten ein Chatroom ist.  <br/> |
|nodeName  <br/> |nvarchar (256), not null  <br/> |Knotenname  <br/> |
|nodeDesc  <br/> |nvarchar (256), not null  <br/> |Knotenbeschreibung.  <br/> |
|invite  <br/> |Bit  <br/> | Für Kategorien: <br/>  "True" wenn Einladungen aktiviert sind. <br/>  "False" wenn Einladungen deaktiviert sind. <br/>  Für Räume: <br/>  "False", wenn Einladungen deaktiviert sind (überschreibt die übergeordnete Kategorie). <br/>  "Null" wenn die Einstellung zum Einladen von der übergeordneten Kategorie geerbt wird. <br/> |
|Protokolliert  <br/> |Bit  <br/> | Für Kategorien: <br/>  "True" wenn der Chatverlauf aktiviert ist. <br/>  "False" wenn der Chatverlauf deaktiviert ist. <br/>  Für Räume: <br/>  Null. <br/> |
|filePost  <br/> |Bit  <br/> | Für Kategorien: <br/>  "True" wenn Dateiuploads zugelassen sind. <br/>  "False" wenn Dateiuploads nicht zugelassen sind. <br/>  Für Räume: <br/>  Null. <br/> |
|deaktiviert  <br/> |bit, not null  <br/> |"True" wenn der Chatroom deaktiviert ist. Trifft nur auf Chatrooms zu. ("False" für Kategorien.)  <br/> |
|Verhalten  <br/> |smallint, not null  <br/> | Verhalten (in der Tabelle "EnumValue" ermittelt): <br/>  4: Normal (normale Chatrooms) <br/>  5: Auditorium (Auditoriumchatrooms, nur Referenten können Beiträge veröffentlichen). <br/>  Trifft nur auf Chatrooms zu. <br/> |
|visibility  <br/> |smallint, nicht NULL  <br/> | Sichtbarkeit (in der Tabelle "EnumValue" ermittelt): <br/>  2: Privat <br/>  3: Bereich <br/>  6: Offen <br/>  Trifft nur auf Chatrooms zu. <br/> |
|siopID  <br/> |GUID  <br/> |Add-In-GUID, falls diesem Chatroom ein Add-In zugeordnet ist. (Kategorien sind keine Add-Ins zugeordnet.)  <br/> Die Add-In-Informationen werden in der Tabelle "SiopWhiteList" gesucht.  <br/> |
|nodeAddedBy  <br/> |int, not null  <br/> |ID des Prinzipals, der diesen Knoten erstellt hat.  <br/> |
|nodeAddedOn  <br/> |bigint, not null  <br/> |Zeitstempel der Knotenerstellung.  <br/> |
|nodeUpdatedBy  <br/> |int, not null  <br/> |ID des Prinzipals, der die letzte Aktualisierung dieses Knotens vorgenommen hat.  <br/> |
|nodeUpdatedOn  <br/> |bigint, not null  <br/> |Zeitstempel der letzten Aktualisierung dieses Knotens.  <br/> |
|purgedOn  <br/> |Datum/Uhrzeit  <br/> |Zeitpunkt des letzten Löschvorgangs (Entfernung von Bereichen aus der Tabelle "tblScopedPrincipal" und Rollen aus der Tabelle "tblPrincipalRole"), der Auswirkungen auf diesen Knoten hatte. Dies wird vom internen Cacheaktualisierungsmechanismus des Chatdiensts verwendet.  <br/> |
   
**Keys**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|nodeID  <br/> |Primärschlüssel  <br/> |
|Verhalten  <br/> |Fremdschlüssel mit Suche in der Tabelle "tblEnumValue.valueID".  <br/> |
|visibility  <br/> |Fremdschlüssel mit Suche in der Tabelle "tblEnumValue.valueID".  <br/> |
|Parentid  <br/> |Fremdschlüssel mit Suche in der Tabelle "tblNode.nodeID".  <br/> |
|siopID  <br/> |Fremdschlüssel mit Suche in der Tabelle "tblSiopWhiteList.siopId".  <br/> |
   

