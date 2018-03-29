---
title: ConferenceSessionDetails-Ansicht
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5858c84d-baed-421d-ad1d-3726e150e256
description: Der ConferenceSessionDetails View speichert Informationen über Sitzungen mit mehreren Beteiligten. Jeder Datensatz steht für eine konferenzsitzung, der die Sitzung mit Konferenzzustandsobjekt oder die Sitzung mit einem spezifischen Konferenzserver werden konnte. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 8e81f33a68fc90a589f4d3574f9ca3070076c479
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="conferencesessiondetails-view"></a>ConferenceSessionDetails-Ansicht
 
Der ConferenceSessionDetails View speichert Informationen über Sitzungen mit mehreren Beteiligten. Jeder Datensatz steht für eine konferenzsitzung, der die Sitzung mit Konferenzzustandsobjekt oder die Sitzung mit einem spezifischen Konferenzserver werden konnte. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Zeitpunkt der sitzungsanforderung. Zusammen mit SessionIdSeq verwendet zur eindeutigen Identifizierung eine Sitzung. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |ID-Nummer, um die Sitzung zu identifizieren. In Verbindung mit SessionIdTime verwendet, um eine Sitzung eindeutig zu identifizieren. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**InviteTime** <br/> |datetime  <br/> |Zeitpunkt der ersten INVITE-Anforderung. In diesem Feld wird in der Regel durch aus der ersten INVITE-Nachricht in der Sitzung generierte Daten aufgefüllt. Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit Datum und Uhrzeit der ersten relevanten SIP-Nachricht (BYE, Abbrechen, Nachricht oder INFO) aufgefüllt.  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |Der URI der Konferenz.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Typ des Konferenz-URI. Finden Sie weitere Informationen der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |Bezeichner, der zwischen Instanzen von sich wiederholenden Konferenzen unterscheidet. Jede Instanz der wiederkehrende Konferenz hat die gleichen ConferenceURI jedoch ein anderer Wert ConfInstance.  <br/> |
|**McuConferenceUri** <br/> |nvarchar(450)  <br/> |Der URI des Konferenzservers.  <br/> |
|**McuConferenceUriType** <br/> |nvarchar(256)  <br/> |Typ der Konferenzserver-URI. Finden Sie weitere Informationen der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |Der URI des Benutzers in der Sitzung.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Typ der URI des Benutzers wurde, dessen der Sitzung. Finden Sie weitere Informationen der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Mandant des Benutzers wurde, dessen der Sitzung. Finden Sie weitere Informationen der [Tenants-Tabelle](tenants.md) . <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |Eindeutiger Bezeichner des Benutzers wurde, dessen der Sitzung.  <br/> |
|**EndTime** <br/> |datetime  <br/> |Die Endzeit der Sitzung.  <br/> |
|**ConferenceClientVersion** <br/> |nvarchar(256)  <br/> |Version des Konferenzservers.  <br/> |
|**ConferenceClientType** <br/> |int  <br/> |Der Typ des Konferenzservers. [UserAgentDef-Tabelle](useragentdef.md) Weitere Informationen finden Sie. <br/> |
|**ConferenceCategory** <br/> |nvarchar(64)  <br/> |Die Kategorie des Konferenzservers.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Version des Clients, die vom Benutzer verwendet, die aus der Sitzung verwendet wurde.  <br/> |
|**UserClientType** <br/> |int  <br/> |Client des Benutzers, die aus der Sitzung verwendet wurde. Finden Sie weitere Details der [UserAgentDef-Tabelle](useragentdef.md) . <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |Name der Kategorie des Clients des Benutzers, der der Sitzung wurde.  <br/> |
|**OnBehalfOfUri** <br/> |nvarchar(450)  <br/> |Der URI des Benutzers, in dessen Namen die Sitzung gestartet wurde.  <br/> |
|**OnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |Typ der URI des Benutzers, in dessen Namen die Sitzung gestartet wurde. Finden Sie weitere Informationen der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |Mandant des Benutzers, dessen im Namen die Sitzung gestartet wurde. Finden Sie weitere Informationen der [Tenants-Tabelle](tenants.md) . <br/> |
|**ReferredByUri** <br/> |nvarchar(450)  <br/> |Der URI des Benutzers, der die Sitzung verwiesen hat.  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |Typ der URI des Benutzers, der die Sitzung verwiesen hat. Finden Sie weitere Informationen der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**ReferredByUriTenant** <br/> |nvarchar(256)  <br/> |Mandant des Benutzers, der die Sitzung verwiesen hat. Finden Sie weitere Informationen der [Tenants-Tabelle](tenants.md) . <br/> |
|**Dialog-ID** <br/> |varstring(775)  <br/> |SIP-Dialog-ID. Das Format ist  <br/> : Dialogfeld; aus Tag; -Tag  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |ID-Nummer im Dialogfeld bestimmt, die durch die aktuelle Sitzung ausgetauscht wurde. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |ID-Nummer, um die Sitzung zu identifizieren. In Verbindung mit ReplaceDialogIdTime verwendet, um eine Sitzung eindeutig zu identifizieren, die von dieser Sitzung ersetzt wird. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**ReplacesDialogId** <br/> |varchar(775)  <br/> |SIP-Dialog-ID die Sitzung ersetzt. Das Format der ist:  <br/> Dialogfeld; aus Tag; -tag  <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> |Gibt an, ob die Sitzung vom Konferenzserver gestartet wurde.  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> |Gibt an, ob die Sitzung vom Konferenzserver beendet wurde.  <br/> |
|**IsUserInternal** <br/> |bit  <br/> |Gibt an, ob der Benutzer aus dem internen Netzwerk angemeldet.  <br/> |
|**ResponseTime** <br/> |datetime  <br/> |Zeitpunkt der Antwort auf die erste INVITE-Nachricht. In diesem Feld wird in der Regel durch aus der ersten INVITE-Nachricht in der Sitzung generierte Daten aufgefüllt. Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit Datum und Uhrzeit der ersten relevanten SIP-Nachricht (BYE, Abbrechen, Nachricht oder INFO) aufgefüllt.  <br/> |
|**ResponseCode** <br/> |int  <br/> |SIP-Antwortcode auf die sitzungseinladung. In diesem Feld wird in der Regel durch aus der ersten INVITE-Nachricht in der Sitzung generierte Daten aufgefüllt. Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit Datum und Uhrzeit der ersten relevanten SIP-Nachricht (BYE, Abbrechen, Nachricht oder INFO) aufgefüllt.  <br/> |
|**DiagnosticId** <br/> |int  <br/> |Diagnose-ID aus der Sitzung SIP-Header.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |Inhaltstyp für die Sitzung.  <br/> |
|**Front-End** <br/> |nvarchar(256)  <br/> |FQDN des Front-End-Servers, die die Daten für die Sitzung erfasst hat.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Vollqualifizierter Domänenname des Pools, der die Daten für die Sitzung erfasst hat.  <br/> |
|**MediationServer** <br/> |nvarchar(256)  <br/> |Vom Benutzer aus der Sitzung verwendet wurde, verwendeter Vermittlungsserver.  <br/> |
|**Gateway** <br/> |nvarchar(256)  <br/> |Vom Benutzer verwendet wurde, verwendetes Gateway der Sitzung.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |FQDN des Edge-Servers, von dem Benutzer, die aus der Sitzung verwendet wurde.  <br/> |
|**UserFlag** <br/> |smallint  <br/> |Gibt die Attribute des Benutzers, der aus der Sitzung verwendet wurde. Die folgenden Attributdefinitionen zulässig:  <br/> 0 x 01 – mit Desktoptelefon integriert  <br/> |
|**CallFlag** <br/> |smallint  <br/> |Gibt die Attribute des Anrufs. Die folgenden Attributdefinitionen sind zulässig:  <br/> 0 x 01 – mit Wiederholungsversuch pro Session0  <br/> X02-ein vom Agent im Namen einer Reaktionsgruppe getätigter Anruf  <br/> |
   

