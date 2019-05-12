---
title: McuJoinsAndLeaves-Ansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
description: McuJoinsAndLeaves-Ansicht speichert Informationen zu Benutzer teilnehmen, und lassen Sie Informationen für eine Konferenzserver. Jeder Datensatz in dieser Ansicht enthält Anrufdetails zu eine Kombination aus einem Benutzer beitreten oder verlassen und Conferencing Server. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 756f9656e31f180ac6b724c8c31c6a7226cada08
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930234"
---
# <a name="mcujoinsandleaves-view"></a>McuJoinsAndLeaves-Ansicht
 
McuJoinsAndLeaves-Ansicht speichert Informationen zu Benutzer teilnehmen, und lassen Sie Informationen für eine Konferenzserver. Jeder Datensatz in dieser Ansicht enthält Anrufdetails zu eine Kombination aus einem Benutzer beitreten oder verlassen und Conferencing Server. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Zeitpunkt des Konferenz-Instanz. Zusammen mit SessionIdSeq verwendet zur eindeutigen Identifizierung eine Konferenz-Instanz. [Conferences-Tabelle in Skype für Business Server 2015](conferences.md) Weitere Informationen finden Sie. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |ID-Nummer zum Identifizieren der Konferenz-Instanz. In Verbindung mit SessionIdTime verwendet, um eine Instanz der Konferenz eindeutig zu identifizieren. [Conferences-Tabelle in Skype für Business Server 2015](conferences.md) Weitere Informationen finden Sie. <br/> |
|**McuUri** <br/> |nvarchar(256)  <br/> |Der URI des Konferenzservers, die der Benutzer verbunden.  <br/> |
|**McuUriType** <br/> |nvarchar(256)  <br/> |Der URI des Konferenzservers, die der Benutzer verbunden. Finden Sie weitere Informationen der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |Der URI des Benutzers, dessen Serverinformationen beitreten/verlassen einer Konferenz erfasst wurde.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Der Typ der URI des Benutzers, dessen Serverinformationen beitreten/verlassen einer Konferenz erfasst wurde. Finden Sie weitere Informationen der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Der Mandant des Benutzers, dessen Serverinformationen beitreten/verlassen einer Konferenz erfasst wurde. Finden Sie weitere Informationen der [Tenants-Tabelle](tenants.md) . <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Die Version des Client des Benutzers, dessen Serverinformationen beitreten/verlassen einer Konferenz erfasst wurde.  <br/> |
|**UserClientType** <br/> |int  <br/> |Der Client des Benutzers, dessen Serverinformationen beitreten/verlassen einer Konferenz erfasst wurde. Finden Sie weitere Details der [UserAgentDef-Tabelle](useragentdef.md) . <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |Der Name der Kategorie des Clients des Benutzers, dessen Serverinformationen beitreten/verlassen einer Konferenz erfasst wurde.  <br/> |
|**McuUserInstance** <br/> |int  <br/> |Die Benutzer/Geräte-Kombination für Benutzer, die gleichzeitig auf mehreren Geräten angemeldet identifiziert eindeutig.  <br/> |
|**IsUserFromPstn** <br/> |bit  <br/> |Bitwert, der angibt, ob der Benutzer ein interner Benutzer oder nicht ist.  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Zeitpunkt der sitzungsanforderung. Zusammen mit SessionIdSeq verwendet zur eindeutigen Identifizierung eine Sitzung. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |ID-Nummer, um die Sitzung zu identifizieren. In Verbindung mit SessionIdTime verwendet, um eine Sitzung eindeutig zu identifizieren. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**Dialog-ID** <br/> |varchar(775)  <br/> |SIP-Dialog-ID der Sitzung. Das Format lautet: Dialogfeld; aus Tag; zu Tag.  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |Zeitpunkt der Benutzer dem Konferenzserver beigetreten ist.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |Zeitpunkt, zu des Benutzers den Konferenzserver verlassen.  <br/> |
   

