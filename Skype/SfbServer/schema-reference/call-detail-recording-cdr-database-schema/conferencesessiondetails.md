---
title: ConferenceSessionDetails-Ansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5858c84d-baed-421d-ad1d-3726e150e256
description: In der ConferenceSessionDetails-Ansicht werden Informationen zu mehrteiligen Sitzungen gespeichert. Jeder Datensatz stellt eine Konferenzsitzung dar, bei der es sich entweder um die Sitzung mit dem Fokus oder um die Sitzung mit einem bestimmten Konferenzserver handeln kann. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 96eec5450709d4b3fcb9958e387248062febce1b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296413"
---
# <a name="conferencesessiondetails-view"></a>ConferenceSessionDetails-Ansicht
 
In der ConferenceSessionDetails-Ansicht werden Informationen zu mehrteiligen Sitzungen gespeichert. Jeder Datensatz stellt eine Konferenzsitzung dar, bei der es sich entweder um die Sitzung mit dem Fokus oder um die Sitzung mit einem bestimmten Konferenzserver handeln kann. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**SessionID** <br/> |datetime  <br/> |Uhrzeit der Sitzungsanforderung. Wird in Verbindung mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Die ID-Nummer, um die Sitzung zu identifizieren. Wird in Verbindung mit SessionID-Mal verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**Einladen** <br/> |datetime  <br/> |Uhrzeit der ersten INVITE-Anforderung. Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden. Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).  <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> |URI der Konferenz.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Typ des Konferenz-URI. Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |Bezeichner, der zwischen Instanzen von wiederkehrenden Konferenzen unterscheidet. Jede wiederkehrende Konferenz Instanz hat dieselbe ConferenceURI, aber einen anderen ConfInstance-Wert.  <br/> |
|**McuConferenceUri** <br/> |nvarchar (450)  <br/> |URI des Konferenzservers  <br/> |
|**McuConferenceUriType** <br/> |nvarchar(256)  <br/> |Der Typ des Konferenzserver-URIs. Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> |Der URI des an der Sitzung beteiligten Benutzers.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Der Typ des URIs des Benutzers, dessen Teil der Sitzung war. Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Der Mandant des Benutzers, dessen Teil der Sitzung war. Weitere Informationen finden Sie in der [Tabelle Mandanten](tenants.md) . <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |Eindeutiger Bezeichner des Benutzers, dessen Teil der Sitzung war.  <br/> |
|**EndTime** <br/> |datetime  <br/> |Endzeit der Sitzung.  <br/> |
|**ConferenceClientVersion** <br/> |nvarchar(256)  <br/> |Version des Konferenzservers  <br/> |
|**ConferenceClientType** <br/> |int  <br/> |Der Typ des Konferenzservers. Weitere Informationen finden Sie in der [UserAgentDef-Tabelle](useragentdef.md) . <br/> |
|**ConferenceCategory** <br/> |nvarchar (64)  <br/> |Konferenzserver Kategorie.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Die Version des Clients, die von dem Benutzer verwendet wird, der an der Sitzung teilgenommen hat.  <br/> |
|**UserClientType** <br/> |int  <br/> |Der Client, der von dem Benutzer verwendet wird, der an der Sitzung teilgenommen hat. Weitere Informationen finden Sie in der [UserAgentDef-Tabelle](useragentdef.md) . <br/> |
|**UserClientCategory** <br/> |nvarchar (64)  <br/> |Der Name der Kategorie des Clients, der von dem Benutzer verwendet wurde, der Teil der Sitzung war.  <br/> |
|**OnBehalfOfUri** <br/> |nvarchar (450)  <br/> |Der URI des Benutzers, in dessen Auftrag die Sitzung gestartet wurde.  <br/> |
|**OnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |Der Typ des URIs des Benutzers, in dessen Auftrag die Sitzung gestartet wurde. Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |Der Mandant des Benutzers, dessen Namen für die Sitzung gestartet wurde. Weitere Informationen finden Sie in der [Tabelle Mandanten](tenants.md) . <br/> |
|**ReferredByUri** <br/> |nvarchar (450)  <br/> |Der URI des Benutzers, der die Sitzung angewiesen hat.  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |Der Typ des URIs des Benutzers, der die Sitzung angewiesen hat. Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**ReferredByUriTenant** <br/> |nvarchar(256)  <br/> |Der Mandant des Benutzers, der die Sitzung angewiesen hat. Weitere Informationen finden Sie in der [Tabelle Mandanten](tenants.md) . <br/> |
|**Dialogfeld-Nr** <br/> |varstring (775)  <br/> |SIP-Dialogfeld-ID. Das Format ist  <br/> :d ialog; from-Tag; to-Tag  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Die ID-Nummer, die das Dialogfeld identifiziert, das durch die aktuelle Sitzung ersetzt wurde. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Die ID-Nummer, um die Sitzung zu identifizieren. Wird in Verbindung mit ReplaceDialogIdTime verwendet, um eine Sitzung, die durch diese Sitzung ersetzt wird, eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**ReplacesDialogId** <br/> |varchar (775)  <br/> |SIP-Dialog-ID, die die Sitzung ersetzt. Das Format des is:  <br/> Dialogfeld; from-Tag; to-Tag  <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> |Gibt an, ob die Sitzung vom Konferenzserver gestartet wurde.  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> |Gibt an, ob die Sitzung vom Konferenzserver beendet wurde.  <br/> |
|**IsUserInternal** <br/> |bit  <br/> |Gibt an, ob sich der Benutzer vom internen Netzwerk anmeldet.  <br/> |
|**Webantworten** <br/> |datetime  <br/> |Zeitpunkt der Antwort auf die erste Einladungsnachricht. Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden. Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).  <br/> |
|**Response Code** <br/> |int  <br/> |SIP-Antwortcode für die Sitzungseinladung Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden. Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).  <br/> |
|**Diagnose-Nr** <br/> |int  <br/> |Diagnose-ID, die aus Sitzungs-SIP-Headern erfasst wird.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |Inhaltstyp für die Sitzung.  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |FQDN des Front-End-Servers, der die Daten für die Sitzung erfasst hat.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Der FQDN des Pools, in dem die Daten für die Sitzung erfasst wurden.  <br/> |
|**MediationServer** <br/> |nvarchar(256)  <br/> |Vermittlungs Server, der von dem Benutzer verwendet wird, der an der Sitzung teilgenommen hat.  <br/> |
|**Gateway** <br/> |nvarchar(256)  <br/> |Gateway, das vom Benutzer verwendet wird, der an der Sitzung teilgenommen hat.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |Der FQDN des Edge-Servers, der von dem Benutzer verwendet wird, der an der Sitzung teilgenommen hat.  <br/> |
|**UserFlag** <br/> |smallint  <br/> |Gibt die Attribute des Benutzers an, der an der Sitzung teilgenommen hat. Die folgenden Attributdefinitionen sind zulässig:  <br/> 0x01-integriert mit dem Desktoptelefon  <br/> |
|**CallFlag** <br/> |smallint  <br/> |Gibt die anrufattribute an. Die folgenden Attributdefinitionen sind zulässig:  <br/> 0x01 – wiederholte Session0  <br/> x02 – ein Anruf, der von einem Agenten im Auftrag einer Reaktionsgruppe durchgeführt wurde  <br/> |
   

