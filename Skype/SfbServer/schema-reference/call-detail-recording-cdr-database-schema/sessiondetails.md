---
title: SessionDetails-Tabelle
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
description: Jeder Eintrag steht für eine Peer-zu-Peer-Sitzung, die ein Telefonanruf von VoIP zu VoIP, eine Sofortnachrichtensitzung mit zwei Teilnehmern oder eine andere Art von Sitzung sein kann. Sie können eine Tabellenknüpfung mit der Media-Tabelle durchführen, um die Details der einzelnen Medien zu finden, die an dieser Sitzung beteiligt sind.
ms.openlocfilehash: e7b89dc242fb3e4adec215948915218b579631ef
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863432"
---
# <a name="sessiondetails-table"></a>SessionDetails-Tabelle
 
Jeder Eintrag steht für eine Peer-zu-Peer-Sitzung, die ein Telefonanruf von VoIP zu VoIP, eine Sofortnachrichtensitzung mit zwei Teilnehmern oder eine andere Art von Sitzung sein kann. Sie können eine Tabellenknüpfung mit der [Media-Tabelle](media.md) durchführen, um die Details der einzelnen Medien zu finden, die an dieser Sitzung beteiligt sind.
  
Beachten Sie, dass die Felder "IsUser1IntegratedWithDeskPhone" und "IsUser2IntegratedWithDeskPhone" aus der SessionDetails-Tabelle gelöscht wurden, die in Skype for Business Server 2015 verwendet wurde.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datum/Uhrzeit  <br/> |Primär, Fremd  <br/> |Zeitpunkt der Sitzungsanforderung. Wird zusammen mit **SessionIdSeq** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie in der [Dialogs-Tabelle in Skype for Business Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primär, Fremd  <br/> |ID zur Identifikation der Sitzung. Wird in Verbindung mit **SessionIdTime** verwendet, um eine Sitzung eindeutig zu identifizieren.* Weitere Informationen finden Sie in der [Dialogs-Tabelle in Skype for Business Server 2015.](dialogs.md) <br/> |
|**Correlationid** <br/> |Uniqueidentifier  <br/> ||Ein GUID für die Korrelation mehrerer Sitzungen.  <br/> |
|**ReplaceDialogIdTime** <br/> |Datum/Uhrzeit  <br/> |Ausländisch  <br/> |ID zur Identifikation des Dialogs, der durch die aktuelle Sitzung ersetzt wurde. Weitere Informationen finden Sie in der [Dialogs-Tabelle in Skype for Business Server 2015.](dialogs.md) <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Ausländisch  <br/> |ID zur Identifikation der Sitzung. Wird zusammen mit **ReplacesDialogIdTime** verwendet, um eine Sitzung eindeutig zu identifizieren, die durch diese Sitzung ersetzt wurde. Weitere Informationen finden Sie in der [Dialogs-Tabelle in Skype for Business Server 2015.](dialogs.md) <br/> |
|**User1Id** <br/> |int  <br/> |Ausländisch  <br/> |ID eines Benutzers in der Sitzung. Weitere Informationen finden Sie in der [Tabelle "Benutzer".](users.md) <br/> |
|**User2Id** <br/> |int  <br/> |Ausländisch  <br/> |ID des anderen Benutzers in der Sitzung. Weitere Informationen finden Sie in der [Tabelle "Benutzer".](users.md) <br/> |
|**User1EndpointId** <br/> |Uniqueidentifier  <br/> ||GUID, die den Endpunkt angibt, der vom ersten Benutzer in der Sitzung verwendet wird.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**User2EndpointId** <br/> |Uniqueidentifier  <br/> ||GUID, die den Endpunkt angibt, der vom zweiten Benutzer in der Sitzung verwendet wird.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**TargetUserId** <br/> |int  <br/> |Ausländisch  <br/> |Der ursprüngliche „An Benutzer“-URI in der SIP-Anforderung. Weitere Informationen finden Sie in der [Tabelle "Benutzer".](users.md) <br/> |
|**SessionStartedById** <br/> |int  <br/> |Ausländisch  <br/> |ID des Benutzers, der die Sitzung gestartet hat. Weitere Informationen finden Sie in der [Tabelle "Benutzer".](users.md) <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Ausländisch  <br/> |Gibt die ID des Benutzers an, der durch den Anrufer vertreten wird. Weitere Informationen finden Sie in der [Tabelle "Benutzer".](users.md) <br/> |
|**ReferredById** <br/> |int  <br/> |Ausländisch  <br/> |ID des Benutzers, der den Anruf weiterleitet. Weitere Informationen finden Sie in der [Tabelle "Benutzer".](users.md) <br/> |
|**ServerId** <br/> |int  <br/> |Ausländisch  <br/> |ID des für diese Sitzung verwendeten Front-End-Servers. Weitere Informationen finden Sie in der [Tabelle "Server".](servers.md) <br/> |
|**PoolId** <br/> |int  <br/> |Ausländisch  <br/> |ID des Pools, in dem die Sitzung erfasst wurde. Weitere Informationen finden Sie in der [Tabelle "Pools".](pools.md) <br/> |
|**ContentTypeID** <br/> |int  <br/> |Ausländisch  <br/> |In der Sitzung verwendeter Inhaltstyp. Weitere Informationen finden Sie in der [ContentTypes-Tabelle in Skype for Business Server 2015.](contenttypes.md) <br/> |
|**User1ClientVerId** <br/> |int  <br/> |Ausländisch  <br/> |Von Benutzer1 verwendete Clientversion. Weitere Informationen finden Sie in der [Tabelle "ClientVersions" in Skype for Business Server 2015.](clientversions.md) <br/> |
|**User2ClientVerId** <br/> |int  <br/> |Ausländisch  <br/> |Von Benutzer2 verwendete Clientversion. Weitere Informationen finden Sie in der [Tabelle "ClientVersions" in Skype for Business Server 2015.](clientversions.md) <br/> |
|**User1EdgeServerid** <br/> |int  <br/> |Ausländisch  <br/> |Von Benutzer1 verwendeter Edgeserver. Weitere Informationen finden Sie in der [EdgeServers-Tabelle in Skype for Business Server 2015.](edgeservers.md) <br/> |
|**User2EdgeServerid** <br/> |int  <br/> |Ausländisch  <br/> |Von Benutzer2 verwendeter Edgeserver. Weitere Informationen finden Sie in der [EdgeServers-Tabelle in Skype for Business Server 2015.](edgeservers.md) <br/> |
|**IsUser1Internal** <br/> |Bit  <br/> ||Gibt an, ob Benutzer1 ein interner oder externer Benutzer ist.  <br/> |
|**IsUser2Internal** <br/> |Bit  <br/> ||Gibt an, ob Benutzer2 ein interner oder externer Benutzer ist.  <br/> |
|**InviteTime** <br/> |Datum/Uhrzeit  <br/> ||Die Uhrzeit der ersten INVITE-Anforderung. Dieses Feld wird in der Regel durch Daten gefüllt, die aus der ersten INVITE-Nachricht in der Sitzung erzeugt werden. Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit Datum und Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt. Dieses Feld wird normalerweise von Daten aufgefüllt, die von der ursprünglichen INVITE-Nachricht in der Sitzung generiert werden. Falls keine INVITE-Nachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (BYE, CANCEL, MESSAGE oder INFO).  <br/> |
|**ResponseTime** <br/> |Datum/Uhrzeit  <br/> ||Die Zeit bis zur Antwort auf die erste INVITE-Anforderung. Dieses Feld wird normalerweise von Daten aufgefüllt, die von der ursprünglichen INVITE-Nachricht in der Sitzung generiert werden. Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit Datum und Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||SIP-Antwortcode auf die Sitzungseinladung. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||Vom SIP-Header erfasste Diagnose-ID.  <br/> |
|**CallPriority** <br/> |int  <br/> |Ausländisch  <br/> |Anrufpriorität. Weitere Informationen finden Sie in der [CallPriorities-Tabelle in Skype for Business Server 2015.](callpriorities.md) <br/> |
|**User1MessageCount** <br/> |int  <br/> ||Anzahl der von Benutzer1 während der Sitzung gesendeten Nachrichten.  <br/> |
|**User2MessageCount** <br/> |int  <br/> ||Anzahl der von Benutzer2 während der Sitzung gesendeten Nachrichten.  <br/> |
|**SessionEndTime** <br/> |Datum/Uhrzeit  <br/> ||Uhrzeit am Ende der Sitzung.  <br/> |
|**MediaTypes** <br/> |int  <br/> ||Ein Bit-Satz, der den Medientyp dieser Sitzung angibt. Die Definitionen folgender Typen sind aufgeführt:  <br/> 1- Chat  <br/> 2- FILE_TRANSFER  <br/> 4- REMOTE_ASSISTANCE  <br/> 8- APP_SHARING  <br/> 16- AUDIO  <br/> 32- VIDEO  <br/> 64- APP_INVITE  <br/> |
|**User1Flag** <br/> |Smallint  <br/> ||Ein Bit-Satz, der die Attribute von Benutzer1 angibt. Die Definitionen folgender Typen sind aufgeführt:  <br/> 0x01 – Mit Desktoptelefon integriert  <br/> |
|**User2Flag** <br/> |Smallint  <br/> ||Ein Bit-Satz, der die Attribute von Benutzer2 angibt. Die Definitionen folgender Typen sind aufgeführt:  <br/> 0x01 – Mit Desktoptelefon integriert  <br/> |
|**CallFlag** <br/> |Smallint  <br/> ||Ein Bit-Satz, der die Anrufattribute angibt. Die Definitionen folgender Attribute sind aufgeführt:  <br/> 0x01 – Wiederholungsversuch der Sitzung  <br/> 0x02 – Von Agent getätigter Anruf im Namen einer Reaktionsgruppe  <br/> |
|**Verarbeitet** <br/> |Bit  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype for Business Server 2015 eingeführt.  <br/> |
   
\* Für die meisten Sitzungen hat SessionIdSeq den Wert 1. Wenn mehrere Sitzungen zum selben Zeitpunkt gestart werden, lautet der Wert für eine Sitzung 1, für eine weitere Sitzung 2, usw.
  

