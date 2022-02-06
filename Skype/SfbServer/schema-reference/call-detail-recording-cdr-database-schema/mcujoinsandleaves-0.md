---
title: McuJoinsAndLeaves-Ansicht
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
description: 'Die McuJoinsAndLeaves-Ansicht speichert Informationen zum Beitreten und Verlassen von Benutzern für einen Konferenzserver. Jeder Datensatz in dieser Ansicht enthält Anrufdetails über eine Kombination aus einem Benutzer, der einer Konferenz beitritt oder sie verlässt, und einem Konferenzserver. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.'
---

# <a name="mcujoinsandleaves-view"></a>McuJoinsAndLeaves-Ansicht
 
Die McuJoinsAndLeaves-Ansicht speichert Informationen zum Beitreten und Verlassen von Benutzern für einen Konferenzserver. Jeder Datensatz in dieser Ansicht enthält Anrufdetails über eine Kombination aus einem Benutzer, der einer Konferenz beitritt oder sie verlässt, und einem Konferenzserver. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datum/Uhrzeit  <br/> |Zeitpunkt der Konferenzinstanz. Wird zusammen mit SessionIdSeq verwendet, um eine Konferenzinstanz eindeutig zu identifizieren. Weitere Informationen finden [Sie in der Tabelle "Konferenzen" in Skype for Business Server 2015](conferences.md). <br/> |
|**SessionIdSeq** <br/> |int  <br/> |ID zur Identifikation der Konferenzinstanz. Wird zusammen mit SessionIdTime verwendet, um eine Konferenzinstanz eindeutig zu identifizieren. Weitere Informationen finden [Sie in der Tabelle "Konferenzen" in Skype for Business Server 2015](conferences.md). <br/> |
|**McuUri** <br/> |nvarchar(256)  <br/> |Der URI des Konferenzservers, mit dem sich der Benutzer verbunden hat.  <br/> |
|**McuUriType** <br/> |nvarchar(256)  <br/> |Der URI des Konferenzservers, mit dem sich der Benutzer verbunden hat. Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |Der URI des Benutzers, dessen Informationen zum Beitreten/Verlassen für den Konferenzserver erfasst wurden.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Der Typ des URIs des Benutzers, dessen Informationen zum Beitreten/Verlassen für den Konferenzserver erfasst wurden. Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Der Mandant des Benutzers, dessen Informationen zum Beitreten/Verlassen für den Konferenzserver erfasst wurden. Weitere Informationen finden Sie in der [Tabelle "Mandanten](tenants.md) ". <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Die Version des URIs des Benutzers, dessen Informationen zum Beitreten/Verlassen für den Konferenzserver erfasst wurden.  <br/> |
|**UserClientType** <br/> |int  <br/> |Der Client, der vom Benutzer, dessen Informationen zum Beitreten/Verlassen für den Konferenzserver erfasst wurden, verwendet wurde. Weitere Informationen finden Sie in der [UserAgentDef-Tabelle](useragentdef.md) . <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |Der Name der Kategorie des Clients, der vom Benutzer, dessen Informationen zum Beitreten/Verlassen für den Konferenzserver erfasst wurden, verwendet wurde.  <br/> |
|**McuUserInstance** <br/> |int  <br/> |Identifiziert die Kombination aus Benutzer/Gerät für Benutzer, die gleichzeitig auf mehreren Geräten angemeldet sind, eindeutig.  <br/> |
|**IsUserFromPstn** <br/> |Bit  <br/> |Bitwert, der angibt, ob ein Benutzer ein interner Benutzer ist oder nicht.  <br/> |
|**DialogSessionIdTime** <br/> |Datum/Uhrzeit  <br/> |Zeitpunkt der Sitzungsanforderung. Wird zusammen mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren.. Weitere Informationen finden Sie [in der Dialogs-Tabelle in Skype for Business Server 2015](dialogs.md). <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |ID zur Identifikation der Sitzung. Wird zusammen mit SessionIdTime verwendet, um eine Konferenzinstanz eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Dialogs-Tabelle in Skype for Business Server 2015](dialogs.md). <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |SIP-DialogID der Sitzung. Das Format lautet: dialog;from-tag;to-tag.  <br/> |
|**UserJoinTime** <br/> |Datum/Uhrzeit  <br/> |Zeitpunkt, zu dem der Benutzer dem Konferenzserver beigetreten ist.  <br/> |
|**UserLeaveTime** <br/> |Datum/Uhrzeit  <br/> |Zeitpunkt, zu dem der Benutzer den Konferenzserver verlassen hat.  <br/> |
   

