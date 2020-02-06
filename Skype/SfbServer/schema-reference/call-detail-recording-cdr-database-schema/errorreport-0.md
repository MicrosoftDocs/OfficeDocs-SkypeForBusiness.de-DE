---
title: ErrorReport-Ansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
description: In der errorreport-Ansicht werden Informationen zu den gemeldeten Fehlern gespeichert. Bei jedem Datensatz handelt es sich um ein Fehlerereignis. Die Fehler werden entweder vom CDR-Agent, der auf dem Front-End-Server ausgeführt wird, erfasst oder vom Client gesendet. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: d51b085d5dabb8a6ae0dc367b23dd23a1702174e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815243"
---
# <a name="errorreport-view"></a>ErrorReport-Ansicht
 
In der errorreport-Ansicht werden Informationen zu den gemeldeten Fehlern gespeichert. Bei jedem Datensatz handelt es sich um ein Fehlerereignis. Die Fehler werden entweder vom CDR-Agent, der auf dem Front-End-Server ausgeführt wird, erfasst oder vom Client gesendet. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**Fehlerzeit** <br/> |datetime  <br/> |Zeitpunkt des Fehlers. Wird in Verbindung mit ErrorReportSeq verwendet, um einen Fehler eindeutig zu identifizieren.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Die ID-Nummer, um den Fehler zu identifizieren. Wird in Verbindung mit Fehlerzeit verwendet, um einen Fehler eindeutig zu identifizieren.  <br/> |
|**MsDiagId** <br/> |int  <br/> |Diagnose-ID für den Fehlerbericht.  <br/> |
|**FromUri** <br/> |nvarchar (450)  <br/> |Der URI des Benutzers, der den Fehler ausgelöst hat.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |Der Typ des URIs des Benutzers, der den Fehler ausgelöst hat. Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**FromTenant** <br/> |nvarchar(256)  <br/> |Der Mandant des Benutzers, der den Fehler ausgelöst hat. Weitere Informationen finden Sie in der [Tabelle Mandanten](tenants.md) . <br/> |
|**Touri** <br/> |nvarchar (450)  <br/> |Der URI des Benutzers, der das Ziel des Fehlerberichts war.  <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |Der Typ des URIs des Benutzers, der auf den Fehlerbericht ausgerichtet ist. Weitere Informationen finden Sie in der UriTypes-Tabelle.  <br/> |
|**Totenant** <br/> |nvarchar(256)  <br/> |Der Mandant des Benutzers, der auf den Fehlerbericht abzielt. Weitere Informationen finden Sie in der [Tabelle Mandanten](tenants.md) . <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> |Der URI der Konferenz, die das Ziel des Fehlerberichts war.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Der URI-Typ der Konferenz, die das Ziel des Fehlerberichts war. Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**SessionID** <br/> |datetime  <br/> |Die Uhrzeit der Sitzungsanforderung, von der der Fehlerbericht stammt. Wird in Verbindung mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Die ID-Nummer, mit der die Sitzungsanforderung identifiziert wird, von der der Fehlerbericht stammt. Wird in Verbindung mit SessionID-Mal verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**Dialogfeld-Nr** <br/> |varstring (775)  <br/> |SIP-Dialogfeld-ID der Sitzung, die den Fehler ausgelöst hat. Das Format lautet:  <br/> Dialogfeld; from-Tag; to-Tag  <br/> Diese Daten können mithilfe der folgenden Syntax in das Text Format konvertiert werden:  <br/> Umwandlung (Umwandlung (extern-als varbinary (max)) als varchar (max))  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |Die Version des Clients, die von dem Benutzer verwendet wird, der den Fehler verursacht hat.  <br/> |
|**Clienttyp** <br/> |int  <br/> |Der Client, der vom Benutzer verwendet wird, der den Fehler ausgelöst hat. Weitere Informationen finden Sie in der [UserAgentDef-Tabelle](useragentdef.md) . <br/> |
|**ClientCategory** <br/> |nvarchar (64)  <br/> |Der Name der Kategorie des Clients, der vom Benutzer verwendet wird, der den Fehler ausgelöst hat.  <br/> |
|**Quelle** <br/> |nvarchar(256)  <br/> |Name des Servers, der den Fehler verursacht hat (wenn der Bericht von einer Serverkomponente gesendet wurde).  <br/> |
|**Anwendung** <br/> |nvarchar(256)  <br/> |Der Name der Anwendung, die den Fehler verursacht hat (wenn der Bericht von einer Serverkomponente gesendet wurde).  <br/> |
|**Response Code** <br/> |int  <br/> |SIP-Antwortcode für die Sitzung der SIP-Nachricht, die den Fehlerbericht enthält.  <br/> |
|**RequestType** <br/> |varchar (max)  <br/> |Der Typ der fehlgeschlagenen Anforderung.  <br/> |
|**ContentType** <br/> |varchar (max)  <br/> |Inhaltstyp der fehlgeschlagenen Anforderung.  <br/> |
|**CallType** <br/> |nvarchar(256)  <br/> |Der Sitzungstyp. Weitere Informationen finden Sie [in der Tabelle "CallType" in Skype for Business Server 2015](calltype.md) . <br/> |
|**Telemetrie** <br/> |uniqueidentifier  <br/> |Eindeutiger Bezeichner, in dem die Verknüpfungszeit Informationen für die verschiedenen an einer Konferenz beteiligten Komponenten korreliert werden.  <br/> |
|**Rüstzeit** <br/> |int  <br/> |Zeit (in Millisekunden), die für eine bestimmte Komponente erforderlich ist, um an einer Konferenz teilzunehmen.  <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> |Gibt an, ob der Fehlerbericht vom auf dem Front-End-Server ausgeführten CDR-Agent erfasst oder vom Client gesendet wurde.  <br/> |
|**Kennzeichnen** <br/> |smallint  <br/> |Für die spätere Verwendung reserviert.  <br/> |
|**MsDiagHeader** <br/> |varchar (max)  <br/> |Weitere Informationen zum Fehler.  <br/> |
|**FrontEnd** <br/> |nvarchar  <br/> |Vollständig qualifizierter Domänenname des Front-End-Servers, der den Bericht übermittelt hat.  <br/> |
|**Pool** <br/> |nvarchar  <br/> |Vollständig qualifizierter Domänenname des Pools, der den Front-End-Server enthält, der den Bericht übermittelt hat.  <br/> |
   

