---
title: ConferenceSessionDetails-Ansicht
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5858c84d-baed-421d-ad1d-3726e150e256
description: In der ConferenceSessionDetails-Ansicht werden Informationen zu Sitzungen mit mehreren Teilnehmern gespeichert. Jeder Datensatz steht für eine Konferenzsitzung, bei der es sich entweder um die Sitzung mit Konferenzzustandsobjekt oder die Sitzung mit einem spezifischen Konferenzserver handelt. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: cebd4acd218d551f7f43dba39334c342441e216a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771901"
---
# <a name="conferencesessiondetails-view"></a>ConferenceSessionDetails-Ansicht
 
In der ConferenceSessionDetails-Ansicht werden Informationen zu Sitzungen mit mehreren Teilnehmern gespeichert. Jeder Datensatz steht für eine Konferenzsitzung, bei der es sich entweder um die Sitzung mit Konferenzzustandsobjekt oder die Sitzung mit einem spezifischen Konferenzserver handelt. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datum/Uhrzeit  <br/> |Zeitpunkt der Sitzungsanforderung. Wird zusammen mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren.. Weitere Informationen finden Sie in der [Dialogs-Tabelle in Skype for Business Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |ID zur Identifikation der Sitzung. Wird zusammen mit SessionIdTime verwendet, um eine Konferenzinstanz eindeutig zu identifizieren. Weitere Informationen finden Sie in der [Dialogs-Tabelle in Skype for Business Server 2015.](dialogs.md) <br/> |
|**InviteTime** <br/> |Datum/Uhrzeit  <br/> |Der Zeitpunkt der ersten INVITE-Anforderung. Dieses Feld wird i. d. R. mit Daten aus der ersten INVITE-Nachricht in der Sitzung gefüllt. Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) gefüllt.  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |Die URI der Konferenz.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Typ des URI. Weitere Informationen finden Sie in der [UriTypes-Tabelle.](uritypes.md) <br/> |
|**ConfInstance** <br/> |Uniqueidentifier  <br/> |ID zur Unterscheidung zwischen einzelnen Instanzen wiederkehrender Konferenzen. Jede wiederkehrende Konferenz weist denselben ConferenceURI, jedoch einen eigenen ConfInstance-Wert auf.  <br/> |
|**McuConferenceUri** <br/> |nvarchar(450)  <br/> |Der URI des Konferenz-Servers.  <br/> |
|**McuConferenceUriType** <br/> |nvarchar(256)  <br/> |Der Typ der Konferenz-Server-URIs. Weitere Informationen finden Sie in der [UriTypes-Tabelle.](uritypes.md) <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |Der URI des Benutzers aus der Sitzung.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Der URI-Typ des Benutzers aus der Sitzung. Weitere Informationen finden Sie in der [UriTypes-Tabelle.](uritypes.md) <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Der Mandant des Benutzers aus der Sitzung. Weitere Informationen finden Sie in der [Tabelle "Mandanten".](tenants.md) <br/> |
|**UserEndpointId** <br/> |Uniqueidentifier  <br/> |Die eindeutige ID des Benutzers aus der Sitzung.  <br/> |
|**EndTime** <br/> |Datum/Uhrzeit  <br/> |Die Endzeit der Sitzung.  <br/> |
|**ConferenceClientVersion** <br/> |nvarchar(256)  <br/> |Die Version des Konferenzservers.  <br/> |
|**ConferenceClientType** <br/> |int  <br/> |Der Typ des Konferenzservers. Weitere Informationen finden Sie in der [UserAgentDef-Tabelle.](useragentdef.md) <br/> |
|**ConferenceCategory** <br/> |nvarchar(64)  <br/> |Die Kategorie des Konferenzservers.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Die Version des Clients für den Benutzer aus der Sitzung.  <br/> |
|**UserClientType** <br/> |int  <br/> |Der Client des Benutzers aus der Sitzung. Weitere Informationen finden Sie in der [UserAgentDef-Tabelle.](useragentdef.md) <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |Der Name der Kategorie für den Client des Benutzers aus der Sitzung.  <br/> |
|**OnBehalfOfUri** <br/> |nvarchar(450)  <br/> |Der URI des Benutzers, in dessen Namen die Sitzung gestartet wurde.  <br/> |
|**OnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |Typ des URI des Benutzers, in dessen Namen die Sitzung gestartet worden ist. Weitere Informationen finden Sie in der [UriTypes-Tabelle.](uritypes.md) <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |Mandant des Benutzers, in dessen Namen die Sitzung gestartet worden ist. Weitere Informationen finden Sie in der [Tabelle "Mandanten".](tenants.md) <br/> |
|**ReferredByUri** <br/> |nvarchar(450)  <br/> |URI des Benutzers, der die Sitzung weitergeleitet hat.  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |Typ des URI des Benutzers, der die Sitzung weitergeleitet hat. Weitere Informationen finden Sie in der [UriTypes-Tabelle.](uritypes.md) <br/> |
|**ReferredByUriTenant** <br/> |nvarchar(256)  <br/> |Mandant des Benutzers, der die Sitzung weitergeleitet hat. Weitere Informationen finden Sie in der [Tabelle "Mandanten".](tenants.md) <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |Die ID des SIP-Dialogs im Format  <br/> :d ialog;from-tag;to-tag  <br/> |
|**ReplaceDialogIdTime** <br/> |Datum/Uhrzeit  <br/> |Die ID-Nummer zum Identifizieren des Dialogs, der durch die aktuelle Sitzung ersetzt wurde. Weitere Informationen finden Sie in der [Dialogs-Tabelle in Skype for Business Server 2015.](dialogs.md) <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Die ID zur Identifizierung der Sitzung. Wird zusammen mit ReplaceDialogIdTime verwendet, um eine Sitzung eindeutig zu identifizieren, die durch diese Sitzung ersetzt wurde. Weitere Informationen finden Sie in der [Dialogs-Tabelle in Skype for Business Server 2015.](dialogs.md) <br/> |
|**ReplacesDialogId** <br/> |varchar(775)  <br/> |Die ID des SIP-Dialogs, der durch die Sitzung ersetzt wird im Format:  <br/> dialog;from-tag;to-tag  <br/> |
|**IsStartedByConfServer** <br/> |Bit  <br/> |Gibt an, ob die Sitzung vom Konferenzserver gestartet wurde.  <br/> |
|**IsEndedByConfServer** <br/> |Bit  <br/> |Gibt an, ob die Sitzung vom Konferenzserver beendet wurde.  <br/> |
|**IsUserInternal** <br/> |Bit  <br/> |Gibt an, ob sich der Benutzer aus dem internen Netzwerk angemeldet hat.  <br/> |
|**ResponseTime** <br/> |Datum/Uhrzeit  <br/> |Zeitpunkt der Antwort auf die erste INVITE-Nachricht. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.  <br/> |
|**ResponseCode** <br/> |int  <br/> |SIP-Antwortcode auf die Sitzungseinladung. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.  <br/> |
|**DiagnosticId** <br/> |int  <br/> |Die Diagnose-ID aus den SIP-Sitzungsheadern.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |Der Inhaltstyp der Sitzung.  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |Vollqualifizierter Domänenname des Front-End-Servers, der die Daten für die Sitzung erfasst hat.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Der FQDN des Pools, der die Daten für die Sitzung erfasst hat.  <br/> |
|**MediationServer** <br/> |nvarchar(256)  <br/> |Der Vermittlungsserver, der vom Benutzer aus der Sitzung verwendet wurde.  <br/> |
|**Gateway** <br/> |nvarchar(256)  <br/> |Das Gateway, das vom Benutzer aus der Sitzung verwendet wurde.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |Der FQDN des Edge-Servers, der vom Benutzer aus der Sitzung verwendet wurde.  <br/> |
|**UserFlag** <br/> |Smallint  <br/> |Gibt die Attribute des Benutzers aus der Sitzung an. Folgende Attributdefinitionen sind zulässig:  <br/> 0x01 - Integriert in Standardtelefon  <br/> |
|**CallFlag** <br/> |Smallint  <br/> |Gibt die Anrufattribute an. Folgende Attributdefinitionen sind zulässig:  <br/> 0x01 - Retried Session0  <br/> x02 - Von Agent getätigter Anruf im Namen einer Reaktionsgruppe  <br/> |
   

