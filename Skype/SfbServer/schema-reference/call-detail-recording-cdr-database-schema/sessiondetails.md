---
title: SessionDetails-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
description: Jeder Datensatz stellt eine Peer-to-Peer-Sitzung dar, bei der es sich um einen VoIP-VoIP-Telefonanruf, eine Chatsitzung mit zwei Teilnehmern oder eine andere Art von Sitzung handeln kann. Sie können eine Tabellen Verknüpfung mit der Medientabelle durchführen, um die Details der einzelnen Medien zu finden, die an dieser Sitzung beteiligt sind.
ms.openlocfilehash: d6c0d68cf5b8efd83cc764e74a56621cdd591ac1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295804"
---
# <a name="sessiondetails-table"></a>SessionDetails-Tabelle
 
Jeder Datensatz stellt eine Peer-to-Peer-Sitzung dar, bei der es sich um einen VoIP-VoIP-Telefonanruf, eine Chatsitzung mit zwei Teilnehmern oder eine andere Art von Sitzung handeln kann. Sie können eine Tabellen Verknüpfung mit der [Medientabelle](media.md) durchführen, um die Details der einzelnen Medien zu finden, die an dieser Sitzung beteiligt sind.
  
Beachten Sie, dass die Felder IsUser1IntegratedWithDeskPhone und IsUser2IntegratedWithDeskPhone aus der SessionDetails-Tabelle gelöscht wurden, die in Skype for Business Server 2015 verwendet wurde.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionID** <br/> |datetime  <br/> |Primär, fremd  <br/> |Uhrzeit der Sitzungsanforderung. Wird in Verbindung mit **SessionIdSeq** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primär, fremd  <br/> |Die ID-Nummer, um die Sitzung zu identifizieren. Wird in Verbindung mit **SessionID** -Mal verwendet, um eine Sitzung eindeutig zu identifizieren. * Weitere Informationen finden Sie [in der Tabelle "Dialogfelder" in Skype for Business Server 2015](dialogs.md) . <br/> |
|**CorrelationId** <br/> |uniqueidentifier  <br/> ||Eine GUID zum Korrelieren mehrerer Sitzungen.  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Fremd  <br/> |Die ID-Nummer, die das Dialogfeld identifiziert, das durch die aktuelle Sitzung ersetzt wurde. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Fremd  <br/> |Die ID-Nummer, um die Sitzung zu identifizieren. Wird in Verbindung mit **ReplacesDialogIdTime** verwendet, um eine Sitzung, die durch diese Sitzung ersetzt wird, eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**Benutzer1** <br/> |int  <br/> |Fremd  <br/> |Die ID eines Benutzers in der Sitzung. Weitere Informationen finden Sie in der [Tabelle "Benutzer](users.md) ". <br/> |
|**User2Id** <br/> |int  <br/> |Fremd  <br/> |Die ID des anderen Benutzers in der Sitzung. Weitere Informationen finden Sie in der [Tabelle "Benutzer](users.md) ". <br/> |
|**User1EndpointId** <br/> |uniqueIdentifier  <br/> ||GUID, die den vom ersten Benutzer in der Sitzung verwendeten Endpunkt identifiziert.  <br/> Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**User2EndpointId** <br/> |uniqueIdentifier  <br/> ||GUID, die den vom zweiten Benutzer in der Sitzung verwendeten Endpunkt identifiziert.  <br/> Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**TargetUserId** <br/> |int  <br/> |Fremd  <br/> |Das Original für Benutzer-URI in der SIP-Anforderung. Weitere Informationen finden Sie in der [Tabelle "Benutzer](users.md) ". <br/> |
|**SessionStartedById** <br/> |int  <br/> |Fremd  <br/> |Die ID des Benutzers, der die Sitzung gestartet hat. Weitere Informationen finden Sie in der [Tabelle "Benutzer](users.md) ". <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Fremd  <br/> |Gibt die ID des Benutzers an, der der Anrufer im Auftrag ist. Weitere Informationen finden Sie in der [Tabelle "Benutzer](users.md) ". <br/> |
|**ReferredById** <br/> |int  <br/> |Fremd  <br/> |Die ID des Benutzers, auf den der Anruf verweist. Weitere Informationen finden Sie in der [Tabelle "Benutzer](users.md) ". <br/> |
|**ServerID** <br/> |int  <br/> |Fremd  <br/> |Die ID des für diese Sitzung verwendeten Front-End-Servers. Weitere Informationen finden Sie in der [Tabelle Server](servers.md) . <br/> |
|**Pool-Nr** <br/> |int  <br/> |Fremd  <br/> |Die ID des Pools, in dem die Sitzung erfasst wurde. Weitere Informationen finden Sie in der [Tabelle Pools](pools.md) . <br/> |
|**ContentTypeID** <br/> |int  <br/> |Fremd  <br/> |Inhaltstyp, der in der Sitzung verwendet wird. Weitere Informationen finden Sie in der Tabelle "ContentTypes" [in Skype for Business Server 2015](contenttypes.md) . <br/> |
|**User1ClientVerId** <br/> |int  <br/> |Fremd  <br/> |Von Benutzer1 verwendete Client Version. Weitere Informationen finden Sie [in der Tabelle ClientVersions in Skype for Business Server 2015](clientversions.md) . <br/> |
|**User2ClientVerId** <br/> |int  <br/> |Fremd  <br/> |Von User2 verwendete Client Version. Weitere Informationen finden Sie [in der Tabelle ClientVersions in Skype for Business Server 2015](clientversions.md) . <br/> |
|**User1EdgeServerid** <br/> |int  <br/> |Fremd  <br/> |Von Benutzer1 verwendeter Edgeserver Weitere Informationen finden Sie [in der Tabelle EdgeServers in Skype for Business Server 2015](edgeservers.md) . <br/> |
|**User2EdgeServerid** <br/> |int  <br/> |Fremd  <br/> |Von User2 verwendeter Edgeserver. Weitere Informationen finden Sie [in der Tabelle EdgeServers in Skype for Business Server 2015](edgeservers.md) . <br/> |
|**IsUser1Internal** <br/> |bit  <br/> ||Gibt an, ob Benutzer1 intern angemeldet ist oder nicht.  <br/> |
|**IsUser2Internal** <br/> |bit  <br/> ||Gibt an, ob User2 intern angemeldet ist oder nicht.  <br/> |
|**Einladen** <br/> |datetime  <br/> ||Der Zeitpunkt der ersten INVITE-Anforderung. Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden. Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info). Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden. Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).  <br/> |
|**Webantworten** <br/> |datetime  <br/> ||Der Zeitpunkt der Antwort auf die erste Einladungsnachricht. Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden. Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).  <br/> |
|**Response Code** <br/> |int  <br/> ||SIP-Antwortcode für die Sitzungseinladung Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden. Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).  <br/> |
|**Diagnose-Nr** <br/> |int  <br/> ||Vom SIP-Header erfasste Diagnose-ID.  <br/> |
|**CallPriority** <br/> |int  <br/> |Fremd  <br/> |Anrufpriorität. Weitere Informationen finden Sie [in der Tabelle CallPriorities in Skype for Business Server 2015](callpriorities.md) . <br/> |
|**User1MessageCount** <br/> |int  <br/> ||Die Anzahl der Nachrichten, die von Benutzer1 während der Sitzung gesendet wurden.  <br/> |
|**User2MessageCount** <br/> |int  <br/> ||Die Anzahl der Nachrichten, die von User2 während der Sitzung gesendet wurden.  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||Uhrzeit am Ende der Sitzung.  <br/> |
|**MediaTypes** <br/> |int  <br/> ||Ein Bit-Satz, der den Medientyp dieser Sitzung angibt. Aufgelistet sind die Definitionen der Typen:  <br/> 1-Chat  <br/> 2 – FILE_TRANSFER  <br/> 4-REMOTE_ASSISTANCE  <br/> 8-APP_SHARING  <br/> 16-Audio  <br/> 32-Video  <br/> 64-APP_INVITE  <br/> |
|**User1Flag** <br/> |smallint  <br/> ||Ein Bit-Satz, der die Benutzer1-Attribute angibt. Die folgenden Attributdefinitionen werden aufgelistet:  <br/> 0x01-integriert mit dem Desktoptelefon  <br/> |
|**User2Flag** <br/> |smallint  <br/> ||Ein Bit-Satz, der die User2-Attribute angibt. Die folgenden Attributdefinitionen werden aufgelistet:  <br/> 0x01-integriert mit dem Desktoptelefon  <br/> |
|**CallFlag** <br/> |smallint  <br/> ||Ein Bit-Satz, der die anrufattribute angibt. Die folgenden Attributdefinitionen werden aufgelistet:  <br/> 0x01-wiederholte Sitzung  <br/> 0x02 – ein Anruf, der von einem Agenten im Auftrag einer Reaktionsgruppe durchgeführt wurde  <br/> |
|**Verarbeitet** <br/> |bit  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype for Business Server 2015 eingeführt.  <br/> |
   
\*Bei den meisten Sitzungen erhält SessionIdSeq den Wert 1. Wenn mehrere Sitzungen genau zur gleichen Zeit beginnen, ist der SessionIdSeq für einen 1, für einen anderen wird 2 usw.
  

