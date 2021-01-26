---
title: Ansicht "ErrorReport"
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
description: In der Ansicht "ErrorReport" werden Informationen zu gemeldeten Fehlern speichert. Jeder Datensatz ist ein Fehlervorkommen. Die Fehler werden entweder vom cdr-Agent erfasst, der auf dem Front-End-Server ausgeführt wird, oder vom Client gesendet. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: e00e2bddaea34be6b09bc211991539ad6123603e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821715"
---
# <a name="errorreport-view"></a>Ansicht "ErrorReport"
 
In der Ansicht "ErrorReport" werden Informationen zu gemeldeten Fehlern speichert. Jeder Datensatz ist ein Fehlervorkommen. Die Fehler werden entweder vom cdr-Agent erfasst, der auf dem Front-End-Server ausgeführt wird, oder vom Client gesendet. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |Datum/Uhrzeit  <br/> |Zeitpunkt des Fehlers. Wird zusammen mit "ErrorReportSeq" verwendet, um einen Fehler eindeutig zu bestimmen.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |ID-Nummer zum Bestimmen des Fehlers. Wird zusammen mit "ErrorTime" verwendet, um einen Fehler eindeutig zu bestimmen.  <br/> |
|**MsDiagId** <br/> |int  <br/> |Diagnose-ID für den Fehlerbericht.  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |URI des Benutzers, der den Fehler verursacht hat.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |Typ des URI des Benutzers, der den Fehler verursacht hat. Weitere Informationen finden Sie in der [Tabelle "UriTypes".](uritypes.md) <br/> |
|**FromTenant** <br/> |nvarchar(256)  <br/> |Mandant des Benutzers, der den Fehler verursacht hat. Weitere Informationen [finden Sie in der Tabelle "Mandanten".](tenants.md) <br/> |
|**ToUri** <br/> |nvarchar(450)  <br/> |URI des Benutzers, der das Ziel des Fehlerberichts war.  <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |Typ des URI des Benutzers, der den Fehlerbericht als Ziel hat. Weitere Informationen finden Sie in der UriTypes Table.  <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |Mandant des Benutzers, der den Fehlerbericht als Ziel hat. Weitere Informationen [finden Sie in der Tabelle "Mandanten".](tenants.md) <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |URI der Konferenz, die das Ziel des Fehlerberichts war.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Der URI-Typ der Konferenz, die das Ziel des Fehlerberichts war. Weitere Informationen finden Sie in der [Tabelle "UriTypes".](uritypes.md) <br/> |
|**SessionIdTime** <br/> |Datum/Uhrzeit  <br/> |Zeitpunkt der Sitzungsanforderung, von der der Fehlerbericht stammt. Wird zusammen mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren.. Weitere Informationen [finden Sie in der Tabelle "Dialogfelder" in Skype for Business Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |ID-Nummer, um die Sitzungsanforderung zu identifizieren, von der der Fehlerbericht stammt. Wird zusammen mit SessionIdTime verwendet, um eine Konferenzinstanz eindeutig zu identifizieren. Weitere Informationen [finden Sie in der Tabelle "Dialogfelder" in Skype for Business Server 2015.](dialogs.md) <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |SIP-Dialog-ID der Sitzung, die den Fehler verursacht hat. Das Format lautet wie folgt:  <br/> dialog;from-tag;to-tag  <br/> Diese Daten können mit der folgenden Syntax in das Textformat konvertiert werden:  <br/> cast(cast(ExternalId as varbinary(max)) as varchar(max))  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |Version des Clients, die vom Benutzer verwendet wird, der den Fehler verursacht hat.  <br/> |
|**ClientType** <br/> |int  <br/> |Client, der vom Benutzer verwendet wird, der den Fehler verursacht hat. Weitere Informationen finden Sie in der Tabelle ["UserAgentDef".](useragentdef.md) <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Name der Kategorie des Clients, der vom Benutzer verwendet wird, der den Fehler verursacht hat.  <br/> |
|**Source** <br/> |nvarchar(256)  <br/> |Name des Servers, von dem der Fehler stammt (wenn der Bericht von einer Serverkomponente gesendet wurde).  <br/> |
|**Anwendung** <br/> |nvarchar(256)  <br/> |Name der Anwendung, von der der Fehler stammt (wenn der Bericht von einer Serverkomponente gesendet wurde).  <br/> |
|**ResponseCode** <br/> |int  <br/> |SIP-Antwortcode für die Sitzung der SIP-Nachricht, die den Fehlerbericht enthält.  <br/> |
|**RequestType** <br/> |varchar(max)  <br/> |Typ der fehlgeschlagenen Anforderung.  <br/> |
|**ContentType** <br/> |varchar(max)  <br/> |Inhaltstyp der fehlgeschlagenen Anforderung.  <br/> |
|**CallType** <br/> |nvarchar(256)  <br/> |Der Sitzungstyp. Weitere Informationen finden Sie in der [Tabelle "CallType" in Skype for Business Server 2015.](calltype.md) <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |Eindeutiger Bezeichner, der die Informationen über den Zeitpunkt des Beitritts für verschiedene in einer Konferenz beteiligten Komponenten korreliert.  <br/> |
|**SetupTime** <br/> |int  <br/> |Für eine bestimmte Komponente erforderliche Zeit (in Millisekunden), um an einer Konferenz teilzunehmen.  <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> |Gibt an, ob der Fehlerbericht vom auf dem Front-End-Server ausgeführten oder vom Client gesendeten CDR-Agent erfasst wurde.  <br/> |
|**Wert** <br/> |smallint  <br/> |Reserviert für zukünftige Verwendung.  <br/> |
|**MsDiagHeader** <br/> |varchar(max)  <br/> |Zusätzliche Informationen zu dem Fehler.  <br/> |
|**FrontEnd** <br/> |nvarchar  <br/> |Vollqualifizierter Domänenname des Front-End-Servers, der den Bericht übermittelt hat.  <br/> |
|**Pool** <br/> |nvarchar  <br/> |Vollqualifizierter Domänenname des Pools, der den Front-End-Server enthält, der den Bericht übermittelt hat.  <br/> |
   

