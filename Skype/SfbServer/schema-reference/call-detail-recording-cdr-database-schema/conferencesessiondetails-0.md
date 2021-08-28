---
title: ConferenceSessionDetails-Tabelle in Skype for Business Server 2015
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
ms.localizationpriority: medium
ms.assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
description: Jeder Datensatz steht für eine Konferenzsitzung, bei der es sich entweder um die Sitzung mit Konferenzzustandsobjekt oder die Sitzung mit einem spezifischen Konferenzserver handelt.
ms.openlocfilehash: e64f1d93714a89c8140d4e8f55d6aab8076ed88c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615551"
---
# <a name="conferencesessiondetails-table-in-skype-for-business-server-2015"></a>ConferenceSessionDetails-Tabelle in Skype for Business Server 2015
 
Jeder Datensatz steht für eine Konferenzsitzung, bei der es sich entweder um die Sitzung mit Konferenzzustandsobjekt oder die Sitzung mit einem spezifischen Konferenzserver handelt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datetime  <br/> |Primär, Fremd  <br/> |Zeitpunkt der Sitzungsanforderung; wird zusammen mit **SessionIdSeq** verwendet, um eine Konferenzsitzung eindeutig zu identifizieren. Weitere Informationen finden Sie in der [Dialogs-Tabelle in Skype for Business Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primär, Fremd  <br/> |ID zur Identifikation der Sitzung. Wird in Verbindung mit **SessionIdTime** verwendet, um eine Konferenzsitzung eindeutig zu identifizieren. Weitere Informationen finden Sie in der [Dialogs-Tabelle in Skype for Business Server 2015.](dialogs.md) * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Ausländisch  <br/> |Konferenz-URI mit Konferenzzustandsobjekt für diese Sitzung. Weitere Informationen finden Sie in der [ConferenceUris-Tabelle in Skype for Business Server 2015.](conferenceuris.md) Dieser URI ist ein auf dem Konferenzzustandsobjekt basierter Konferenz-URI. <br/> |
|**ConfInstance** <br/> |Uniqueidentifier  <br/> ||ID zur Unterscheidung zwischen einzelnen Instanzen wiederkehrender Konferenzen. Jede wiederkehrende Konferenz weist denselben ConferenceURI, jedoch einen eigenen ConfInstance-Wert auf.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**McuConferenceUriId** <br/> |int  <br/> |Ausländisch  <br/> |Konferenz-URI des Konferenzservers für diese Sitzung. Weitere Informationen finden Sie in der [ConferenceUris-Tabelle in Skype for Business Server 2015.](conferenceuris.md) Dieser URI ist der konferenzserverbasierte Konferenz-URI. Bei Konferenzsitzungen mit Konferenzzustandsobjekt ist diese Spalte NULL. <br/> |
|**UserId** <br/> |int  <br/> |Ausländisch  <br/> |ID eines Benutzers in der Konferenzsitzung. Weitere Informationen finden Sie in der [Tabelle "Benutzer".](users.md) <br/> |
|**UserEndpointId** <br/> |Uniqueidentifier  <br/> ||Eine GUID zur Identifikation der Instanz des Endpunkts. Wenn sich beispielsweise ein Benutzer auf verschiedenen Computern über dasselbe Konto anmeldet, erhält jeder Computer eine andere Endpunkt-ID.  <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Ausländisch  <br/> |Gibt die ID des Benutzers an, der durch den Anrufer vertreten wird. Weitere Informationen finden Sie in der [Tabelle "Benutzer".](users.md) <br/> |
|**ReferredById** <br/> |int  <br/> |Ausländisch  <br/> |ID des Benutzers, der den Anruf weiterleitet. Weitere Informationen finden Sie in der [Tabelle "Benutzer".](users.md) <br/> |
|**UserClientVersionId** <br/> |int  <br/> |Ausländisch  <br/> |Clientversion, die vom Konferenzbenutzer verwendet wird. Weitere Informationen finden Sie in der [Tabelle "ClientVersions" in Skype for Business Server 2015.](clientversions.md) <br/> |
|**ConfClientVersionId** <br/> |int  <br/> |Ausländisch  <br/> |Clientversion, die vom Konferenzserver verwendet wird. Weitere Informationen finden Sie in der [Tabelle "ClientVersions" in Skype for Business Server 2015.](clientversions.md) <br/> |
|**ReplaceDialogIdTime** <br/> |Datum/Uhrzeit  <br/> |Ausländisch  <br/> |ID zur Identifikation des Dialogs, der durch die aktuelle Sitzung ersetzt wurde. Weitere Informationen finden Sie in der [Dialogs-Tabelle in Skype for Business Server 2015.](dialogs.md) <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Ausländisch  <br/> |ID zur Identifikation der Sitzung. Wird zusammen mit **ReplacesDialogIdTime** verwendet, um eine Sitzung eindeutig zu identifizieren, die durch diese Sitzung ersetzt wurde. Weitere Informationen finden Sie in der [Dialogs-Tabelle in Skype for Business Server 2015.](dialogs.md) <br/> |
|**IsStartedByConfServer** <br/> |Bit  <br/> ||Zeigt an, ob die Sitzung durch den A/V-Konferenzserver gestartet wurde.  <br/> |
|**IsEndedByConfServer** <br/> |Bit  <br/> ||Zeigt an, ob die Sitzung durch den Konferenzserver beendet wurde.  <br/> |
|**IsUserInternal** <br/> |Bit  <br/> ||Tatsache, ob die Anmeldung des Benutzers intern erfolgte oder nicht.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||SIP-Antwortcode (Session Initiation Protocol) auf die Sitzungseinladung. Dieses Feld wird in der Regel durch Daten gefüllt, die aus der ersten INVITE-Nachricht in der Sitzung erzeugt werden. Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit Datum und Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||Diagnose-ID aus dem SIP-Header.  <br/> |
|**ServerId** <br/> |int  <br/> |Ausländisch  <br/> |ID des für diese Sitzung verwendeten Front-End-Servers. Weitere Informationen finden Sie in der [Tabelle "Server".](servers.md) <br/> |
|**PoolId** <br/> |int  <br/> |Ausländisch  <br/> |ID des Pools, in dem die Sitzung erfasst wurde. Weitere Informationen finden Sie in der [Tabelle "Pools".](pools.md) <br/> |
|**MediationServerId** <br/> |int  <br/> |Ausländisch  <br/> |Der für den Anruf verwendete Vermittlungsserver. Weitere Informationen finden Sie in der [MediationServers-Tabelle.](mediationservers.md) <br/> |
|**GatewayId** <br/> |int  <br/> |Ausländisch  <br/> |Das vom Anruf verwendete Gateway. Weitere Informationen finden Sie in der [Gateways-Tabelle in Skype for Business Server 2015.](gateways.md) <br/> |
|**EdgeServerId** <br/> |int  <br/> |Ausländisch  <br/> |Der vom Anruf verwendete Edgeserver. Weitere Informationen finden Sie in der [EdgeServers-Tabelle in Skype for Business Server 2015.](edgeservers.md) <br/> |
|**ContentTypeId** <br/> |int  <br/> |Ausländisch  <br/> |In der Sitzung verwendeter Inhaltstyp. Weitere Informationen finden Sie in der [ContentTypes-Tabelle in Skype for Business Server 2015.](contenttypes.md) <br/> |
|**InviteTime** <br/> |Datum/Uhrzeit  <br/> ||Die Uhrzeit der ersten INVITE-Anforderung. Dieses Feld wird in der Regel durch Daten gefüllt, die aus der ersten INVITE-Nachricht in der Sitzung erzeugt werden. Falls keine INVITE-Nachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (BYE, CANCEL, MESSAGE oder INFO).  <br/> |
|**ResponseTime** <br/> |Datum/Uhrzeit  <br/> ||Die Uhrzeit der ersten SIP RESPONSE. Dieses Feld wird in der Regel durch Daten gefüllt, die aus der ersten INVITE-Nachricht in der Sitzung erzeugt werden. Falls keine INVITE-Nachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (BYE, CANCEL, MESSAGE oder INFO).  <br/> |
|**SessionEndTime** <br/> |Datum/Uhrzeit  <br/> ||Der Zeitpunkt des Sitzungsendes.  <br/> |
|**UriTypeId** <br/> |Tinyint  <br/> |Ausländisch  <br/> |Enthält den MCU-URI-Typwert aus der [UriTypes-Tabelle.](uritypes.md) Dieses Feld dient zur Verbesserung der Abfrageleistung.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**UserFlag** <br/> |Smallint  <br/> || Ein Bitsatz, der die Benutzerattribute angibt. Die folgenden Attributdefinitionen werden aufgeführt: <br/>  Integrated with desktop phone - 1 <br/> |
|**CallFlag** <br/> |Smallint  <br/> || Ein Bitsatz, der die Anrufattribute angibt. Die folgenden Attributdefinitionen werden aufgeführt: <br/>  Retried Session - 1 <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype for Business Server 2015 eingeführt.  <br/> |
   
\* Für die meisten Sitzungen hat SessionIdSeq den Wert 1. Wenn mehrere Sitzungen zum selben Zeitpunkt gestart werden, lautet der Wert für eine Sitzung 1, für eine weitere Sitzung 2, usw.
  

