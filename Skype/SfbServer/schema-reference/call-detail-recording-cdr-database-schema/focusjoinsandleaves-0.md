---
title: FocusJoinsAndLeaves-Ansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 226460ef-766f-4d61-80cb-f332b65a210d
description: FocusJoinsAndLeaves-Ansicht speichert Informationen zu Join und lassen Sie Informationen für eine Konferenz. Jede Konferenz wird in dieser Ansicht durch einen Datensatz geschrieben, wenn ein Benutzer verknüpft und die Konferenz verlässt dargestellt. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 3565a9bfbcfd735e4ba6b16facd8e0c88abd4a13
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901180"
---
# <a name="focusjoinsandleaves-view"></a>FocusJoinsAndLeaves-Ansicht
 
FocusJoinsAndLeaves-Ansicht speichert Informationen zu Join und lassen Sie Informationen für eine Konferenz. Jede Konferenz wird in dieser Ansicht durch einen Datensatz geschrieben, wenn ein Benutzer verknüpft und die Konferenz verlässt dargestellt. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Zeitpunkt des Konferenz-Instanz. Zusammen mit SessionIdSeq verwendet zur eindeutigen Identifizierung eine Konferenz-Instanz. [Conferences-Tabelle in Skype für Business Server 2015](conferences.md) Weitere Informationen finden Sie. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |ID-Nummer zum Identifizieren der Konferenz-Instanz. In Verbindung mit SessionIdTime verwendet, um eine Instanz der Konferenz eindeutig zu identifizieren. [Conferences-Tabelle in Skype für Business Server 2015](conferences.md) Weitere Informationen finden Sie. <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |Der URI des Benutzers, dessen Konferenz beitreten/verlassen erfasst wurden.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Typ der URI des Benutzers, dessen Konferenz beitreten/verlassen erfasst wurden. Finden Sie weitere Informationen der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Mandant des Benutzers, dessen Konferenz beitreten/verlassen erfasst wurden. Finden Sie weitere Informationen der [Tenants-Tabelle](tenants.md) . <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |Eindeutiger Bezeichner des Benutzers, dessen Konferenz beitreten/verlassen erfasst wurden.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Version des Client des Benutzers, dessen Konferenz beitreten/verlassen erfasst wurden.  <br/> |
|**UserClientType** <br/> |int  <br/> |Client des Benutzers, dessen Konferenz beitreten/verlassen erfasst wurden. Einzelheiten finden Sie unter [UserAgentDef-Tabelle](useragentdef.md) . <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |Name der Kategorie des Clients des Benutzers, dessen Konferenz beitreten/verlassen erfasst wurden.  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||
|**IsuserInternal** <br/> |bit  <br/> |Bitwert, der angibt, ob der Benutzer ein interner Benutzer oder nicht ist.  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Zeitpunkt der sitzungsanforderung. Zusammen mit SessionIdSeq verwendet zur eindeutigen Identifizierung eine Sitzung. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Wenn ein Benutzer auf mehreren Computern oder Geräten gleichzeitig angemeldet ist, wird UserInstance verwendet, um die Benutzer/Geräte-Kombination eindeutig zu identifizieren.  <br/> |
|**Dialog-ID** <br/> |varchar(775)  <br/> |SIP-Dialog-ID der Sitzung. Das Format lautet: Dialogfeld; aus Tag; zu Tag.  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |Die Zeit, der Benutzer an der Konferenz Teil.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |Die Zeit, die der Benutzer die Konferenz verlassen.  <br/> |
|**UserRole** <br/> |nvarchar(256)  <br/> |Rolle des Benutzers bei der Konferenz, wie etwa Referent oder Teilnehmer.  <br/> |
   

