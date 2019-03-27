---
title: SessionDetails-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
description: Jeder Datensatz steht für eine Peer-zu-Peer-Sitzung, die VoIP-VoIP-Anruf, zwei Teilnehmern Sofortnachrichtensitzung oder andere Art von Sitzung sein könnten. Bei der Durchführung einer Tabelle Verknüpfung mit der Tabelle Media, die Details der einzelnen Medien in dieser Sitzung zu erhalten.
ms.openlocfilehash: e499c8d443742bacfcdbe9c129e884cae4dd96a0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889924"
---
# <a name="sessiondetails-table"></a>SessionDetails-Tabelle
 
Jeder Datensatz steht für eine Peer-zu-Peer-Sitzung, die VoIP-VoIP-Anruf, zwei Teilnehmern Sofortnachrichtensitzung oder andere Art von Sitzung sein könnten. Bei der Durchführung einer Tabelle Verknüpfung mit der [Media-Tabelle](media.md) , die Details der einzelnen Medien in dieser Sitzung zu erhalten.
  
Beachten Sie, dass die IsUser1IntegratedWithDeskPhone und die IsUser2IntegratedWithDeskPhone Felder aus der SessionDetails-Tabelle in Skype für Business Server 2015 verwendet gelöscht worden sein.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primär, Fremd  <br/> |Zeitpunkt der sitzungsanforderung. Zusammen mit **SessionIdSeq** verwendet zur eindeutigen Identifizierung eine Sitzung. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primär, Fremd  <br/> |ID-Nummer, um die Sitzung zu identifizieren. In Verbindung mit **SessionIdTime** verwendet, um eine session.* der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen finden Sie unter eindeutig zu identifizieren. <br/> |
|**CorrelationId** <br/> |uniqueidentifier  <br/> ||Eine GUID zum Korrelieren mehrerer Sitzungen.  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Ausländisch  <br/> |ID-Nummer im Dialogfeld bestimmt, die durch die aktuelle Sitzung ausgetauscht wurde. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Ausländisch  <br/> |ID-Nummer, um die Sitzung zu identifizieren. In Verbindung mit **ReplacesDialogIdTime** verwendet, um eine Sitzung eindeutig zu identifizieren, die von dieser Sitzung ersetzt wird. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**User1Id** <br/> |int  <br/> |Ausländisch  <br/> |Die ID eines Benutzers in der Sitzung. Finden Sie in der [Tabelle Benutzer](users.md) Weitere Informationen. <br/> |
|**User2Id** <br/> |int  <br/> |Ausländisch  <br/> |ID des Benutzers in der Sitzung. Finden Sie in der [Tabelle Benutzer](users.md) Weitere Informationen. <br/> |
|**User1EndpointId** <br/> |uniqueIdentifier  <br/> ||GUID, den Endpunkt des ersten Benutzers in der Sitzung identifiziert.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**User2EndpointId** <br/> |uniqueIdentifier  <br/> ||GUID, den vom zweiten Benutzer in der Sitzung verwendeten Endpunkt identifiziert.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**TargetUserId** <br/> |int  <br/> |Ausländisch  <br/> |Die ursprüngliche an Benutzer-URI in der SIP-Anforderung. finden Sie in der [Tabelle Benutzer](users.md) Weitere Informationen. <br/> |
|**SessionStartedById** <br/> |int  <br/> |Ausländisch  <br/> |ID des Benutzers, der die Sitzung gestartet hat. Finden Sie in der [Tabelle Benutzer](users.md) Weitere Informationen. <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Ausländisch  <br/> |Gibt die ID des Benutzers, die der Anrufer in Namen ist. Finden Sie in der [Tabelle Benutzer](users.md) Weitere Informationen. <br/> |
|**ReferredById** <br/> |int  <br/> |Ausländisch  <br/> |ID des Benutzers, die der Anruf verweist. Finden Sie in der [Tabelle Benutzer](users.md) Weitere Informationen. <br/> |
|**ServerId** <br/> |int  <br/> |Ausländisch  <br/> |ID des Front-End-Servers für diese Sitzung verwendet. Finden Sie weitere Informationen der [Server-Tabelle](servers.md) . <br/> |
|**PoolId** <br/> |int  <br/> |Ausländisch  <br/> |ID des Pools, in der die Sitzung erfasst wurde. Finden Sie weitere Informationen der [Pools-Tabelle](pools.md) . <br/> |
|**ContentTypeID** <br/> |int  <br/> |Ausländisch  <br/> |Inhaltstyp in der Sitzung verwendet. Finden Sie in der [ContentTypes-Tabelle in Skype für Business Server 2015](contenttypes.md) Weitere Informationen. <br/> |
|**User1ClientVerId** <br/> |int  <br/> |Ausländisch  <br/> |Clientversion von User1 verwendet. [ClientVersions-Tabelle in Skype für Business Server 2015](clientversions.md) Weitere Informationen finden Sie. <br/> |
|**User2ClientVerId** <br/> |int  <br/> |Ausländisch  <br/> |Clientversion von Benutzer2 verwendet. [ClientVersions-Tabelle in Skype für Business Server 2015](clientversions.md) Weitere Informationen finden Sie. <br/> |
|**User1EdgeServerid** <br/> |int  <br/> |Ausländisch  <br/> |Edge-Server von User1 verwendet. [EdgeServers-Tabelle in Skype für Business Server 2015](edgeservers.md) Weitere Informationen finden Sie. <br/> |
|**User2EdgeServerid** <br/> |int  <br/> |Ausländisch  <br/> |Edge-Server von Benutzer2 verwendet. [EdgeServers-Tabelle in Skype für Business Server 2015](edgeservers.md) Weitere Informationen finden Sie. <br/> |
|**IsUser1Internal** <br/> |bit  <br/> ||Gibt an, ob Benutzer1 aus internen oder nicht angemeldet ist.  <br/> |
|**IsUser2Internal** <br/> |bit  <br/> ||Gibt an, ob Benutzer2 aus internen oder nicht angemeldet ist.  <br/> |
|**InviteTime** <br/> |datetime  <br/> ||Der Zeitpunkt der ersten INVITE-Anforderung. In diesem Feld wird in der Regel durch aus der ersten INVITE-Nachricht in der Sitzung generierte Daten aufgefüllt. Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit Datum und Uhrzeit der ersten relevanten SIP-Nachricht (BYE, Abbrechen, Nachricht oder INFO) aufgefüllt. In diesem Feld wird in der Regel durch aus der ersten INVITE-Nachricht in der Sitzung generierte Daten aufgefüllt. Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit Datum und Uhrzeit der ersten relevanten SIP-Nachricht (BYE, Abbrechen, Nachricht oder INFO) aufgefüllt.  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||Der Zeitpunkt der Antwort auf die erste INVITE-Nachricht. In diesem Feld wird in der Regel durch aus der ersten INVITE-Nachricht in der Sitzung generierte Daten aufgefüllt. Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit Datum und Uhrzeit der ersten relevanten SIP-Nachricht (BYE, Abbrechen, Nachricht oder INFO) aufgefüllt.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||SIP-Antwortcode auf die sitzungseinladung. In diesem Feld wird in der Regel durch aus der ersten INVITE-Nachricht in der Sitzung generierte Daten aufgefüllt. Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit Datum und Uhrzeit der ersten relevanten SIP-Nachricht (BYE, Abbrechen, Nachricht oder INFO) aufgefüllt.  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||Diagnose-ID vom SIP-Header.  <br/> |
|**CallPriority** <br/> |int  <br/> |Ausländisch  <br/> |Rufen Sie die Priorität. [CallPriorities-Tabelle in Skype für Business Server 2015](callpriorities.md) Weitere Informationen finden Sie. <br/> |
|**User1MessageCount** <br/> |int  <br/> ||Anzahl der von Benutzer1 während der Sitzung gesendeten Nachrichten.  <br/> |
|**User2MessageCount** <br/> |int  <br/> ||Anzahl der von Benutzer2 während der Sitzung gesendeten Nachrichten.  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||Uhrzeit am Ende der Sitzung.  <br/> |
|**MediaTypes** <br/> |int  <br/> ||Ein bit festlegen gibt an, dass der Medientyp dieser Sitzung. Aufgelistet sind die Definitionen der Typen:  <br/> 1 – SOFORTNACHRICHTEN  <br/> 2 - FILE_TRANSFER  <br/> 4 - REMOTE_ASSISTANCE  <br/> 8 - APP_SHARING  <br/> 16 - AUDIO  <br/> 32 - VIDEO  <br/> 64 - APP_INVITE  <br/> |
|**User1Flag** <br/> |smallint  <br/> ||Ein bit festlegen gibt an, dass die User1 Attribute. Die folgenden Attributdefinitionen werden aufgeführt:  <br/> 0 x 01 – mit Desktoptelefon integriert  <br/> |
|**User2Flag** <br/> |smallint  <br/> ||Ein bit festlegen gibt an, dass die Attribute Benutzer2. Die folgenden Attributdefinitionen werden aufgeführt:  <br/> 0 x 01 – mit Desktoptelefon integriert  <br/> |
|**CallFlag** <br/> |smallint  <br/> ||Ein bit festlegen gibt an, dass der Anruf Attribute. Die folgenden Attributdefinitionen werden aufgeführt:  <br/> 0 x 01 – Wiederholungsversuch der Sitzung  <br/> 0 x 02 - ein vom Agent im Namen einer reaktionsgruppe getätigter Anruf  <br/> |
|**Verarbeitet** <br/> |bit  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ZuletztGeändertUm** <br/> |DateTime  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype für Business Server 2015 eingeführt.  <br/> |
   
\*Für die meisten Sitzungen müssen SessionIdSeq den Wert 1. Wenn mehrerer Sitzungen zur selben Zeit gestartet werden, werden die SessionIdSeq für einen 1, für eine andere 2, und so weiter.
  

