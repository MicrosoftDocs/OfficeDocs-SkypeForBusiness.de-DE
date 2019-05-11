---
title: FocusJoinsAndLeaves-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e6f0212c-67e9-4061-8720-d0296e855991
description: Jeder Datensatz in dieser Tabelle enthält die CDR Informationen zu einem Benutzer teilnehmen und Informationen für eine Konferenz verlassen. Jede Konferenz wird in dieser Tabelle durch einen Datensatz für jedes Mal dargestellt ein Benutzer teilnimmt und die Konferenz verlässt.
ms.openlocfilehash: 8767b72163be4b90fb06950d3eca33bbe9d9974c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901122"
---
# <a name="focusjoinsandleaves-table-in-skype-for-business-server-2015"></a>FocusJoinsAndLeaves-Tabelle in Skype für Business Server 2015
 
Jeder Datensatz in dieser Tabelle enthält die CDR Informationen zu einem Benutzer teilnehmen und Informationen für eine Konferenz verlassen. Jede Konferenz wird in dieser Tabelle durch einen Datensatz für jedes Mal dargestellt ein Benutzer teilnimmt und die Konferenz verlässt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primär, Fremd  <br/> |Zeitpunkt des Konferenz-Instanz. Zusammen mit **SessionIdSeq** verwendet zur eindeutigen Identifizierung eine Konferenz-Instanz. [Conferences-Tabelle in Skype für Business Server 2015](conferences.md) Weitere Informationen finden Sie. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primär, Fremd  <br/> |ID-Nummer zum Identifizieren der Konferenz-Instanz. In Verbindung mit **SessionIdTime** verwendet, um eine Instanz der Konferenz eindeutig zu identifizieren. [Conferences-Tabelle in Skype für Business Server 2015](conferences.md) Weitere Informationen finden Sie. <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Primär, Fremd  <br/> |Zeitpunkt der sitzungsanforderung. Zusammen mit **SessionIdSeq** verwendet zur eindeutigen Identifizierung eine Sitzung. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Primär, Fremd  <br/> |ID-Nummer, um die Sitzung zu identifizieren. In Verbindung mit **SessionIdTime** verwendet, um eine Sitzung eindeutig zu identifizieren. finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**Benutzer-ID** <br/> |int  <br/> |Ausländisch  <br/> |Eindeutige Zahl, die diesen Benutzer wird aus der [Tabelle Benutzer](users.md)identifiziert.  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||Wenn ein Benutzer auf mehreren Computern oder Geräten gleichzeitig angemeldet ist, wird **UserInstance** verwendet, um die Benutzer/Geräte-Kombination eindeutig zu identifizieren. <br/> |
|**IsUserInternal** <br/> |bit  <br/> | <br/> |Gibt an, ob der Benutzer von innerhalb oder nicht angemeldet.  <br/> |
|**UserRole** <br/> |int  <br/> | <br/> |Die Rolle des Benutzers bei der Konferenz, wie etwa Referent oder Teilnehmer.  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |Die Zeit, die dieser Benutzer die Konferenz beitritt.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |Der Zeitpunkt, zu dem dieser Benutzer die Konferenz verlässt.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Ausländisch  <br/> |Version der Clientsoftware des Benutzers, auf die [ClientVersions-Tabelle in Skype für Business Server 2015](clientversions.md)verwiesen wird.  <br/> |
|**UserEndpointId** <br/> |uniqueIdentifier  <br/> ||Global eindeutigen Bezeichner (GUID) des in der Konferenz verwendeten Endpunkts.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ZuletztGeändertUm** <br/> |DateTime  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype für Business Server 2015 eingeführt.  <br/> |
   

