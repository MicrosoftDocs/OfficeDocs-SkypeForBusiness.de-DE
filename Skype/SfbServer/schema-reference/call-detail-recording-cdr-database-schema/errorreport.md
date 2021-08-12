---
title: ErrorReport-Tabelle in Skype for Business Server 2015
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
description: In der ErrorReport-Tabelle werden Informationen zu aufgetretenen Fehlern gespeichert. Jeder Datensatz ist ein Fehler. Die Fehler werden entweder vom KDS-Agent erfasst, der auf dem Front-End-Server ausgeführt wird, oder vom Client gesendet.
ms.openlocfilehash: 1cac143f50e361598c7985aa585485bd73c9aa79d3b47bd21fb0b70e75b9377e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303678"
---
# <a name="errorreport-table-in-skype-for-business-server-2015"></a>ErrorReport-Tabelle in Skype for Business Server 2015
 
In der ErrorReport-Tabelle werden Informationen zu aufgetretenen Fehlern gespeichert. Jeder Datensatz ist ein Fehler. Die Fehler werden entweder vom KDS-Agent erfasst, der auf dem Front-End-Server ausgeführt wird, oder vom Client gesendet.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |Datum/Uhrzeit  <br/> |Primary  <br/> |Datum und Uhrzeit des Fehlers.  <br/> |
|**ErrorReportSeq** <br/> |Ganzzahl  <br/> |Primary  <br/> |ID-Nummer zum Identifizieren des Fehlerberichts. Wird in Verbindung mit **ErrorTime** verwendet, um einen Fehlerbericht eindeutig zu identifizieren. <br/> |
|**Errorid** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |Eindeutige ID des Fehlertyps. Weitere Informationen finden Sie in der [ErrorDef-Tabelle in Skype for Business Server 2015.](errordef.md) <br/> |
|**FromUserId** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |Benutzer, der die Anforderung, die den Fehler verursacht hat, ausgelöst hat. Weitere Informationen finden Sie in der [Tabelle "Benutzer".](users.md) <br/> |
|**ToUserId** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |Zielbenutzer für die Anforderung, die den Fehler verursacht hat. Weitere Informationen finden Sie in der [Tabelle "Benutzer".](users.md) <br/> |
|**ConferenceUriId** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |Konferenz-URI im Zusammenhang mit dem Fehler. Weitere Informationen finden Sie in der [ConferenceUris-Tabelle in Skype for Business Server 2015.](conferenceuris.md) Wenn ConferenceUriId nicht NULL ist, ist FromUserId oder ToUserId normalerweise null. <br/> |
|**SessionIdTime** <br/> |Datum/Uhrzeit  <br/> |Ausländisch  <br/> |Wird zusammen mit **SessionIdSeq** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie in der [Dialogs-Tabelle in Skype for Business Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |ID zur Identifikation der Sitzung. Wird zusammen mit **SessionIdTime** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie in der [Dialogs-Tabelle in Skype for Business Server 2015.](dialogs.md) <br/> |
|**SourceId** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |Server, der den Fehlerbericht gesendet hat (wenn der Bericht von einer Serverkomponente gesendet wird). Weitere Informationen finden Sie in der [Tabelle "Server".](servers.md) <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**Applicationid** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |Server, der den Fehlerbericht gesendet hat (wenn der Bericht von einer Serverkomponente gesendet wird). Weitere Informationen finden Sie in der [Application-Tabelle in Skype for Business Server 2015.](application.md) <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**MsDiagHeader** <br/> |Abbildung  <br/> | <br/> |Weitere Informationen zu dem Fehler.  <br/> Diese Daten können mithilfe der folgenden Syntax in das Textformat konvertiert werden:  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |Die Clientversion des Endpunkts, der den Fehlerbericht sendet. Weitere Informationen finden Sie in der [Tabelle "ClientVersions" in Skype for Business Server 2015.](clientversions.md) <br/> |
|**IsCapturedByServer** <br/> |Bit  <br/> ||Ist der Fehlerbericht, der vom KDS-Agent erfasst wird, der auf dem Front-End-Server ausgeführt oder vom Client gesendet wird.  <br/> |
|**Wert** <br/> |Smallint  <br/> ||Reserviert für zukünftige Verwendung.  <br/> |
|**Telemetrie-ID** <br/> |Uniqueidentifier  <br/> ||Eindeutiger Bezeichner, der die Informationen über den Zeitpunkt des Beitritts für verschiedene in einer Konferenz beteiligten Komponenten korreliert.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**SessionSetupTime** <br/> |Ganzzahl  <br/> ||Für eine bestimmte Komponente erforderliche Zeit (in Millisekunden), um an einer Konferenz teilzunehmen.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**ServerId** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |Stellt den vollqualifizierten Domänennamen des Servers dar, der den Fehlerbericht generiert hat.  <br/> |
|**PoolId** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |Stellt den vollqualifizierten Domänennamen des Pools dar, in dem der Fehlerbericht generiert wurde.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype for Business Server 2015 eingeführt.  <br/> |
   

