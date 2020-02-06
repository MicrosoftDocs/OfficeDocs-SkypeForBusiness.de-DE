---
title: FocusJoinsAndLeaves-Ansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 226460ef-766f-4d61-80cb-f332b65a210d
description: In der FocusJoinsAndLeaves-Ansicht werden Informationen zu Join-und Leave-Informationen für eine Konferenz gespeichert. Jede Konferenz wird in dieser Ansicht durch einen Datensatz dargestellt, der jedes Mal geschrieben wird, wenn ein Benutzer eine Konferenz anschließt und verlässt. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 771685a5546ef5b462a3ce3955406eb535f4c3eb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815193"
---
# <a name="focusjoinsandleaves-view"></a>FocusJoinsAndLeaves-Ansicht
 
In der FocusJoinsAndLeaves-Ansicht werden Informationen zu Join-und Leave-Informationen für eine Konferenz gespeichert. Jede Konferenz wird in dieser Ansicht durch einen Datensatz dargestellt, der jedes Mal geschrieben wird, wenn ein Benutzer eine Konferenz anschließt und verlässt. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**SessionID** <br/> |datetime  <br/> |Uhrzeit der Konferenz Instanz. Wird in Verbindung mit SessionIdSeq verwendet, um eine Konferenz Instanz eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle "Konferenzen" in Skype for Business Server 2015](conferences.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Die ID-Nummer zum Identifizieren der Konferenz Instanz. Wird in Verbindung mit SessionID-Mal verwendet, um eine Konferenz Instanz eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle "Konferenzen" in Skype for Business Server 2015](conferences.md) . <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> |Der URI des Benutzers, dessen Konferenz beitreten/Leave-Informationen erfasst wurden.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Der Typ des URIs des Benutzers, dessen Konferenz beitreten/Leave-Informationen erfasst wurden. Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Der Mandant des Benutzers, dessen Konferenz beitreten/Leave-Informationen erfasst wurde. Weitere Informationen finden Sie in der [Tabelle Mandanten](tenants.md) . <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |Eindeutiger Bezeichner des Benutzers, dessen Konferenz beitreten/Leave-Informationen erfasst wurden.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Die Version des Clients, die von dem Benutzer verwendet wurde, dessen Konferenz beitreten/Leave-Informationen erfasst wurden.  <br/> |
|**UserClientType** <br/> |int  <br/> |Der Client, der von dem Benutzer verwendet wird, dessen Konferenz beitreten/Leave-Informationen erfasst wurde. Weitere Informationen finden Sie unter [UserAgentDef-Tabelle](useragentdef.md) . <br/> |
|**UserClientCategory** <br/> |nvarchar (64)  <br/> |Name der Kategorie des Clients, die von dem Benutzer verwendet wird, dessen Konferenz teilnehmen/-Abwesenheitsinformationen erfasst wurden.  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||
|**IsuserInternal** <br/> |bit  <br/> |Bit, das darstellt, ob der Benutzer ein interner Benutzer ist oder nicht.  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Uhrzeit der Sitzungsanforderung. Wird in Verbindung mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Wenn ein Benutzer gleichzeitig an mehreren Computern oder Geräten angemeldet ist, wird UserInstance verwendet, um die Kombination aus Benutzer und Gerät eindeutig zu identifizieren.  <br/> |
|**Dialogfeld-Nr** <br/> |varchar (775)  <br/> |SIP-Dialogfeld-ID der Sitzung. Das Format lautet: Dialogfeld; from-Tag; to-Tag.  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |Uhrzeit, zu der der Benutzer der Konferenz beigetreten ist.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |Der Zeitpunkt, zu dem der Benutzer die Konferenz verlassen hat.  <br/> |
|**UserRole** <br/> |nvarchar(256)  <br/> |Rolle des Benutzers in der Konferenz, beispielsweise Referent oder Teilnehmer.  <br/> |
   

