---
title: tblNode
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a31d2961-aa83-4286-a12e-15d279c95f19
description: "\"TblNode\" enthält die Objektstruktur (mit Kategorie oder Chatroom-Knoten) wie in der Systemsteuerung und administrativen Cmdlets verwaltet."
ms.openlocfilehash: 333ea267c4e65f20d5c4dd15f115b40ec162e209
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929833"
---
# <a name="tblnode"></a>tblNode
 
"TblNode" enthält die Objektstruktur (mit Kategorie oder Chatroom-Knoten) wie in der Systemsteuerung und administrativen Cmdlets verwaltet.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|nodeID  <br/> |Int, nicht null  <br/> |Knoten-ID (eindeutige Nummer).  <br/> |
|nodeGuid  <br/> |GUID, nicht null  <br/> |Knoten-GUID.  <br/> |
|parentID  <br/> |int  <br/> |Knoten-ID des übergeordneten Elements. Den Stammknoten (wobei ID 1), die selbst als auch das übergeordnete enthält.  <br/> |
|nodeType  <br/> |Bit, nicht null  <br/> |True, wenn der Knoten eine Kategorie ist.  <br/> False, wenn der Knoten ein Chatroom ist.  <br/> |
|Knotenname  <br/> |Nvarchar (256), nicht null  <br/> |Name des Knotens.  <br/> |
|nodeDesc  <br/> |Nvarchar (256), nicht null  <br/> |Beschreibung des Knotens.  <br/> |
|einladen  <br/> |bit  <br/> | Für Kategorien: <br/>  True, wenn Einladungen aktiviert sind. <br/>  False, wenn Einladungen deaktiviert sind. <br/>  Für Räume: <br/>  "False" Wenn Einladungen deaktiviert sind (überschreibt die übergeordnete Kategorie). <br/>  NULL, wenn die Einstellung zum Einladen von der übergeordneten Kategorie geerbt wird. <br/> |
|protokolliert  <br/> |bit  <br/> | Für Kategorien: <br/>  True, wenn der Chatverlauf aktiviert ist. <br/>  False, wenn der Chatverlauf deaktiviert ist. <br/>  Für Räume: <br/>  NULL. <br/> |
|filePost  <br/> |bit  <br/> | Für Kategorien: <br/>  True, wenn Dateiuploads zugelassen sind. <br/>  False, wenn Dateiuploads nicht zugelassen sind. <br/>  Für Räume: <br/>  NULL. <br/> |
|deaktiviert  <br/> |Bit, nicht null  <br/> |True, wenn Sie den Chatroom deaktiviert ist. Gilt nur für Chatrooms. (False für Kategorien).  <br/> |
|Verhalten  <br/> |Smallint, nicht null  <br/> | Verhalten (in der Tabelle "EnumValue" ermittelt): <br/>  4: Normal (normale Chatrooms). <br/>  5: Auditorium (auditoriumchatrooms, nur Referenten können Beiträge veröffentlichen). <br/>  Gilt nur für Chatrooms. <br/> |
|Sichtbarkeit  <br/> |Smallint, nicht null  <br/> | Sichtbarkeit (für Tabelle "EnumValue" ermittelt): <br/>  2: private <br/>  3: bezogenen <br/>  6: Öffnen <br/>  Gilt nur für Chatrooms. <br/> |
|siopID  <br/> |GUID  <br/> |Add-in-GUID, wenn ein Add-in in Chatrooms zugeordnet ist. (Kategorien haben keinen-add-ins.)  <br/> Die Add-in-Informationen in der Tabelle "SiopWhiteList" gesucht werden.  <br/> |
|nodeAddedBy  <br/> |Int, nicht null  <br/> |ID des Prinzipals, der diesen Knoten erstellt hat.  <br/> |
|nodeAddedOn  <br/> |Bigint, nicht null  <br/> |Zeitstempel der knotenerstellung.  <br/> |
|nodeUpdatedBy  <br/> |Int, nicht null  <br/> |ID des Prinzipals, der das neueste Update dieses Knotens haben.  <br/> |
|nodeUpdatedOn  <br/> |Bigint, nicht null  <br/> |Zeitstempel der letzten Aktualisierung dieses Knotens.  <br/> |
|purgedOn  <br/> |datetime  <br/> |Zeit den neuesten Aufräumvorgang (zum Entfernen von Bereichen aus TblScopedPrincipal Tabelle und Rollen aus der TblPrincipalRole-Tabelle), die diesem Knoten betroffen. Dies wird von der Chat-Dienst internen Cache Updatemechanismus verwendet.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|nodeID  <br/> |Primärschlüssel.  <br/> |
|Verhalten  <br/> |Fremdschlüssel mit Abfrage der Tabelle "tblenumvalue.ValueID".  <br/> |
|Sichtbarkeit  <br/> |Fremdschlüssel mit Abfrage der Tabelle "tblenumvalue.ValueID".  <br/> |
|parentID  <br/> |Fremdschlüssel mit Abfrage der tblNode.nodeID-Tabelle.  <br/> |
|siopID  <br/> |Fremdschlüssel mit Abfrage der Tabelle "tblsiopwhitelist.siopid".  <br/> |
   

