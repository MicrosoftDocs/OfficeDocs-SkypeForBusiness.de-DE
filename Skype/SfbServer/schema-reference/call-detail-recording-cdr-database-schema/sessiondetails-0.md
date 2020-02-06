---
title: SessionDetails-Ansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
description: In der SessionDetails-Ansicht werden Informationen zu Peer-to-Peer-Sitzungen gespeichert, bei denen es sich um einen VoIP-VoIP-Anruf, eine Chatsitzung mit zwei Teilnehmern oder eine andere Art von Sitzung handeln kann. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: f1d0d68fe152f277c02c53fd87afdb0ea4e4ab0c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814913"
---
# <a name="sessiondetails-view"></a>SessionDetails-Ansicht
 
In der SessionDetails-Ansicht werden Informationen zu Peer-to-Peer-Sitzungen gespeichert, bei denen es sich um einen VoIP-VoIP-Anruf, eine Chatsitzung mit zwei Teilnehmern oder eine andere Art von Sitzung handeln kann. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**SessionID** <br/> |datetime  <br/> |Uhrzeit der Sitzungsanforderung. Wird in Verbindung mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie in der Tabelle [Dialogfelder in der Skype for Business Server 2015](dialogs.md) -Tabelle. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Die ID-Nummer, um die Sitzung zu identifizieren. Wird in Verbindung mit SessionID-Mal verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**Einladen** <br/> |datetime  <br/> |Uhrzeit der ersten INVITE-Anforderung. Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden. Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info). Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden. Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).  <br/> |
|**FromUri** <br/> |nvarchar (450)  <br/> |Der URI des Benutzers, der die Sitzung gestartet hat.  <br/> |
|**Touri** <br/> |nvarchar (450)  <br/> |Der URI des Benutzers, der der Sitzung beigetreten ist.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |Der Typ des URIs des Benutzers, der die Sitzung gestartet hat. Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |Der Typ des URIs des Benutzers, der der Sitzung beigetreten ist. Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**FromTenant** <br/> |nvarchar (450)  <br/> |Der Mandant des Benutzers, der die Sitzung gestartet hat. Weitere Informationen finden Sie in der [Tabelle Mandanten](tenants.md) . <br/> |
|**Totenant** <br/> |nvarchar(256)  <br/> |Der Mandant des Benutzers, der der Sitzung beigetreten ist. Weitere Informationen finden Sie in der [Tabelle Mandanten](tenants.md) . <br/> |
|**FromEndpointId** <br/> |uniqueidentifier  <br/> |Eindeutiger Bezeichner des Endpunkts des Benutzers, der die Sitzung gestartet hat.  <br/> |
|**Endpunkt-Nr** <br/> |uniqueidentifier  <br/> |Eindeutiger Bezeichner des Endpunkts des Benutzers, der der Sitzung beigetreten ist.  <br/> |
|**EndTime** <br/> |datetime  <br/> |Endzeit der Sitzung.  <br/> |
|**FromMessageCount** <br/> |int  <br/> |Die Anzahl der Nachrichten, die von dem Benutzer gesendet wurden, der die Sitzung gestartet hat.  <br/> |
|**ToMessageCount** <br/> |int  <br/> |Die Anzahl der Nachrichten, die von dem Benutzer gesendet wurden, der der Sitzung beigetreten ist.  <br/> |
|**FromClientVersion** <br/> |nvarchar(256)  <br/> |Die Version des Clients, die von dem Benutzer verwendet wird, der die Sitzung gestartet hat.  <br/> |
|**FromClientType** <br/> |int  <br/> |Der Client, der von dem Benutzer verwendet wird, der die Sitzung gestartet hat. Weitere Informationen finden Sie in der [UserAgentDef-Tabelle](useragentdef.md) . <br/> |
|**FromClientCategory** <br/> |nvarchar (64)  <br/> |Der Name der Kategorie des Clients, der vom Benutzer verwendet wird, der die Sitzung gestartet hat.  <br/> |
|**ToClientVersion** <br/> |nvarchar(256)  <br/> |Die Version des Clients, die von dem Benutzer verwendet wird, der der Sitzung beigetreten ist  <br/> |
|**Toclienttype** <br/> |int  <br/> |Der Client, der von dem Benutzer verwendet wird, der der Sitzung beigetreten ist. Weitere Informationen finden Sie in der [UserAgentDef-Tabelle](useragentdef.md) . <br/> |
|**ToClientCategory** <br/> |nvarchar (64)  <br/> |Der Name der Kategorie des Clients, der von dem Benutzer verwendet wird, der der Sitzung beigetreten ist.  <br/> |
|**TargetUri** <br/> |nvarchar (450)  <br/> |Der URI des Zielbenutzers der Sitzung.  <br/> |
|**TargetUriType** <br/> |nvarchar (450)  <br/> |Der Typ des URIs des Zielbenutzers für die Sitzung. Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**OnBehalfOfUri** <br/> |nvarchar (450)  <br/> |Der URI des Benutzers, in dessen Auftrag die Sitzung gestartet wurde.  <br/> |
|**OnnnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |Der Typ des URIs des Benutzers, in dessen Auftrag die Sitzung gestartet wurde. Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |Der Mandant des Benutzers, dessen Namen für die Sitzung gestartet wurde. Weitere Informationen finden Sie in der [Tabelle Mandanten](tenants.md) . <br/> |
|**ReferredByUri** <br/> |nvarchar (450)  <br/> |Der URI des Benutzers, der die Sitzung angewiesen hat.  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |Der Typ des URIs des Benutzers, der die Sitzung angewiesen hat. Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**ReferredByTenant** <br/> |nvarchar(256)  <br/> |Der Mandant des Benutzers, der die Sitzung angewiesen hat. Weitere Informationen finden Sie in der [Tabelle Mandanten](tenants.md) . <br/> |
|**Dialogfeld-Nr** <br/> |varchar (775)  <br/> |SIP-Dialogfeld-ID. Das Format lautet:  <br/> Dialogfeld; from-Tag; to-Tag  <br/> |
|**CorrelationId** <br/> |uniqueidentifier  <br/> |GUID, die verwendet wird, um mehrere Sitzungen zu korrelieren.  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Uhrzeit des Dialogs, der durch die Sitzung ersetzt wurde. Wird in Verbindung mit ReplaceDialogIdSeq verwendet, um ein durch die Sitzung Ersetztes Dialogfeld eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Die ID-Nummer, um die Sitzung zu identifizieren. Wird in Verbindung mit ReplaceDialogIdTime verwendet, um ein durch die Sitzung Ersetztes Dialogfeld eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**ReplacesDialogId** <br/> |varchar (775)  <br/> |SIP-Dialog-ID, die die Sitzung ersetzt. Das Format lautet:  <br/> Dialogfeld; from-Tag; to-Tag  <br/> |
|**Webantworten** <br/> |datetime  <br/> |Zeitpunkt der Antwort auf die erste Einladungsnachricht. Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden. Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).  <br/> |
|**Response Code** <br/> |int  <br/> |SIP-Antwortcode für die Sitzungseinladung Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden. Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).  <br/> |
|**Diagnose-Nr** <br/> |int  <br/> |Von SIP-Headern erfasste Diagnose-ID.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |Der Typ des Inhalts für die Sitzung.  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |FQDN des Front-End-Servers, der die Daten für die Sitzung erfasst hat.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Der FQDN des Pools, in dem die Daten für die Sitzung erfasst wurden.  <br/> |
|**FromEdgeServer** <br/> |nvarchar(256)  <br/> |Der FQDN des Edge-Servers, der vom Benutzer verwendet wird, der die Sitzung gestartet hat.  <br/> |
|**ToEdgeServer** <br/> |nvarchar(256)  <br/> |FQDN des Edge-Servers, der vom Benutzer verwendet wird, der die Sitzung gestartet hat  <br/> |
|**IsFromInternal** <br/> |bit  <br/> |Gibt an, ob der Benutzer, der die Sitzung gestartet hat, sich über das interne Netzwerk angemeldet hat.  <br/> |
|**IsToInternal** <br/> |bit  <br/> |Gibt an, ob der Benutzer, der der Sitzung beigetreten ist, aus dem internen Netzwerk angemeldet ist.  <br/> |
|**CallPriority** <br/> |nvarchar(256)  <br/> |Anrufpriorität der Sitzung.  <br/> |
|**FromUserFlag** <br/> |smallint  <br/> |Gibt die Attribute des Benutzers an, der die Sitzung gestartet hat. Die folgenden Attributdefinitionen sind zulässig:  <br/> 0x01-integriert mit dem Desktoptelefon  <br/> |
|**ToUserFlag** <br/> |smallint  <br/> |Gibt die Attribute des Benutzers an, der die Sitzung gestartet hat. Die folgenden Attributdefinitionen sind zulässig:  <br/> 0x01-integriert mit dem Desktoptelefon  <br/> |
|**CallFlag** <br/> |smallint  <br/> |Gibt die anrufattribute an. Die folgenden Attributdefinitionen sind zulässig:  <br/> 0x01-wiederholte Sitzung  <br/> 0x02 – ein Anruf, der von einem Agenten im Auftrag einer Reaktionsgruppe durchgeführt wurde  <br/> |
|**Standort** <br/> |varchar (max)  <br/> |Ort des Notrufs.  <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> |Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype for Business Server 2015 eingeführt.  <br/> |
   

