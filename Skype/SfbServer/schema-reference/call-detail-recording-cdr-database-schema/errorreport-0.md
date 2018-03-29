---
title: ErrorReport-Ansicht
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
description: ErrorReport-Ansicht speichert Informationen über Fehler gemeldet. Jeder Datensatz ist ein Fehler auftreten. Die Fehler werden erfasst entweder von der CDR-Agent auf dem Front-End-Server oder vom Client gesendet. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: b1815d4420b5768b065a5695ea09174ecff91912
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="errorreport-view"></a>ErrorReport-Ansicht
 
ErrorReport-Ansicht speichert Informationen über Fehler gemeldet. Jeder Datensatz ist ein Fehler auftreten. Die Fehler werden erfasst entweder von der CDR-Agent auf dem Front-End-Server oder vom Client gesendet. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**"ErrorTime"** <br/> |datetime  <br/> |Zeitpunkt der Fehler aufgetreten ist. In Verbindung mit "errorreportseq" verwendet, um einen Fehler eindeutig zu identifizieren.  <br/> |
|**"Errorreportseq"** <br/> |int  <br/> |ID-Nummer zur Identifikation des Fehlers. In Verbindung mit ErrorTime verwendet, um einen Fehler eindeutig zu identifizieren.  <br/> |
|**MsDiagId** <br/> |int  <br/> |Diagnose-ID für den Fehlerbericht.  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |Der URI des Benutzers, der den Fehler ausgelöst hat.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |Typ der URI des Benutzers, der den Fehler ausgelöst hat. Finden Sie weitere Informationen der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**FromTenant** <br/> |nvarchar(256)  <br/> |Mandant des Benutzers, der den Fehler ausgelöst hat. Finden Sie weitere Informationen der [Tenants-Tabelle](tenants.md) . <br/> |
|**ToUri** <br/> |nvarchar(450)  <br/> |Der URI des Benutzers, der das Ziel des Fehlerberichts war.  <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |Typ der URI des Benutzers, der als Ziel des Fehlerberichts. Finden Sie weitere Informationen der UriTypes-Tabelle.  <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |Mandant des Benutzers, der als Ziel des Fehlerberichts. Finden Sie weitere Informationen der [Tenants-Tabelle](tenants.md) . <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |Der URI der Konferenz, die das Ziel des Fehlerberichts war.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |URI-Typ der Konferenz, die das Ziel des Fehlerberichts war. Finden Sie weitere Informationen der [UriTypes-Tabelle](uritypes.md) . <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |Zeitpunkt der sitzungsanforderung, die den Fehlerbericht ausgelöst hat. Zusammen mit SessionIdSeq verwendet zur eindeutigen Identifizierung eine Sitzung. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |ID-Nummer die sitzungsanforderung eindeutig identifiziert, die den Fehlerbericht ausgelöst hat. In Verbindung mit SessionIdTime verwendet, um eine Sitzung eindeutig zu identifizieren. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**Dialog-ID** <br/> |varstring(775)  <br/> |SIP-Dialog-ID der Sitzung, die den Fehler ausgelöst hat. Das Format lautet:  <br/> Dialogfeld; aus Tag; -tag  <br/> Diese Daten können mithilfe der folgenden Syntax in das Textformat konvertiert werden:  <br/> CAST (Cast (ExternalId as varbinary(max)) as varchar(max))  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |Version des Client des Benutzers, der den Fehler ausgelöst hat.  <br/> |
|**Clienttyp** <br/> |int  <br/> |Client des Benutzers, der den Fehler ausgelöst hat. Finden Sie weitere Details der [UserAgentDef-Tabelle](useragentdef.md) . <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Name der Kategorie des Clients des Benutzers, der den Fehler ausgelöst hat.  <br/> |
|**Quelle** <br/> |nvarchar(256)  <br/> |Name des Servers, der den Fehler ausgelöst hat (falls der Bericht von einer Serverkomponente gesendet wurde).  <br/> |
|**Anwendung** <br/> |nvarchar(256)  <br/> |Name der Anwendung, die den Fehler ausgelöst hat (falls der Bericht von einer Serverkomponente gesendet wurde).  <br/> |
|**ResponseCode** <br/> |int  <br/> |SIP-Antwortcode für die Sitzung der SIP-Nachricht, die den Fehlerbericht enthält.  <br/> |
|**RequestType** <br/> |varchar(max)  <br/> |Typ der erfolgreichen Anforderung.  <br/> |
|**ContentType** <br/> |varchar(max)  <br/> |Inhaltstyp der erfolgreichen Anforderung.  <br/> |
|**CallType** <br/> |nvarchar(256)  <br/> |Der Sitzungstyp. [CallType-Tabelle in Skype für Business Server 2015](calltype.md) Weitere Informationen finden Sie. <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |Eindeutige ID zum korelieren für die verschiedenen Komponenten in einer Konferenz Beteiligten.  <br/> |
|**SetupTime** <br/> |int  <br/> |Zeit (in Millisekunden) für eine bestimmte Komponente zu einer Konferenz erforderlich.  <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> |Gibt an, ob der Fehlerbericht vom KDS-Agent auf dem Front-End-Server ausgeführt erfasst wurde, oder vom Client gesendet wurde.  <br/> |
|**Kennzeichnung** <br/> |smallint  <br/> |Für künftige Zwecke vorbehalten.  <br/> |
|**MsDiagHeader** <br/> |varchar(max)  <br/> |Weitere Informationen zu dem Fehler.  <br/> |
|**Front-End** <br/> |nvarchar  <br/> |Vollqualifizierter Domänenname des Front-End-Servers, die den Bericht gesendet.  <br/> |
|**Pool** <br/> |nvarchar  <br/> |Vollständig qualifizierte Domänenname des Pools mit dem Front-End-Server, der den Bericht gesendet.  <br/> |
   

