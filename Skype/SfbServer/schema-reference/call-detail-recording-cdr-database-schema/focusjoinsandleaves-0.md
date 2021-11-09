---
title: FocusJoinsAndLeaves-Ansicht
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 226460ef-766f-4d61-80cb-f332b65a210d
description: In der FocusJoinsAndLeaves-Ansicht werden Informationen zum Beitreten und Verlassen von Informationen für eine Konferenz gespeichert. Jede Konferenz wird in dieser Ansicht durch einen Datensatz dargestellt, der jedes Mal geschrieben wird, wenn ein Benutzer der Konferenz beitritt und diese verlässt. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 8dcc82fe641b451190236f813f432c237e7fa2e2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845058"
---
# <a name="focusjoinsandleaves-view"></a>FocusJoinsAndLeaves-Ansicht
 
In der FocusJoinsAndLeaves-Ansicht werden Informationen zum Beitreten und Verlassen von Informationen für eine Konferenz gespeichert. Jede Konferenz wird in dieser Ansicht durch einen Datensatz dargestellt, der jedes Mal geschrieben wird, wenn ein Benutzer der Konferenz beitritt und diese verlässt. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datum/Uhrzeit  <br/> |Zeitpunkt der Konferenzinstanz. Wird zusammen mit SessionIdSeq verwendet, um eine Konferenzinstanz eindeutig zu identifizieren. Weitere Informationen finden Sie in der [Tabelle "Konferenzen" in Skype for Business Server 2015.](conferences.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |ID zur Identifikation der Konferenzinstanz. Wird zusammen mit SessionIdTime verwendet, um eine Konferenzinstanz eindeutig zu identifizieren. Weitere Informationen finden Sie in der [Tabelle "Konferenzen" in Skype for Business Server 2015.](conferences.md) <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI des Benutzers, dessen Informationen zum Beitreten/Verlassen einer Konferenz erfasst wurden.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Typ des URIs des Benutzers, dessen Informationen zum Beitreten/Verlassen einer Konferenz erfasst wurden. Weitere Informationen finden Sie in der [UriTypes-Tabelle.](uritypes.md) <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Mandant des Benutzers, dessen Informationen zum Beitreten/Verlassen einer Konferenz erfasst wurden. Weitere Informationen finden Sie in der [Tabelle "Mandanten".](tenants.md) <br/> |
|**UserEndpointId** <br/> |Uniqueidentifier  <br/> |Eindeutiger Bezeichner des Benutzers, dessen Informationen zum Beitreten/Verlassen einer Konferenz erfasst wurden.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Version des Client des Benutzers, dessen Informationen zum Beitreten/Verlassen einer Konferenz erfasst wurden.  <br/> |
|**UserClientType** <br/> |int  <br/> |Client, der vom Benutzer verwendet wurde, dessen Informationen zum Beitreten/Verlassen einer Konferenz erfasst wurden. Weitere Informationen finden Sie in [der UserAgentDef-Tabelle.](useragentdef.md) <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |Name der Kategorie des Clients des Benutzers, dessen Informationen zum Beitreten/Verlassen einer Konferenz erfasst wurden.  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||
|**IsuserInternal** <br/> |Bit  <br/> |Bitwert, der angibt, ob ein Benutzer ein interner Benutzer ist oder nicht.  <br/> |
|**DialogSessionIdTime** <br/> |Datum/Uhrzeit  <br/> |Zeitpunkt der Sitzungsanforderung. Wird zusammen mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren.. Weitere Informationen finden Sie in der [Dialogs-Tabelle in Skype for Business Server 2015.](dialogs.md) <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Wenn ein Benutzer auf mehreren Computern oder Geräten gleichzeitig angemeldet ist, wird UserInstance verwendet, um die Benutzer/Geräte-Kombination eindeutig zu identifizieren.  <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |SIP-DialogID der Sitzung. Das Format lautet: dialog;from-tag;to-tag.  <br/> |
|**UserJoinTime** <br/> |Datum/Uhrzeit  <br/> |Zeitpunkt, zu dem dieser Benutzer der Konferenz beitrat.  <br/> |
|**UserLeaveTime** <br/> |Datum/Uhrzeit  <br/> |Zeitpunkt, zu dem dieser Benutzer die Konferenz verließ.  <br/> |
|**Userrole** <br/> |nvarchar(256)  <br/> |Rolle des Benutzers in der Konferenz, z. B. Referent oder Teilnehmer.  <br/> |
   

