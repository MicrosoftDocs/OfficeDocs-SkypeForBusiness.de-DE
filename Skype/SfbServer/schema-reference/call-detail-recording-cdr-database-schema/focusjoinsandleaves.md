---
title: FocusJoinsAndLeaves-Tabelle in Skype for Business Server 2015
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
description: Jeder Datensatz in dieser Tabelle enthält die KDS-Informationen über die Teilnahme- und Leave-Informationen eines Benutzers für eine Konferenz. Jede Konferenz wird in dieser Tabelle jeweils durch einen Datensatz dargestellt, wenn ein Benutzer der Konferenz beitritt und diese verlässt.
ms.openlocfilehash: 879c4df8dce048820e2d1a23f62ff5c7070611a7e0331cb496a50363aa98f3b9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54352084"
---
# <a name="focusjoinsandleaves-table-in-skype-for-business-server-2015"></a>FocusJoinsAndLeaves-Tabelle in Skype for Business Server 2015
 
Jeder Datensatz in dieser Tabelle enthält die KDS-Informationen über die Teilnahme- und Leave-Informationen eines Benutzers für eine Konferenz. Jede Konferenz wird in dieser Tabelle jeweils durch einen Datensatz dargestellt, wenn ein Benutzer der Konferenz beitritt und diese verlässt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datum/Uhrzeit  <br/> |Primär, Fremd  <br/> |Zeitpunkt der Konferenzinstanz. Wird in Verbindung mit **SessionIdSeq** verwendet, um eine Konferenzinstanz eindeutig zu identifizieren. Weitere Informationen finden Sie in der [Tabelle "Konferenzen" in Skype for Business Server 2015.](conferences.md) <br/> |
|**SessionIdSeq** <br/> |Ganzzahl  <br/> |Primär, Fremd  <br/> |ID zur Identifikation der Konferenzinstanz. Wird in Verbindung mit **SessionIdTime** verwendet, um eine Konferenzinstanz eindeutig zu identifizieren. Weitere Informationen finden Sie in der [Tabelle "Konferenzen" in Skype for Business Server 2015.](conferences.md) <br/> |
|**DialogSessionIdTime** <br/> |Datum/Uhrzeit  <br/> |Primär, Fremd  <br/> |Zeitpunkt der Sitzungsanforderung. Wird zusammen mit **SessionIdSeq** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie in der [Dialogs-Tabelle in Skype for Business Server 2015.](dialogs.md) <br/> |
|**DialogSessionIdSeq** <br/> |Ganzzahl  <br/> |Primär, Fremd  <br/> |ID zur Identifikation der Sitzung. Wird zusammen mit **SessionIdTime** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie in der [Dialogs-Tabelle in Skype for Business Server 2015.](dialogs.md) <br/> |
|**UserId** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |Eindeutige Nummer, die diesen Benutzer identifiziert, auf die in der [Tabelle "Benutzer"](users.md)verwiesen wird.  <br/> |
|**FocusUserInstance** <br/> |Ganzzahl  <br/> ||Wenn ein Benutzer gleichzeitig auf mehreren Computern oder Geräten angemeldet ist, wird **UserInstance** verwendet, um die Kombination aus Benutzer und Gerät eindeutig zu identifizieren. <br/> |
|**IsUserInternal** <br/> |Bit  <br/> | <br/> |Gibt an, ob sich der Benutzer intern angemeldet hat oder nicht.  <br/> |
|**Userrole** <br/> |Ganzzahl  <br/> | <br/> |Die Rolle dieses Benutzers in der Konferenz, z. B. Referent oder Teilnehmer.  <br/> |
|**UserJoinTime** <br/> |Datum/Uhrzeit  <br/> | <br/> |Der Zeitpunkt, an dem dieser Benutzer der Konferenz beitritt.  <br/> |
|**UserLeaveTime** <br/> |Datum/Uhrzeit  <br/> | <br/> |Der Zeitpunkt, zu dem dieser Benutzer die Konferenz verlässt.  <br/> |
|**ClientVerId** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |Version der Clientsoftware des Benutzers, auf die [in Skype for Business Server 2015 auf die Tabelle "ClientVersions"](clientversions.md)verwiesen wird.  <br/> |
|**UserEndpointId** <br/> |Uniqueidentifier  <br/> ||GUID (Globally Unique Identifier) des endpunkts, der in der Konferenz verwendet wird.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype for Business Server 2015 eingeführt.  <br/> |
   

