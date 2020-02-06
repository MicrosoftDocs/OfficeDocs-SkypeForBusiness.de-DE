---
title: ConferenceSessionDetails-Tabelle in Skype for Business Server 2015
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
ms.assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
description: Jeder Datensatz stellt eine Konferenzsitzung dar, bei der es sich entweder um die Sitzung mit dem Fokus oder um die Sitzung mit einem bestimmten Konferenzserver handeln kann.
ms.openlocfilehash: 95cf64589cdcd0fd38b4e29cd4e863c870f2a7a6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815343"
---
# <a name="conferencesessiondetails-table-in-skype-for-business-server-2015"></a>ConferenceSessionDetails-Tabelle in Skype for Business Server 2015
 
Jeder Datensatz stellt eine Konferenzsitzung dar, bei der es sich entweder um die Sitzung mit dem Fokus oder um die Sitzung mit einem bestimmten Konferenzserver handeln kann.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionID** <br/> |DateTime  <br/> |Primär, fremd  <br/> |Uhrzeit der Sitzungsanforderung; wird in Verbindung mit **SessionIdSeq** verwendet, um eine Konferenzsitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primär, fremd  <br/> |Die ID-Nummer, um die Sitzung zu identifizieren. Wird in Verbindung mit **SessionID** -Mal verwendet, um eine Konferenzsitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Fremd  <br/> |Fokus Konferenz-URI, der sich auf diese Sitzung bezieht. Weitere Informationen finden Sie [in der Tabelle ConferenceUris in Skype for Business Server 2015](conferenceuris.md) . Dieser URI ist ein Fokus basierter Konferenz-URI. <br/> |
|**ConfInstance** <br/> |uniqueIdentifier  <br/> ||Bezeichner, der zwischen Instanzen von wiederkehrenden Konferenzen unterscheidet. Jede wiederkehrende Konferenz Instanz hat dieselbe ConferenceURI, aber einen anderen ConfInstance-Wert.  <br/> Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**McuConferenceUriId** <br/> |int  <br/> |Fremd  <br/> |Konferenzserver-Konferenz-URI, der sich auf diese Sitzung bezieht. Weitere Informationen finden Sie [in der Tabelle ConferenceUris in Skype for Business Server 2015](conferenceuris.md) . Dieser URI ist der Konferenz-serverbasierte Konferenz-URI. Für Konferenzsitzungen mit Fokus ist diese Spalte NULL. <br/> |
|**UserID** <br/> |int  <br/> |Fremd  <br/> |Die ID eines Benutzers in der Konferenzsitzung. Weitere Informationen finden Sie in der [Tabelle "Benutzer](users.md) ". <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> ||Eine GUID zum Identifizieren der Instanz des Endpunkts. Wenn sich ein Benutzer beispielsweise an verschiedenen Computern mit demselben Konto anmeldet, verfügt jeder Computer über eine andere Endpunkt-ID.  <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Fremd  <br/> |Gibt die ID des Benutzers an, der der Anrufer im Auftrag ist. Weitere Informationen finden Sie in der [Tabelle "Benutzer](users.md) ". <br/> |
|**ReferredById** <br/> |int  <br/> |Fremd  <br/> |Die ID des Benutzers, auf den der Anruf verweist. Weitere Informationen finden Sie in der [Tabelle "Benutzer](users.md) ". <br/> |
|**UserClientVersionId** <br/> |int  <br/> |Fremd  <br/> |Vom Konferenzbenutzer verwendete Client Version. Weitere Informationen finden Sie [in der Tabelle ClientVersions in Skype for Business Server 2015](clientversions.md) . <br/> |
|**ConfClientVersionId** <br/> |int  <br/> |Fremd  <br/> |Client Version, die vom Konferenzserver verwendet wird. Weitere Informationen finden Sie [in der Tabelle ClientVersions in Skype for Business Server 2015](clientversions.md) . <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Fremd  <br/> |Die ID-Nummer, die das Dialogfeld identifiziert, das durch die aktuelle Sitzung ersetzt wurde. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Fremd  <br/> |Die ID-Nummer, um die Sitzung zu identifizieren. Wird in Verbindung mit **ReplacesDialogIdTime** verwendet, um eine Sitzung, die durch diese Sitzung ersetzt wird, eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> ||Gibt an, ob die Sitzung vom Konferenz Server gestartet wurde.  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> ||Gibt an, ob die Sitzung vom Konferenzserver beendet wurde.  <br/> |
|**IsUserInternal** <br/> |bit  <br/> ||Ob der Benutzer intern angemeldet ist oder nicht.  <br/> |
|**Response Code** <br/> |int  <br/> ||SIP-Antwortcode (Session Initiation Protocol) für die Sitzungseinladung Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden. Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).  <br/> |
|**Diagnose-Nr** <br/> |int  <br/> ||Vom SIP-Header erfasste Diagnose-ID.  <br/> |
|**ServerID** <br/> |int  <br/> |Fremd  <br/> |Die ID des für diese Sitzung verwendeten Front-End-Servers. Weitere Informationen finden Sie in der [Tabelle Server](servers.md) . <br/> |
|**Pool-Nr** <br/> |int  <br/> |Fremd  <br/> |Die ID des Pools, in dem die Sitzung erfasst wurde. Weitere Informationen finden Sie in der [Tabelle Pools](pools.md) . <br/> |
|**MediationServerId** <br/> |int  <br/> |Fremd  <br/> |Der Vermittlungs Server, den der Anruf verwendet. Weitere Informationen finden Sie in der [MediationServers-Tabelle](mediationservers.md) . <br/> |
|**Gatewayserver** <br/> |int  <br/> |Fremd  <br/> |Das Gateway, das der Anruf verwendet. Weitere Informationen finden Sie [in der Tabelle Gateways in Skype for Business Server 2015](gateways.md) . <br/> |
|**EdgeServerId** <br/> |int  <br/> |Fremd  <br/> |Der Edge-Server, den der Anruf verwendet. Weitere Informationen finden Sie [in der Tabelle EdgeServers in Skype for Business Server 2015](edgeservers.md) . <br/> |
|**ContentTypeID** <br/> |int  <br/> |Fremd  <br/> |Inhaltstyp, der in der Sitzung verwendet wird. Weitere Informationen finden Sie [in der Tabelle "ContentTypes" in Skype for Business Server 2015](contenttypes.md) . <br/> |
|**Einladen** <br/> |datetime  <br/> ||Der Zeitpunkt der ersten INVITE-Anforderung. Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden. Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).  <br/> |
|**Webantworten** <br/> |datetime  <br/> ||Zeitpunkt der ersten SIP-Antwort. Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden. Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||Der Zeitpunkt, zu dem die Sitzung beendet wird.  <br/> |
|**UriTypeId** <br/> |tinyint  <br/> |Fremd  <br/> |Enthält den Wert des MCU-URI-Typs aus der [UriTypes-Tabelle](uritypes.md). Dieses Feld wird verwendet, um die Abfrageleistung zu verbessern.  <br/> Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**UserFlag** <br/> |smallint  <br/> || Ein Bit-Satz, der die Benutzerattribute angibt. Die folgenden Attributdefinitionen werden aufgelistet: <br/>  Integriert mit dem Desktop-Telefon-1 <br/> |
|**CallFlag** <br/> |smallint  <br/> || Ein Bit-Satz, der die anrufattribute angibt. Die folgenden Attributdefinitionen werden aufgelistet: <br/>  Wiederholte Sitzung – 1 <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype for Business Server 2015 eingeführt.  <br/> |
   
\*Bei den meisten Sitzungen erhält SessionIdSeq den Wert 1. Wenn mehrere Sitzungen genau zur gleichen Zeit beginnen, ist der SessionIdSeq für einen 1, für einen anderen wird 2 usw.
  

