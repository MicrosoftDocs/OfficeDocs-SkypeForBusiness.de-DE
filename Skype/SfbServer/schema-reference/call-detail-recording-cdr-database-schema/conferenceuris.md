---
title: ConferenceUris-Tabelle in Skype for Business Server 2015
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
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: 'Bei der ConferenceUris-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Darin wird eine Liste der verschiedenen Konferenz-URIs gespeichert, die an in der Datenbank aufgezeichneten Konferenzsitzungen beteiligt waren. Jeder Datensatz in der Tabelle steht für einen Konferenz-URI.'
---

# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>ConferenceUris-Tabelle in Skype for Business Server 2015
 
Bei der ConferenceUris-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Darin wird eine Liste der verschiedenen Konferenz-URIs gespeichert, die an in der Datenbank aufgezeichneten Konferenzsitzungen beteiligt waren. Jeder Datensatz in der Tabelle steht für einen Konferenz-URI.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |Datum/Uhrzeit  <br/> |Primary  <br/> |Zeitstempel; zu internen Zwecken.  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diesen Konferenz-URI identifiziert.  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> ||Konferenz-URI  <br/> |
|**Prüfsumme** <br/> |int  <br/> ||Prüfsumme von ConferenceUri. Wird verwendet, um die Geschwindigkeit von Datenbanksuchvorgängen zu steigern.  <br/> |
|**UriTypeId** <br/> |int  <br/> |Ausländisch  <br/> |URI-Typ, z. B. conf:chat für Chatkonferenzen oder conf:audio-video für Audio-/Videokonferenzen. Weitere Informationen finden Sie in der [Tabelle "UriTypes"](uritypes.md) . <br/> |
   

