---
title: Tabelle "FileTransfers" in Skype for Business Server 2015
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
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: Jeder Datensatz steht für eine Dateiübertragungssitzung.
ms.openlocfilehash: fde871bb434a2aa458bc59cfdf098c82ba3a7093
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821695"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a>Tabelle "FileTransfers" in Skype for Business Server 2015
 
Jeder Datensatz steht für eine Dateiübertragungssitzung.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datum/Uhrzeit  <br/> |Primär, Fremd  <br/> |Zeitpunkt der Sitzungsanforderung. Wird zusammen mit **SessionIdSeq** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen [finden Sie in der Tabelle "Dialogfelder" in Skype for Business Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primär, Fremd  <br/> |ID zur Identifikation der Sitzung. Wird zusammen mit **SessionIdTime** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen [finden Sie in der Tabelle "Dialogfelder" in Skype for Business Server 2015.](dialogs.md) <br/> |
|**File Name** <br/> |nvarchar(256)  <br/> ||Name der Datei.  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> ||Eindeutige ID zum Unterscheiden zwischen Dateiübertragungen mit dem gleichen Dateinamen.  <br/> |
|**Cookie** <br/> |nvarchar(128)  <br/> |Primary  <br/> |Wird verwendet, um jede Nachricht zur Nachverfolgung als hiermit zugeordnet zu identifizieren.  <br/> |
|**Accept** <br/> |bit  <br/> ||Kann TRUE oder NULL sein. Falls TRUE erhalten Reject und Cancel den Wert NULL.  <br/> |
|**Reject** <br/> |bit  <br/> ||Kann TRUE oder NULL sein. Falls TRUE erhalten Accept und Cancel den Wert NULL.  <br/> |
|**Cancel** <br/> |bit  <br/> ||Kann TRUE oder NULL sein. Falls TRUE erhalten Accept und Reject den Wert NULL.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype for Business Server 2015 eingeführt.  <br/> |
   

