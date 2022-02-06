---
title: ConferenceMessageCount-Tabelle in Skype for Business Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Jeder Datensatz in dieser Tabelle stellt einen Benutzer in einer Chatkonferenz dar und enthält die Anzahl der von diesem Benutzer gesendeten Nachrichten. Jede Konferenz wird durch mehrere Datensätze in dieser Tabelle dargestellt. ein Datensatz für jeden Benutzer.
---

# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>ConferenceMessageCount-Tabelle in Skype for Business Server 2015
 
Jeder Datensatz in dieser Tabelle stellt einen Benutzer in einer Chatkonferenz dar und enthält die Anzahl der von diesem Benutzer gesendeten Nachrichten. Jede Konferenz wird durch mehrere Datensätze in dieser Tabelle dargestellt. ein Datensatz für jeden Benutzer.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datum/Uhrzeit  <br/> |Primär, Fremd  <br/> |Zeitpunkt der Konferenzinstanz. Wird in Verbindung mit **SessionIdSeq** verwendet, um eine Konferenzinstanz eindeutig zu identifizieren. Weitere Informationen finden [Sie in der Tabelle "Konferenzen" in Skype for Business Server 2015](conferences.md). <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primär, Fremd  <br/> |ID zur Identifikation der Konferenzinstanz. Wird in Verbindung mit **SessionIdTime** verwendet, um eine Konferenzinstanz eindeutig zu identifizieren. Weitere Informationen finden [Sie in der Tabelle "Konferenzen" in Skype for Business Server 2015](conferences.md). <br/> |
|**UserId** <br/> |int  <br/> |Ausländisch  <br/> |Unique number identifying this user, referenced from the [Users table](users.md).  <br/> |
|**MessageCount** <br/> |Smallint  <br/> | <br/> |Die Anzahl der Nachrichten, die dieser Benutzer während dieser Konferenz gesendet hat.  <br/> |
   

