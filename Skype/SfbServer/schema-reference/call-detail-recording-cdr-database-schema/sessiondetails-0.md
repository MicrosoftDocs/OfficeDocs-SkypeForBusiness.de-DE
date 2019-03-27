---
title: SessionDetails-Ansicht
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
description: Der SessionDetails View speichert Informationen zu Peer-zu-Peer-Sitzungen, die VoIP-VoIP-Anruf, zwei Teilnehmern Sofortnachrichtensitzung oder andere Art von Sitzung sein könnten. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: c62f6e2c1bb505bf00d56898a562db2c00d298d0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896028"
---
# <a name="sessiondetails-view"></a>SessionDetails-Ansicht
 
Der SessionDetails View speichert Informationen zu Peer-zu-Peer-Sitzungen, die VoIP-VoIP-Anruf, zwei Teilnehmern Sofortnachrichtensitzung oder andere Art von Sitzung sein könnten. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Zeitpunkt der sitzungsanforderung. Zusammen mit SessionIdSeq verwendet zur eindeutigen Identifizierung eine Sitzung. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Tabelle für Weitere Informationen. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |ID-Nummer, um die Sitzung zu identifizieren. In Verbindung mit SessionIdTime verwendet, um eine Sitzung eindeutig zu identifizieren. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**InviteTime** <br/> |datetime  <br/> |Zeitpunkt der ersten INVITE-Anforderung. In diesem Feld wird in der Regel durch aus der ersten INVITE-Nachricht in der Sitzung generierte Daten aufgefüllt. Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit Datum und Uhrzeit der ersten relevanten SIP-Nachricht (BYE, Abbrechen, Nachricht oder INFO) aufgefüllt. In diesem Feld wird in der Regel durch aus der ersten INVITE-Nachricht in der Sitzung generierte Daten aufgefüllt. Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit Datum und Uhrzeit der ersten relevanten SIP-Nachricht (BYE, Abbrechen, Nachricht oder INFO) aufgefüllt.  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |Der URI des Benutzers, der die Sitzung gestartet hat.  <br/> |
|**ToUri** <br/> |nvarchar(450)  <br/> |Der URI des Benutzers, der der Sitzung beigetreten ist.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |Typ der URI des Benutzers, der die Sitzung gestartet hat. Finden Sie weitere Informationen der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |Typ der URI des Benutzers, der der Sitzung beigetreten ist. Finden Sie weitere Informationen der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**FromTenant** <br/> |nvarchar(450)  <br/> |Mandant des Benutzers, der die Sitzung gestartet hat. Finden Sie weitere Informationen der [Tenants-Tabelle](tenants.md) . <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |Der Mandant des Benutzers, der die Sitzung beigetreten ist. Finden Sie weitere Informationen der [Tenants-Tabelle](tenants.md) . <br/> |
|**FromEndpointId** <br/> |uniqueidentifier  <br/> |Eindeutiger Bezeichner des Endpunkts des Benutzers, der die Sitzung gestartet hat.  <br/> |
|**ToEndpointId** <br/> |uniqueidentifier  <br/> |Eindeutiger Bezeichner des Endpunkts des Benutzers, der der Sitzung beigetreten ist.  <br/> |
|**EndTime** <br/> |datetime  <br/> |Die Endzeit der Sitzung.  <br/> |
|**FromMessageCount** <br/> |int  <br/> |Anzahl der Nachrichten des Benutzers, der die Sitzung gestartet hat.  <br/> |
|**ToMessageCount** <br/> |int  <br/> |Anzahl der Nachrichten des Benutzers, der der Sitzung beigetreten ist.  <br/> |
|**FromClientVersion** <br/> |nvarchar(256)  <br/> |Version des Client des Benutzers, der die Sitzung gestartet hat.  <br/> |
|**FromClientType** <br/> |int  <br/> |Client des Benutzers, der die Sitzung gestartet hat. Finden Sie weitere Details der [UserAgentDef-Tabelle](useragentdef.md) . <br/> |
|**FromClientCategory** <br/> |nvarchar(64)  <br/> |Name der Kategorie des Clients des Benutzers, der die Sitzung gestartet hat.  <br/> |
|**ToClientVersion** <br/> |nvarchar(256)  <br/> |Version des Clients des Benutzers, der die Sitzung beigetreten ist.  <br/> |
|**ToClientType** <br/> |int  <br/> |Client des Benutzers, der die Sitzung beigetreten ist. Finden Sie weitere Details der [UserAgentDef-Tabelle](useragentdef.md) . <br/> |
|**ToClientCategory** <br/> |nvarchar(64)  <br/> |Name der Kategorie des Clients des Benutzers, der die Sitzung beigetreten ist.  <br/> |
|**"TargetUri"** <br/> |nvarchar(450)  <br/> |Der URI des Zielbenutzers der Sitzung.  <br/> |
|**TargetUriType** <br/> |nvarchar(450)  <br/> |Typ der URI des Zielbenutzers der Sitzung. Finden Sie weitere Informationen der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**OnBehalfOfUri** <br/> |nvarchar(450)  <br/> |Der URI des Benutzers, in dessen Namen die Sitzung gestartet wurde.  <br/> |
|**OnnnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |Typ der URI des Benutzers, in dessen Namen die Sitzung gestartet wurde. Finden Sie weitere Informationen der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |Mandant des Benutzers, dessen im Namen die Sitzung gestartet wurde. Finden Sie weitere Informationen der [Tenants-Tabelle](tenants.md) . <br/> |
|**ReferredByUri** <br/> |nvarchar(450)  <br/> |Der URI des Benutzers, der die Sitzung verwiesen hat.  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |Typ der URI des Benutzers, der die Sitzung verwiesen hat. Finden Sie weitere Informationen der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**ReferredByTenant** <br/> |nvarchar(256)  <br/> |Mandant des Benutzers, der die Sitzung verwiesen hat. Finden Sie weitere Informationen der [Tenants-Tabelle](tenants.md) . <br/> |
|**Dialog-ID** <br/> |varchar(775)  <br/> |SIP-Dialog-ID. Das Format lautet:  <br/> Dialogfeld; aus Tag; -tag  <br/> |
|**CorrelationId** <br/> |uniqueidentifier  <br/> |GUID zum Korrelieren mehrerer Sitzungen.  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Zeitpunkt des Dialogfelds, das von der Sitzung ausgetauscht wurde. In Verbindung mit ReplaceDialogIdSeq verwendet, um ein Dialogfeld eindeutig zu identifizieren, die von der Sitzung ersetzt wird. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |ID-Nummer, um die Sitzung zu identifizieren. In Verbindung mit ReplaceDialogIdTime verwendet, um ein Dialogfeld eindeutig zu identifizieren, die von der Sitzung ersetzt wird. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**ReplacesDialogId** <br/> |varchar(775)  <br/> |SIP-Dialog-ID die Sitzung ersetzt. Das Format lautet:  <br/> Dialogfeld; aus Tag; -tag  <br/> |
|**ResponseTime** <br/> |datetime  <br/> |Zeitpunkt der Antwort auf die erste INVITE-Nachricht. In diesem Feld wird in der Regel durch aus der ersten INVITE-Nachricht in der Sitzung generierte Daten aufgefüllt. Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit Datum und Uhrzeit der ersten relevanten SIP-Nachricht (BYE, Abbrechen, Nachricht oder INFO) aufgefüllt.  <br/> |
|**ResponseCode** <br/> |int  <br/> |SIP-Antwortcode auf die sitzungseinladung. In diesem Feld wird in der Regel durch aus der ersten INVITE-Nachricht in der Sitzung generierte Daten aufgefüllt. Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit Datum und Uhrzeit der ersten relevanten SIP-Nachricht (BYE, Abbrechen, Nachricht oder INFO) aufgefüllt.  <br/> |
|**DiagnosticId** <br/> |int  <br/> |Diagnose-ID aus SIP-Headern erfasst.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |Typ des Inhalts für die Sitzung.  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |FQDN des Front-End-Servers, die die Daten für die Sitzung erfasst hat.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Vollqualifizierter Domänenname des Pools, der die Daten für die Sitzung erfasst hat.  <br/> |
|**FromEdgeServer** <br/> |nvarchar(256)  <br/> |FQDN des Edge-Servers, von dem Benutzer, der die Sitzung gestartet hat.  <br/> |
|**ToEdgeServer** <br/> |nvarchar(256)  <br/> |FQDN des Edge-Servers, von dem Benutzer, der die Sitzung gestartet hat  <br/> |
|**IsFromInternal** <br/> |bit  <br/> |Gibt an, ob der Benutzer, der die Sitzung gestartet hat, aus dem internen Netzwerk angemeldet.  <br/> |
|**IsToInternal** <br/> |bit  <br/> |Gibt an, ob der Benutzer, der die Sitzung beigetreten ist aus dem internen Netzwerk angemeldet.  <br/> |
|**CallPriority** <br/> |nvarchar(256)  <br/> |Anrufpriorität der Sitzung.  <br/> |
|**FromUserFlag** <br/> |smallint  <br/> |Gibt die Attribute des Benutzers, der die Sitzung gestartet hat. Die folgenden Attributdefinitionen sind zulässig:  <br/> 0 x 01 – mit Desktoptelefon integriert  <br/> |
|**ToUserFlag** <br/> |smallint  <br/> |Gibt die Attribute des Benutzers, der die Sitzung gestartet hat. Die folgenden Attributdefinitionen sind zulässig:  <br/> 0 x 01 – mit Desktoptelefon integriert  <br/> |
|**CallFlag** <br/> |smallint  <br/> |Gibt die Attribute des Anrufs. Die folgenden Attributdefinitionen sind zulässig:  <br/> 0 x 01 – Wiederholungsversuch der Sitzung  <br/> 0 x 02 - ein vom Agent im Namen einer Reaktionsgruppe getätigter Anruf  <br/> |
|**Standort** <br/> |varchar(max)  <br/> |Standort des Notrufs.  <br/> |
|**ZuletztGeändertUm** <br/> |DateTime  <br/> |Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype für Business Server 2015 eingeführt.  <br/> |
   

