---
title: Tabelle "FocusJoinsAndLeaves" in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e6f0212c-67e9-4061-8720-d0296e855991
description: Jeder Datensatz in dieser Tabelle enthält die Informationen zu den Teilnahme- und Ausgängen eines Benutzers für eine Konferenz. Jede Konferenz wird in dieser Tabelle durch einen Datensatz für jedes Mal dargestellt, wenn ein Benutzer der Konferenz beitritt und sie verlässt.
ms.openlocfilehash: ea3af4da259fe4186a3fa3937fd2977779dafeaa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821625"
---
# <a name="focusjoinsandleaves-table-in-skype-for-business-server-2015"></a>Tabelle "FocusJoinsAndLeaves" in Skype for Business Server 2015
 
Jeder Datensatz in dieser Tabelle enthält die Informationen zu den Teilnahme- und Ausgängen eines Benutzers für eine Konferenz. Jede Konferenz wird in dieser Tabelle durch einen Datensatz für jedes Mal dargestellt, wenn ein Benutzer der Konferenz beitritt und sie verlässt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datum/Uhrzeit  <br/> |Primär, Fremd  <br/> |Zeitpunkt der Konferenzinstanz. Wird in Verbindung mit **SessionIdSeq verwendet,** um eine Konferenzinstanz eindeutig zu identifizieren. Weitere Informationen finden Sie in der [Tabelle "Konferenzen" in Skype for Business Server 2015.](conferences.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primär, Fremd  <br/> |ID zur Identifikation der Konferenzinstanz. Wird in Verbindung mit **SessionIdTime verwendet,** um eine Konferenzinstanz eindeutig zu identifizieren. Weitere Informationen finden Sie in der [Tabelle "Konferenzen" in Skype for Business Server 2015.](conferences.md) <br/> |
|**DialogSessionIdTime** <br/> |Datum/Uhrzeit  <br/> |Primär, Fremd  <br/> |Zeitpunkt der Sitzungsanforderung. Wird zusammen mit **SessionIdSeq** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen [finden Sie in der Tabelle "Dialogfelder" in Skype for Business Server 2015.](dialogs.md) <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Primär, Fremd  <br/> |ID zur Identifikation der Sitzung. Wird zusammen mit **SessionIdTime** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen [finden Sie in der Tabelle "Dialogfelder" in Skype for Business Server 2015.](dialogs.md) <br/> |
|**UserId** <br/> |int  <br/> |Fremd  <br/> |Eindeutige Nummer, die diesen Benutzer identifiziert, auf die in der Tabelle ["Benutzer" verwiesen wird.](users.md)  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||Wenn ein Benutzer auf mehreren Computern oder Geräten gleichzeitig angemeldet ist, wird **UserInstance** verwendet, um die Kombination aus Benutzer und Gerät eindeutig zu identifizieren. <br/> |
|**IsUserInternal** <br/> |bit  <br/> | <br/> |Gibt an, ob sich der Benutzer von intern aus angemeldet hat oder nicht.  <br/> |
|**UserRole** <br/> |int  <br/> | <br/> |Die Rolle dieses Benutzers in der Konferenz, z. B. Presenter oder Attendee.  <br/> |
|**UserJoinTime** <br/> |Datum/Uhrzeit  <br/> | <br/> |Der Zeitpunkt, zu dem dieser Benutzer der Konferenz beitritt.  <br/> |
|**UserLeaveTime** <br/> |Datum/Uhrzeit  <br/> | <br/> |Der Zeitpunkt, zu dem dieser Benutzer die Konferenz verlässt.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Fremd  <br/> |Version der Clientsoftware des Benutzers, referenziert auf die [Tabelle "ClientVersions" in Skype for Business Server 2015](clientversions.md).  <br/> |
|**UserEndpointId** <br/> |uniqueIdentifier  <br/> ||GUID (Globally Unique Identifier) des in der Konferenz verwendeten Endpunkts.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype for Business Server 2015 eingeführt.  <br/> |
   

