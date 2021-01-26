---
title: Tabelle "ErrorReport" in Skype for Business Server 2015
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
localization_priority: Normal
ms.assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
description: In der Tabelle "ErrorReport" werden Informationen zu aufgetretenen Fehlern speichert. Jeder Datensatz ist ein Fehlervorkommen. Die Fehler werden entweder vom cdr-Agent erfasst, der auf dem Front-End-Server ausgeführt wird, oder vom Client gesendet.
ms.openlocfilehash: b2f81df1134294185124d78b90c2e4f639575ded
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821675"
---
# <a name="errorreport-table-in-skype-for-business-server-2015"></a>Tabelle "ErrorReport" in Skype for Business Server 2015
 
In der Tabelle "ErrorReport" werden Informationen zu aufgetretenen Fehlern speichert. Jeder Datensatz ist ein Fehlervorkommen. Die Fehler werden entweder vom cdr-Agent erfasst, der auf dem Front-End-Server ausgeführt wird, oder vom Client gesendet.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |Datum/Uhrzeit  <br/> |Primary  <br/> |Datum und Uhrzeit des Fehlers.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Primary  <br/> |ID zum Identifizieren des Fehlerberichts. Wird in Verbindung mit **ErrorTime verwendet,** um einen Fehlerbericht eindeutig zu identifizieren. <br/> |
|**ErrorId** <br/> |int  <br/> |Fremd  <br/> |Eindeutige ID des Fehlertyps. Weitere Informationen finden Sie in der [Tabelle "ErrorDef" in Skype for Business Server 2015.](errordef.md) <br/> |
|**FromUserId** <br/> |int  <br/> |Fremd  <br/> |Der Benutzer, der die Anforderung stammt, die den Fehler verursacht hat. Weitere Informationen [finden Sie in der Tabelle](users.md) "Benutzer". <br/> |
|**ToUserId** <br/> |int  <br/> |Fremd  <br/> |Zielbenutzer für die Anforderung, die den Fehler verursacht hat. Weitere Informationen [finden Sie in der Tabelle](users.md) "Benutzer". <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Fremd  <br/> |Konferenz-URI im Zusammenhang mit dem Fehler. Weitere Informationen finden Sie in der [Tabelle "ConferenceUris" in Skype for Business Server 2015.](conferenceuris.md) Wenn "ConferenceUriId" nicht null ist, ist "FromUserId" oder "ToUserId" in der Regel null. <br/> |
|**SessionIdTime** <br/> |Datum/Uhrzeit  <br/> |Fremd  <br/> |Wird zusammen mit **SessionIdSeq** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen [finden Sie in der Tabelle "Dialogfelder" in Skype for Business Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Fremd  <br/> |ID zur Identifikation der Sitzung. Wird zusammen mit **SessionIdTime** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen [finden Sie in der Tabelle "Dialogfelder" in Skype for Business Server 2015.](dialogs.md) <br/> |
|**SourceId** <br/> |int  <br/> |Fremd  <br/> |Server, der den Fehlerbericht gesendet hat (wenn der Bericht von einer Serverkomponente gesendet wird). Weitere Informationen [finden Sie in der Tabelle "Server".](servers.md) <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ApplicationId** <br/> |int  <br/> |Fremd  <br/> |Server, der den Fehlerbericht gesendet hat (wenn der Bericht von einer Serverkomponente gesendet wird). Weitere Informationen [finden Sie in der Anwendungstabelle in Skype for Business Server 2015.](application.md) <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**MsDiagHeader** <br/> |Abbildung  <br/> | <br/> |Weitere Informationen zu dem Fehler.  <br/> Diese Daten können mit der folgenden Syntax in das Textformat konvertiert werden:  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |int  <br/> |Fremd  <br/> |Die Clientversion des Endpunkts, der den Fehlerbericht sendet. Weitere Informationen finden Sie in der [Tabelle "ClientVersions" in Skype for Business Server 2015.](clientversions.md) <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> ||Ist der Fehlerbericht, der vom auf dem Front-End-Server ausgeführten oder vom Client gesendeten CDR-Agent erfasst wurde.  <br/> |
|**Wert** <br/> |smallint  <br/> ||Reserviert für zukünftige Verwendung.  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||Eindeutiger Bezeichner, der die Informationen über den Zeitpunkt des Beitritts für verschiedene in einer Konferenz beteiligten Komponenten korreliert.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Für eine bestimmte Komponente erforderliche Zeit (in Millisekunden), um an einer Konferenz teilzunehmen.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ServerId** <br/> |int  <br/> |Fremd  <br/> |Stellt den vollqualifizierten Domänennamen des Servers dar, der den Fehlerbericht generiert hat.  <br/> |
|**PoolId** <br/> |int  <br/> |Fremd  <br/> |Stellt den vollqualifizierten Domänennamen des Pools dar, in dem der Fehlerbericht generiert wurde.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype for Business Server 2015 eingeführt.  <br/> |
   

