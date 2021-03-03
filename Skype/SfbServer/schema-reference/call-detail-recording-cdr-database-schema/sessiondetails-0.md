---
title: '#A0'
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
ms.assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
description: In der Ansicht "SessionDetails" werden Informationen zu Peer-zu-Peer-Sitzungen gespeichert, bei denen es sich um einen VoIP-VoIP-Telefonanruf, eine VoIP-VoIP mit zwei Parteien oder eine andere Art von Sitzung sein kann. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 71875dd1f3399b382c1fac3754436ada052873af
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809955"
---
# <a name="sessiondetails-view"></a>#A0
 
In der Ansicht "SessionDetails" werden Informationen zu Peer-zu-Peer-Sitzungen gespeichert, bei denen es sich um einen VoIP-VoIP-Telefonanruf, eine VoIP-VoIP mit zwei Parteien oder eine andere Art von Sitzung sein kann. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datum/Uhrzeit  <br/> |Zeitpunkt der Sitzungsanforderung. Wird zusammen mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren.. Weitere Informationen finden Sie in der [Tabelle "Dialogfelder" in Skype for Business Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |ID zur Identifikation der Sitzung. Wird zusammen mit SessionIdTime verwendet, um eine Konferenzinstanz eindeutig zu identifizieren. Weitere Informationen [finden Sie in der Tabelle "Dialogfelder" in Skype for Business Server 2015.](dialogs.md) <br/> |
|**InviteTime** <br/> |Datum/Uhrzeit  <br/> |Zeitpunkt der ersten INVITE-Anforderung. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |URI des Benutzers, der die Sitzung gestartet hat.  <br/> |
|**ToUri** <br/> |nvarchar(450)  <br/> |URI des Benutzers, der der Sitzung beigetreten ist.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |Typ des URI des Benutzers, der die Sitzung gestartet hat. Weitere Informationen finden Sie in der [Tabelle "UriTypes".](uritypes.md) <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |Typ des URI des Benutzers, der der Sitzung beigetreten ist. Weitere Informationen finden Sie in der [Tabelle "UriTypes".](uritypes.md) <br/> |
|**FromTenant** <br/> |nvarchar(450)  <br/> |Mandant des Benutzers, der die Sitzung gestartet hat. Weitere Informationen [finden Sie in der Tabelle "Mandanten".](tenants.md) <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |Mandant des Benutzers, der der Sitzung beigetreten ist. Weitere Informationen [finden Sie in der Tabelle "Mandanten".](tenants.md) <br/> |
|**FromEndpointId** <br/> |uniqueidentifier  <br/> |Eindeutiger Bezeichner des Endpunkts des Benutzers, der die Sitzung gestartet hat.  <br/> |
|**ToEndpointId** <br/> |uniqueidentifier  <br/> |Eindeutiger Bezeichner des Endpunkts des Benutzers, der der Sitzung beigetreten ist.  <br/> |
|**EndTime** <br/> |Datum/Uhrzeit  <br/> |Endzeitpunkt der Sitzung.  <br/> |
|**FromMessageCount** <br/> |int  <br/> |Anzahl der Nachrichten, die von dem Benutzer gesendet wurden, der die Sitzung gestartet hat.  <br/> |
|**ToMessageCount** <br/> |int  <br/> |Anzahl der Nachrichten, die von dem Benutzer gesendet wurden, der der Sitzung beigetreten ist.  <br/> |
|**FromClientVersion** <br/> |nvarchar(256)  <br/> |Version des Clients, die der Benutzer verwendet, der die Sitzung gestartet hat.  <br/> |
|**FromClientType** <br/> |int  <br/> |Client, den der Benutzer verwendet, der die Sitzung gestartet hat. Weitere Informationen finden [Sie in der Tabelle "UserAgentDef".](useragentdef.md) <br/> |
|**FromClientCategory** <br/> |nvarchar(64)  <br/> |Name der Kategorie des Clients, den der Benutzer verwendet, der die Sitzung gestartet hat.  <br/> |
|**ToClientVersion** <br/> |nvarchar(256)  <br/> |Version des Clients, die der Benutzer verwendet, der der Sitzung beigetreten ist.  <br/> |
|**ToClientType** <br/> |int  <br/> |Client, den der Benutzer verwendet, der der Sitzung beigetreten ist. Weitere Informationen finden [Sie in der Tabelle "UserAgentDef".](useragentdef.md) <br/> |
|**ToClientCategory** <br/> |nvarchar(64)  <br/> |Name der Kategorie des Clients, den der Benutzer verwendet, der der Sitzung beigetreten ist.  <br/> |
|**TargetUri** <br/> |nvarchar(450)  <br/> |URI des Zielbenutzers der Sitzung.  <br/> |
|**TargetUriType** <br/> |nvarchar(450)  <br/> |Typ des URI des Zielbenutzers der Sitzung. Weitere Informationen finden Sie in der [Tabelle "UriTypes".](uritypes.md) <br/> |
|**OnBehalfOfUri** <br/> |nvarchar(450)  <br/> |URI des Benutzers, in dessen Namen die Sitzung gestartet worden ist.  <br/> |
|**OnnnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |Typ des URI des Benutzers, in dessen Namen die Sitzung gestartet worden ist. Weitere Informationen finden Sie in der [Tabelle "UriTypes".](uritypes.md) <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |Mandant des Benutzers, in dessen Namen die Sitzung gestartet worden ist. Weitere Informationen [finden Sie in der Tabelle "Mandanten".](tenants.md) <br/> |
|**ReferredByUri** <br/> |nvarchar(450)  <br/> |URI des Benutzers, der die Sitzung weitergeleitet hat.  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |Typ des URI des Benutzers, der die Sitzung weitergeleitet hat. Weitere Informationen finden Sie in der [Tabelle "UriTypes".](uritypes.md) <br/> |
|**ReferredByTenant** <br/> |nvarchar(256)  <br/> |Mandant des Benutzers, der die Sitzung weitergeleitet hat. Weitere Informationen [finden Sie in der Tabelle "Mandanten".](tenants.md) <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |SIP-Dialog-ID. Das Format lautet wie folgt:  <br/> dialog;from-tag;to-tag  <br/> |
|**CorrelationId** <br/> |uniqueidentifier  <br/> |GUID zum Korrelieren mehrerer Sitzungen.  <br/> |
|**ReplaceDialogIdTime** <br/> |Datum/Uhrzeit  <br/> |Zeitpunkt des Dialogfelds, das durch die Sitzung ersetzt wurde. Wird in Verbindung mit ReplaceDialogIdSeq verwendet, um ein Dialogfeld eindeutig zu identifizieren, das durch die Sitzung ersetzt wird. Weitere Informationen [finden Sie in der Tabelle "Dialogfelder" in Skype for Business Server 2015.](dialogs.md) <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |ID zur Identifikation der Sitzung. Wird in Verbindung mit ReplaceDialogIdTime verwendet, um ein Dialogfeld eindeutig zu identifizieren, das durch die Sitzung ersetzt wird. Weitere Informationen [finden Sie in der Tabelle "Dialogfelder" in Skype for Business Server 2015.](dialogs.md) <br/> |
|**ReplacesDialogId** <br/> |varchar(775)  <br/> |SIP-Dialog-ID, die durch die Sitzung ersetzt wird. Das Format lautet wie folgt:  <br/> dialog;from-tag;to-tag  <br/> |
|**ResponseTime** <br/> |Datum/Uhrzeit  <br/> |Zeitpunkt der Antwort auf die erste INVITE-Nachricht. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.  <br/> |
|**ResponseCode** <br/> |int  <br/> |SIP-Antwortcode auf die Sitzungseinladung. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.  <br/> |
|**DiagnosticId** <br/> |int  <br/> |Diagnose-ID, die aus SIP-Headern erfasst wird.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |Typ des Inhalts für die Sitzung.  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |Vollqualifizierter Domänenname des Front-End-Servers, der die Daten für die Sitzung erfasst hat.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Vollqualifizierter Domänenname des Pools, der die Daten für die Sitzung erfasst hat.  <br/> |
|**FromEdgeServer** <br/> |nvarchar(256)  <br/> |Vollqualifizierter Domänenname des Edgeservers, den der Benutzer verwendet, der die Sitzung gestartet hat.  <br/> |
|**ToEdgeServer** <br/> |nvarchar(256)  <br/> |Vollqualifizierter Domänenname des Edgeservers, den der Benutzer verwendet, der der Sitzung beigetreten ist.  <br/> |
|**IsFromInternal** <br/> |bit  <br/> |Gibt an, ob der Benutzer, der die Sitzung gestartet hat, über das interne Netzwerk angemeldet war.  <br/> |
|**IsToInternal** <br/> |bit  <br/> |Gibt an, ob der Benutzer, der der Sitzung beigetreten ist, über das interne Netzwerk angemeldet war.  <br/> |
|**CallPriority** <br/> |nvarchar(256)  <br/> |Anrufpriorität der Sitzung.  <br/> |
|**FromUserFlag** <br/> |smallint  <br/> |Gibt die Attribute des Benutzers an, der die Sitzung gestartet hat. Die folgenden Attributdefinitionen sind zulässig:  <br/> 0x01 - Mit dem Desktoptelefon integriert  <br/> |
|**ToUserFlag** <br/> |smallint  <br/> |Gibt die Attribute des Benutzers an, der die Sitzung gestartet hat. Die folgenden Attributdefinitionen sind zulässig:  <br/> 0x01 - Mit dem Desktoptelefon integriert  <br/> |
|**CallFlag** <br/> |smallint  <br/> |Gibt die Anrufattribute an. Die folgenden Attributdefinitionen sind zulässig:  <br/> 0x01 - Sitzung mit Wiederholungsversuch  <br/> 0x02 - Ein vom Agent im Namen einer Reaktionsgruppe getätigter Anruf  <br/> |
|**Ort** <br/> |varchar(max)  <br/> |Standort des Notrufs.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> |Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype for Business Server 2015 eingeführt.  <br/> |
   

