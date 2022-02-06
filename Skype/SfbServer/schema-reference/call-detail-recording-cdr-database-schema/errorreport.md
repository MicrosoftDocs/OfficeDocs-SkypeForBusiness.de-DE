---
title: ErrorReport-Tabelle in Skype for Business Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
description: 'In der ErrorReport-Tabelle werden Informationen zu aufgetretenen Fehlern gespeichert. Jeder Datensatz ist ein Fehler. Die Fehler werden entweder vom KDS-Agent erfasst, der auf dem Front-End-Server ausgeführt wird, oder vom Client gesendet.'
---

# <a name="errorreport-table-in-skype-for-business-server-2015"></a>ErrorReport-Tabelle in Skype for Business Server 2015
 
In der ErrorReport-Tabelle werden Informationen zu aufgetretenen Fehlern gespeichert. Jeder Datensatz ist ein Fehler. Die Fehler werden entweder vom KDS-Agent erfasst, der auf dem Front-End-Server ausgeführt wird, oder vom Client gesendet.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |Datum/Uhrzeit  <br/> |Primary  <br/> |Datum und Uhrzeit des Fehlers.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Primary  <br/> |ID-Nummer zum Identifizieren des Fehlerberichts. Wird in Verbindung mit **ErrorTime** verwendet, um einen Fehlerbericht eindeutig zu identifizieren. <br/> |
|**Errorid** <br/> |int  <br/> |Ausländisch  <br/> |Eindeutige ID des Fehlertyps. Weitere Informationen finden Sie [in der ErrorDef-Tabelle in Skype for Business Server 2015](errordef.md). <br/> |
|**FromUserId** <br/> |int  <br/> |Ausländisch  <br/> |Benutzer, der die Anforderung, die den Fehler verursacht hat, ausgelöst hat. Weitere Informationen finden Sie in der [Tabelle "Benutzer](users.md) ". <br/> |
|**ToUserId** <br/> |int  <br/> |Ausländisch  <br/> |Zielbenutzer für die Anforderung, die den Fehler verursacht hat. Weitere Informationen finden Sie in der [Tabelle "Benutzer](users.md) ". <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Ausländisch  <br/> |Konferenz-URI im Zusammenhang mit dem Fehler. Weitere Informationen finden Sie [in der ConferenceUris-Tabelle in Skype for Business Server 2015](conferenceuris.md). Wenn ConferenceUriId nicht NULL ist, ist FromUserId oder ToUserId normalerweise null. <br/> |
|**SessionIdTime** <br/> |Datum/Uhrzeit  <br/> |Ausländisch  <br/> |Wird zusammen mit **SessionIdSeq** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Dialogs-Tabelle in Skype for Business Server 2015](dialogs.md). <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Ausländisch  <br/> |ID zur Identifikation der Sitzung. Wird zusammen mit **SessionIdTime** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Dialogs-Tabelle in Skype for Business Server 2015](dialogs.md). <br/> |
|**SourceId** <br/> |int  <br/> |Ausländisch  <br/> |Server, der den Fehlerbericht gesendet hat (wenn der Bericht von einer Serverkomponente gesendet wird). Weitere Informationen finden Sie in der [Tabelle "Server](servers.md) ". <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ApplicationId** <br/> |int  <br/> |Ausländisch  <br/> |Server, der den Fehlerbericht gesendet hat (wenn der Bericht von einer Serverkomponente gesendet wird). Weitere Informationen finden Sie [in der Application-Tabelle in Skype for Business Server 2015](application.md). <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**MsDiagHeader** <br/> |Abbildung  <br/> | <br/> |Weitere Informationen zu dem Fehler.  <br/> Diese Daten können mithilfe der folgenden Syntax in das Textformat konvertiert werden:  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |int  <br/> |Ausländisch  <br/> |Die Clientversion des Endpunkts, der den Fehlerbericht sendet. Weitere Informationen finden Sie [in der Tabelle "ClientVersions" in Skype for Business Server 2015](clientversions.md). <br/> |
|**IsCapturedByServer** <br/> |Bit  <br/> ||Ist der Fehlerbericht, der vom KDS-Agent erfasst wird, der auf dem Front-End-Server ausgeführt oder vom Client gesendet wird.  <br/> |
|**Wert** <br/> |Smallint  <br/> ||Reserviert für zukünftige Verwendung.  <br/> |
|**Telemetrie-ID** <br/> |Uniqueidentifier  <br/> ||Eindeutiger Bezeichner, der die Informationen über den Zeitpunkt des Beitritts für verschiedene in einer Konferenz beteiligten Komponenten korreliert.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Für eine bestimmte Komponente erforderliche Zeit (in Millisekunden), um an einer Konferenz teilzunehmen.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ServerId** <br/> |int  <br/> |Ausländisch  <br/> |Stellt den vollqualifizierten Domänennamen des Servers dar, der den Fehlerbericht generiert hat.  <br/> |
|**PoolId** <br/> |int  <br/> |Ausländisch  <br/> |Stellt den vollqualifizierten Domänennamen des Pools dar, in dem der Fehlerbericht generiert wurde.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype for Business Server 2015 eingeführt.  <br/> |
   

