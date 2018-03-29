---
title: ErrorReport-Tabelle in Skype für Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
description: ErrorReport-Tabelle speichert Informationen zu aufgetretenen Fehlern. Jeder Datensatz ist ein Fehler auftreten. Die Fehler werden erfasst entweder von der CDR-Agent auf dem Front-End-Server oder vom Client gesendet.
ms.openlocfilehash: 80ae8cb9fb4bea586ac31456fc396856e5263a34
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="errorreport-table-in-skype-for-business-server-2015"></a>ErrorReport-Tabelle in Skype für Business Server 2015
 
ErrorReport-Tabelle speichert Informationen zu aufgetretenen Fehlern. Jeder Datensatz ist ein Fehler auftreten. Die Fehler werden erfasst entweder von der CDR-Agent auf dem Front-End-Server oder vom Client gesendet.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**"ErrorTime"** <br/> |datetime  <br/> |Primary  <br/> |Datum und Uhrzeit des Auftretens des Fehlers.  <br/> |
|**"Errorreportseq"** <br/> |int  <br/> |Primary  <br/> |ID-Nummer zum Identifizieren des Fehlerberichts. In Verbindung mit **ErrorTime** verwendet, um einen Fehlerbericht eindeutig zu identifizieren. <br/> |
|**Fehler-ID** <br/> |int  <br/> |Fremdschlüssel  <br/> |Eindeutige ID des Fehlertyps. [ErrorDef-Tabelle in Skype für Business Server 2015](errordef.md) Weitere Informationen finden Sie. <br/> |
|**FromUserId** <br/> |int  <br/> |Fremdschlüssel  <br/> |Benutzer, der die Anforderung stammt, die den Fehler verursacht hat. Finden Sie in der [Tabelle Benutzer](users.md) Weitere Informationen. <br/> |
|**ToUserId** <br/> |int  <br/> |Fremdschlüssel  <br/> |Zielbenutzer für die Anforderung, die den Fehler verursacht hat. Finden Sie in der [Tabelle Benutzer](users.md) Weitere Informationen. <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Fremdschlüssel  <br/> |Konferenz-URI im Zusammenhang mit dem Fehler. [ConferenceUris-Tabelle in Skype für Business Server 2015](conferenceuris.md) Weitere Informationen finden Sie. In der Regel, wenn ConferenceUriId ungleich null ist, wird dann FromUserId oder ToUserId null sein. <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |Fremdschlüssel  <br/> |Zusammen mit **SessionIdSeq** verwendet zur eindeutigen Identifizierung eine Sitzung. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Fremdschlüssel  <br/> |ID-Nummer, um die Sitzung zu identifizieren. In Verbindung mit **SessionIdTime** verwendet, um eine Sitzung eindeutig zu identifizieren. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**SourceId** <br/> |int  <br/> |Fremdschlüssel  <br/> |Server, die den Fehlerbericht gesendet (wenn der Bericht von einer Serverkomponente gesendet wird). Finden Sie weitere Informationen der [Server-Tabelle](servers.md) . <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ApplicationId** <br/> |int  <br/> |Fremdschlüssel  <br/> |Server, die den Fehlerbericht gesendet (wenn der Bericht von einer Serverkomponente gesendet wird). Siehe die [Application-Tabelle in Skype für Business Server 2015](application.md) Weitere Informationen. <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**MsDiagHeader** <br/> |Bild  <br/> | <br/> |Weitere Informationen zu dem Fehler.  <br/> Diese Daten können mithilfe der folgenden Syntax in das Textformat konvertiert werden:  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |int  <br/> |Fremdschlüssel  <br/> |Client-Version des Endpunkt, der den Fehlerbericht sendet. [ClientVersions-Tabelle in Skype für Business Server 2015](clientversions.md) Weitere Informationen finden Sie. <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> ||Der Fehlerbericht ist vom KDS-Agent auf dem Front-End-Server ausgeführt erfasst oder vom Client gesendet wurde.  <br/> |
|**Kennzeichnung** <br/> |smallint  <br/> ||Für künftige Zwecke vorbehalten.  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||Eindeutige ID zum korelieren für die verschiedenen Komponenten in einer Konferenz Beteiligten.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Zeit (in Millisekunden) für eine bestimmte Komponente zu einer Konferenz erforderlich.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ServerId** <br/> |int  <br/> |Fremdschlüssel  <br/> |Stellt den vollqualifizierten Domänennamen des Servers, der den Fehlerbericht generiert hat.  <br/> |
|**PoolId** <br/> |int  <br/> |Fremdschlüssel  <br/> |Stellt den vollqualifizierten Domänennamen des Pools, in dem der Fehlerbericht generiert wurde.  <br/> |
|**ZuletztGeändertUm** <br/> |DateTime  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype für Business Server 2015 eingeführt.  <br/> |
   

