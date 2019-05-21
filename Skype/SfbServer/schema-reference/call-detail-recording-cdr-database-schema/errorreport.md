---
title: ErrorReport-Tabelle in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
description: In der errorreport-Tabelle werden Informationen zu Fehlern gespeichert, die aufgetreten sind. Bei jedem Datensatz handelt es sich um ein Fehlerereignis. Die Fehler werden entweder vom CDR-Agent, der auf dem Front-End-Server ausgeführt wird, erfasst oder vom Client gesendet.
ms.openlocfilehash: 80a6106bd7c6b87a7519bca6ce5cc72f45147ad6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296266"
---
# <a name="errorreport-table-in-skype-for-business-server-2015"></a>ErrorReport-Tabelle in Skype for Business Server 2015
 
In der errorreport-Tabelle werden Informationen zu Fehlern gespeichert, die aufgetreten sind. Bei jedem Datensatz handelt es sich um ein Fehlerereignis. Die Fehler werden entweder vom CDR-Agent, der auf dem Front-End-Server ausgeführt wird, erfasst oder vom Client gesendet.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Fehlerzeit** <br/> |datetime  <br/> |Primary  <br/> |Das Datum und die Uhrzeit, zu der der Fehler aufgetreten ist.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Primary  <br/> |Die ID-Nummer, um den Fehlerbericht zu identifizieren. Wird in Verbindung mit **Fehler** Zeit verwendet, um einen Fehlerbericht eindeutig zu identifizieren. <br/> |
|**ErrorID** <br/> |int  <br/> |Fremd  <br/> |Eindeutige ID des Fehlertyps. Weitere Informationen finden Sie [in der Tabelle ErrorDef in Skype for Business Server 2015](errordef.md) . <br/> |
|**FromUserId** <br/> |int  <br/> |Fremd  <br/> |Der Benutzer, der die Anforderung initiiert hat, die den Fehler verursacht hat. Weitere Informationen finden Sie in der [Tabelle "Benutzer](users.md) ". <br/> |
|**Touser-Nr** <br/> |int  <br/> |Fremd  <br/> |Der Zielbenutzer für die Anforderung, die den Fehler verursacht hat. Weitere Informationen finden Sie in der [Tabelle "Benutzer](users.md) ". <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Fremd  <br/> |Konferenz-URI im Zusammenhang mit dem Fehler. Weitere Informationen finden Sie [in der Tabelle ConferenceUris in Skype for Business Server 2015](conferenceuris.md) . Wenn ConferenceUriId nicht NULL ist, ist in der Regel entweder FromUserId oder touser-Wert NULL. <br/> |
|**SessionID** <br/> |datetime  <br/> |Fremd  <br/> |Wird in Verbindung mit **SessionIdSeq** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Fremd  <br/> |Die ID-Nummer, um die Sitzung zu identifizieren. Wird in Verbindung mit **SessionID** -Mal verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**SourceID** <br/> |int  <br/> |Fremd  <br/> |Der Server, der den Fehlerbericht gesendet hat (wenn der Bericht von einer Serverkomponente gesendet wird). Weitere Informationen finden Sie in der [Tabelle Server](servers.md) . <br/> Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**ApplicationId** <br/> |int  <br/> |Fremd  <br/> |Der Server, der den Fehlerbericht gesendet hat (wenn der Bericht von einer Serverkomponente gesendet wird). Weitere Informationen finden Sie [in der Anwendungstabelle in Skype for Business Server 2015](application.md) . <br/> Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**MsDiagHeader** <br/> |Bild  <br/> | <br/> |Weitere Informationen zum Fehler.  <br/> Diese Daten können mithilfe der folgenden Syntax in das Text Format konvertiert werden:  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |int  <br/> |Fremd  <br/> |Die Client Version des Endpunkts, der den Fehlerbericht sendet. Weitere Informationen finden Sie [in der Tabelle ClientVersions in Skype for Business Server 2015](clientversions.md) . <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> ||Der Fehlerbericht, der vom auf dem Front-End-Server ausgeführten CDR-Agent erfasst oder vom Client gesendet wird.  <br/> |
|**Kennzeichnen** <br/> |smallint  <br/> ||Für die spätere Verwendung reserviert.  <br/> |
|**Telemetrie** <br/> |uniqueIdentifier  <br/> ||Eindeutiger Bezeichner, in dem die Verknüpfungszeit Informationen für die verschiedenen an einer Konferenz beteiligten Komponenten korreliert werden.  <br/> Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Zeit (in Millisekunden), die für eine bestimmte Komponente erforderlich ist, um an einer Konferenz teilzunehmen.  <br/> Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**ServerID** <br/> |int  <br/> |Fremd  <br/> |Stellt den vollqualifizierten Domänennamen des Servers dar, der den Fehlerbericht generiert hat.  <br/> |
|**Pool-Nr** <br/> |int  <br/> |Fremd  <br/> |Stellt den vollqualifizierten Domänennamen des Pools dar, in dem der Fehlerbericht generiert wurde.  <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype for Business Server 2015 eingeführt.  <br/> |
   

