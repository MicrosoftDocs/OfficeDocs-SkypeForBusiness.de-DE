---
title: FocusJoinsAndLeaves-Tabelle in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e6f0212c-67e9-4061-8720-d0296e855991
description: Jeder Datensatz in dieser Tabelle enthält die CDR-Informationen zu den Join-und Leave-Informationen eines Benutzers für eine Konferenz. Jede Konferenz wird in dieser Tabelle für jedes Mal, wenn ein Benutzer mit der Konferenz verbunden ist, mit einem Datensatz dargestellt.
ms.openlocfilehash: 4eb9f6300613fb61a7173be547aa83adf61d1026
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296210"
---
# <a name="focusjoinsandleaves-table-in-skype-for-business-server-2015"></a>FocusJoinsAndLeaves-Tabelle in Skype for Business Server 2015
 
Jeder Datensatz in dieser Tabelle enthält die CDR-Informationen zu den Join-und Leave-Informationen eines Benutzers für eine Konferenz. Jede Konferenz wird in dieser Tabelle für jedes Mal, wenn ein Benutzer mit der Konferenz verbunden ist, mit einem Datensatz dargestellt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionID** <br/> |datetime  <br/> |Primär, fremd  <br/> |Uhrzeit der Konferenz Instanz. Wird in Verbindung mit **SessionIdSeq** verwendet, um eine Konferenz Instanz eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle "Konferenzen" in Skype for Business Server 2015](conferences.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primär, fremd  <br/> |Die ID-Nummer zum Identifizieren der Konferenz Instanz. Wird in Verbindung mit **SessionID** -Mal verwendet, um eine Konferenz Instanz eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle "Konferenzen" in Skype for Business Server 2015](conferences.md) . <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Primär, fremd  <br/> |Uhrzeit der Sitzungsanforderung. Wird in Verbindung mit **SessionIdSeq** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Primär, fremd  <br/> |Die ID-Nummer, um die Sitzung zu identifizieren. Wird in Verbindung mit **SessionID** -Mal verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**UserID** <br/> |int  <br/> |Fremd  <br/> |Eindeutige Nummer, die diesen Benutzer identifiziert, auf die in der [Tabelle "Benutzer](users.md)" verwiesen wird.  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||Wenn ein Benutzer gleichzeitig an mehreren Computern oder Geräten angemeldet ist, wird **UserInstance** verwendet, um die Kombination aus Benutzer und Gerät eindeutig zu identifizieren. <br/> |
|**IsUserInternal** <br/> |bit  <br/> | <br/> |Ob sich der Benutzer intern angemeldet hat oder nicht.  <br/> |
|**UserRole** <br/> |int  <br/> | <br/> |Die Rolle dieses Benutzers in der Konferenz, beispielsweise Referent oder Teilnehmer.  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |Der Zeitpunkt, zu dem dieser Benutzer der Konferenz Beitritt.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |Der Zeitpunkt, zu dem dieser Benutzer die Konferenz verlässt.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Fremd  <br/> |Die Version der Client Software des Benutzers, auf die [in der Tabelle "ClientVersions" in Skype for Business Server 2015](clientversions.md)Bezug genommen wird.  <br/> |
|**UserEndpointId** <br/> |uniqueIdentifier  <br/> ||GUID (Globally Unique Identifier) des in der Konferenz verwendeten Endpunkts.  <br/> Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype for Business Server 2015 eingeführt.  <br/> |
   

