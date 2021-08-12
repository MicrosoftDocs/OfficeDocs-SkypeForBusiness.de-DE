---
title: ErrorReport-Ansicht
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
description: In der ErrorReport-Ansicht werden Informationen zu gemeldeten Fehlern gespeichert. Jeder Datensatz ist ein Fehler. Die Fehler werden entweder vom KDS-Agent erfasst, der auf dem Front-End-Server ausgeführt wird, oder vom Client gesendet. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 324c22f58883207d49c0224043b8672560f1cf6e64551ca93b9ac43540d46ceb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295382"
---
# <a name="errorreport-view"></a>ErrorReport-Ansicht
 
In der ErrorReport-Ansicht werden Informationen zu gemeldeten Fehlern gespeichert. Jeder Datensatz ist ein Fehler. Die Fehler werden entweder vom KDS-Agent erfasst, der auf dem Front-End-Server ausgeführt wird, oder vom Client gesendet. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |Datum/Uhrzeit  <br/> |Zeitpunkt des Fehlers. Wird zusammen mit "ErrorReportSeq" verwendet, um einen Fehler eindeutig zu bestimmen.  <br/> |
|**ErrorReportSeq** <br/> |Ganzzahl  <br/> |ID-Nummer zum Bestimmen des Fehlers. Wird zusammen mit "ErrorTime" verwendet, um einen Fehler eindeutig zu bestimmen.  <br/> |
|**MsDiagId** <br/> |Ganzzahl  <br/> |Diagnose-ID für den Fehlerbericht.  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |URI des Benutzers, der den Fehler verursacht hat.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |URI-Typ des Benutzers, der den Fehler verursacht hat. Weitere Informationen finden Sie in der [UriTypes-Tabelle.](uritypes.md) <br/> |
|**FromTenant** <br/> |nvarchar(256)  <br/> |Mandant des Benutzers, der den Fehler verursacht hat. Weitere Informationen finden Sie in der [Tabelle "Mandanten".](tenants.md) <br/> |
|**Touri** <br/> |nvarchar(450)  <br/> |URI des Benutzers, der das Ziel des Fehlerberichts war.  <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |URI-Typ des Benutzers, der auf den Fehlerbericht ausgerichtet ist. Weitere Informationen finden Sie in der UriTypes Table.  <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |Mandant des Benutzers, der auf den Fehlerbericht ausgerichtet ist. Weitere Informationen finden Sie in der [Tabelle "Mandanten".](tenants.md) <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |URI der Konferenz, die das Ziel des Fehlerberichts war.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |URI-Typ der Konferenz, die das Ziel des Fehlerberichts war. Weitere Informationen finden Sie in der [UriTypes-Tabelle.](uritypes.md) <br/> |
|**SessionIdTime** <br/> |Datum/Uhrzeit  <br/> |Zeitpunkt der Sitzungsanforderung, die den Fehlerbericht ausgelöst hat. Wird zusammen mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren.. Weitere Informationen finden Sie in der [Dialogs-Tabelle in Skype for Business Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |Ganzzahl  <br/> |ID-Nummer zum Identifizieren der Sitzungsanforderung, die den Fehlerbericht ausgelöst hat. Wird zusammen mit SessionIdTime verwendet, um eine Konferenzinstanz eindeutig zu identifizieren. Weitere Informationen finden Sie in der [Dialogs-Tabelle in Skype for Business Server 2015.](dialogs.md) <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |SIP-Dialog-ID der Sitzung, die den Fehler verursacht hat. Das Format lautet wie folgt:  <br/> dialog;from-tag;to-tag  <br/> Diese Daten können mithilfe der folgenden Syntax in das Textformat konvertiert werden:  <br/> cast(cast(ExternalId as varbinary(max)) as varchar(max))  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |Version des Clients, die vom Benutzer verwendet wird, der den Fehler verursacht hat.  <br/> |
|**ClientType** <br/> |Ganzzahl  <br/> |Client, der vom Benutzer verwendet wird, der den Fehler verursacht hat. Weitere Informationen finden Sie in der [UserAgentDef-Tabelle.](useragentdef.md) <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Name der Kategorie des Clients, der vom Benutzer verwendet wird, der den Fehler verursacht hat.  <br/> |
|**Source** <br/> |nvarchar(256)  <br/> |Name des Servers, von dem der Fehler stammt (wenn der Bericht von einer Serverkomponente gesendet wurde).  <br/> |
|**Anwendung** <br/> |nvarchar(256)  <br/> |Name der Anwendung, von der der Fehler stammt (wenn der Bericht von einer Serverkomponente gesendet wurde).  <br/> |
|**ResponseCode** <br/> |Ganzzahl  <br/> |SIP-Antwortcode für die Sitzung der SIP-Nachricht, die den Fehlerbericht enthält.  <br/> |
|**RequestType** <br/> |varchar(max)  <br/> |Typ der fehlgeschlagenen Anforderung.  <br/> |
|**ContentType** <br/> |varchar(max)  <br/> |Inhaltstyp der fehlgeschlagenen Anforderung.  <br/> |
|**CallType** <br/> |nvarchar(256)  <br/> |Der Sitzungstyp. Weitere Informationen finden Sie in der [CallType-Tabelle in Skype for Business Server 2015.](calltype.md) <br/> |
|**Telemetrie-ID** <br/> |Uniqueidentifier  <br/> |Eindeutiger Bezeichner, der die Informationen über den Zeitpunkt des Beitritts für verschiedene in einer Konferenz beteiligten Komponenten korreliert.  <br/> |
|**SetupTime** <br/> |Ganzzahl  <br/> |Für eine bestimmte Komponente erforderliche Zeit (in Millisekunden), um an einer Konferenz teilzunehmen.  <br/> |
|**IsCapturedByServer** <br/> |Bit  <br/> |Gibt an, ob der Fehlerbericht vom KDS-Agent auf dem Front-End-Server erfasst oder vom Client gesendet wurde.  <br/> |
|**Wert** <br/> |Smallint  <br/> |Reserviert für zukünftige Verwendung.  <br/> |
|**MsDiagHeader** <br/> |varchar(max)  <br/> |Zusätzliche Informationen zu dem Fehler.  <br/> |
|**FrontEnd** <br/> |Nvarchar  <br/> |Vollqualifizierte Domänenname des Front-End-Servers, der den Bericht übermittelt hat.  <br/> |
|**Pool** <br/> |Nvarchar  <br/> |Vollqualifizierte Domänenname des Pools, der den Front-End-Server enthält, der den Bericht übermittelt hat.  <br/> |
   

