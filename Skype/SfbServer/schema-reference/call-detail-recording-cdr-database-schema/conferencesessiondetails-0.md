---
title: ConferenceSessionDetails-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
description: Jeder Datensatz steht für eine konferenzsitzung, der die Sitzung mit Konferenzzustandsobjekt oder die Sitzung mit einem spezifischen Konferenzserver werden konnte.
ms.openlocfilehash: ab51ff0c75ba5ea9c6164fdee00be65ff5538c73
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213256"
---
# <a name="conferencesessiondetails-table-in-skype-for-business-server-2015"></a>ConferenceSessionDetails-Tabelle in Skype für Business Server 2015
 
Jeder Datensatz steht für eine konferenzsitzung, der die Sitzung mit Konferenzzustandsobjekt oder die Sitzung mit einem spezifischen Konferenzserver werden konnte.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateTime  <br/> |Primär, Fremd  <br/> |Zeitpunkt der sitzungsanforderung; zusammen mit **SessionIdSeq** verwendet zur eindeutigen Identifizierung eine konferenzsitzung. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primär, Fremd  <br/> |ID-Nummer, um die Sitzung zu identifizieren. In Verbindung mit **SessionIdTime** verwendet, um eine konferenzsitzung eindeutig zu identifizieren. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Ausländisch  <br/> |Konferenz-URI für den Fokus im Zusammenhang mit dieser Sitzung. [ConferenceUris-Tabelle in Skype für Business Server 2015](conferenceuris.md) Weitere Informationen finden Sie. Dieser URI ist ein Konferenzzustandsobjekten basierenden Konferenz-URI. <br/> |
|**ConfInstance** <br/> |uniqueIdentifier  <br/> ||Bezeichner, der zwischen Instanzen von sich wiederholenden Konferenzen unterscheidet. Jede Instanz der wiederkehrende Konferenz hat die gleichen ConferenceURI jedoch ein anderer Wert ConfInstance.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**McuConferenceUriId** <br/> |int  <br/> |Ausländisch  <br/> |Conferencing Server Konferenz URI im Zusammenhang mit dieser Sitzung. [ConferenceUris-Tabelle in Skype für Business Server 2015](conferenceuris.md) Weitere Informationen finden Sie. Dieser URI ist die Conferencing Server-basierten Konferenz-URI. Für den Fokus konferenzsitzungen wird diese Spalte null sein. <br/> |
|**Benutzer-ID** <br/> |int  <br/> |Ausländisch  <br/> |Die ID eines Benutzers in der Sitzung. Finden Sie in der [Tabelle Benutzer](users.md) Weitere Informationen. <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> ||Eine GUID zum Identifizieren der Instanz des Endpunkts. Beispielsweise wenn ein Benutzer auf verschiedenen Computern mit demselben Konto anmeldet, wird dann jedes Computers eine anderen Endpunkt-ID aufweisen.  <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Ausländisch  <br/> |Gibt die ID des Benutzers, die der Anrufer in Namen ist. Finden Sie in der [Tabelle Benutzer](users.md) Weitere Informationen. <br/> |
|**ReferredById** <br/> |int  <br/> |Ausländisch  <br/> |ID des Benutzers, die der Anruf verweist. Finden Sie in der [Tabelle Benutzer](users.md) Weitere Informationen. <br/> |
|**UserClientVersionId** <br/> |int  <br/> |Ausländisch  <br/> |Clientversion des Benutzers Konferenz. [ClientVersions-Tabelle in Skype für Business Server 2015](clientversions.md) Weitere Informationen finden Sie. <br/> |
|**ConfClientVersionId** <br/> |int  <br/> |Ausländisch  <br/> |Clientversion vom Konferenzserver verwendet werden. [ClientVersions-Tabelle in Skype für Business Server 2015](clientversions.md) Weitere Informationen finden Sie. <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Ausländisch  <br/> |ID-Nummer im Dialogfeld bestimmt, die durch die aktuelle Sitzung ausgetauscht wurde. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Ausländisch  <br/> |ID-Nummer, um die Sitzung zu identifizieren. In Verbindung mit **ReplacesDialogIdTime** verwendet, um eine Sitzung eindeutig zu identifizieren, die von dieser Sitzung ersetzt wird. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> ||Gibt an, ob die Sitzung gestartet, durch die Conferencing Server hat.  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> ||Gibt an, ob die Sitzung vom Konferenzserver beendet wurde.  <br/> |
|**IsUserInternal** <br/> |bit  <br/> ||Gibt an, ob Benutzer von innerhalb oder nicht angemeldet ist.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Session Initiation Protocol (SIP) Antwortcode auf die sitzungseinladung. In diesem Feld wird in der Regel durch aus der ersten INVITE-Nachricht in der Sitzung generierte Daten aufgefüllt. Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit Datum und Uhrzeit der ersten relevanten SIP-Nachricht (BYE, Abbrechen, Nachricht oder INFO) aufgefüllt.  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||Diagnose-ID vom SIP-Header.  <br/> |
|**ServerId** <br/> |int  <br/> |Ausländisch  <br/> |ID des Front-End-Servers für diese Sitzung verwendet. Finden Sie weitere Informationen der [Server-Tabelle](servers.md) . <br/> |
|**PoolId** <br/> |int  <br/> |Ausländisch  <br/> |ID des Pools, in der die Sitzung erfasst wurde. Finden Sie weitere Informationen der [Pools-Tabelle](pools.md) . <br/> |
|**MediationServerId** <br/> |int  <br/> |Ausländisch  <br/> |Der Vermittlungsserver den Anruf verwendet. Finden Sie weitere Informationen den [MediationServers-Tabelle](mediationservers.md) . <br/> |
|**GatewayId** <br/> |int  <br/> |Ausländisch  <br/> |Das Gateway der Anruf wird verwendet. [Gateways-Tabelle in Skype für Business Server 2015](gateways.md) Weitere Informationen finden Sie. <br/> |
|**EdgeServerId** <br/> |int  <br/> |Ausländisch  <br/> |Der Edge-Server den Anruf verwendet. [EdgeServers-Tabelle in Skype für Business Server 2015](edgeservers.md) Weitere Informationen finden Sie. <br/> |
|**ContentTypeId** <br/> |int  <br/> |Ausländisch  <br/> |Inhaltstyp in der Sitzung verwendet. Finden Sie in der [ContentTypes-Tabelle in Skype für Business Server 2015](contenttypes.md) Weitere Informationen. <br/> |
|**InviteTime** <br/> |datetime  <br/> ||Der Zeitpunkt der ersten INVITE-Anforderung. In diesem Feld wird in der Regel durch aus der ersten INVITE-Nachricht in der Sitzung generierte Daten aufgefüllt. Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit Datum und Uhrzeit der ersten relevanten SIP-Nachricht (BYE, Abbrechen, Nachricht oder INFO) aufgefüllt.  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||Zeitpunkt der ersten SIP-Antwort. In diesem Feld wird in der Regel durch aus der ersten INVITE-Nachricht in der Sitzung generierte Daten aufgefüllt. Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit Datum und Uhrzeit der ersten relevanten SIP-Nachricht (BYE, Abbrechen, Nachricht oder INFO) aufgefüllt.  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||Der Zeitpunkt, wenn die Sitzung beendet wird.  <br/> |
|**UriTypeId** <br/> |tinyint  <br/> |Ausländisch  <br/> |Enthält den Wert des MCU-URI-Typ aus der [UriTypes-Tabelle](uritypes.md). Dieses Feld wird zur Verbesserung der Leistung von Abfragen verwendet.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**UserFlag** <br/> |smallint  <br/> || Ein bit festlegen gibt an, dass die Attribute. Die folgenden Attributdefinitionen werden aufgeführt: <br/>  Mit Desktoptelefon - 1 integriert <br/> |
|**CallFlag** <br/> |smallint  <br/> || Ein bit festlegen gibt an, dass der Anruf Attribute. Die folgenden Attributdefinitionen werden aufgeführt: <br/>  Wiederholungsversuch der Sitzung - 1 <br/> |
|**ZuletztGeändertUm** <br/> |DateTime  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype für Business Server 2015 eingeführt.  <br/> |
   
\*Für die meisten Sitzungen müssen SessionIdSeq den Wert 1. Wenn mehrerer Sitzungen zur selben Zeit gestartet werden, werden die SessionIdSeq für einen 1, für eine andere 2, und so weiter.
  

