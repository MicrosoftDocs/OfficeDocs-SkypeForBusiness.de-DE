---
title: tblChat
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
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: tblChat enthält alle Chatnachrichten.
---

# <a name="tblchat"></a>tblChat
 
tblChat enthält alle Chatnachrichten.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|channelId  <br/> |int, nicht NULL  <br/> |Knoten-ID  <br/> |
|chatId  <br/> |bigint, nicht NULL  <br/> |Eindeutige fortlaufende Zahl (pro Knoten-ID), die die Reihenfolge der Chatrooms identifiziert, generiert von der tblLastChatId-Tabelle.  <br/> |
|chatDate  <br/> |bigint, nicht NULL  <br/> |Zeitstempel für die Chatnachricht.  <br/> |
|userId  <br/> |int, nicht NULL  <br/> |Prinzipal-ID des Bereitstellers.  <br/> |
|isAlert  <br/> |bit, nicht NULL  <br/> |TRUE, wenn es sich bei der Nachricht um eine Fehlermeldung handelt, andernfalls FALSE.  <br/> |
|content  <br/> |nvarchar (max), nicht NULL  <br/> | Chatinhalt (Nur-Text-Version). Der Inhalt ist normalerweise einfacher Text mit den folgenden Ausnahmen: <br/>  Dateien sind als Links vom Typ ma-filelink: dargestellt. <br/>  Links sind als HTML-Elemente dargestellt (obwohl der Inhaltstyp nicht als HTML betrachtet werden kann). <br/>  Storys werden als "[STORY]...."-ähnliches Format codiert. <br/> |
|RTF  <br/> |varchar(max)  <br/> |Chatinhalt (RTF-Version). Kann Null sein, wenn der Client ihn nicht bereitstellt.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|\<channelID, chatD\>  <br/> |Primärschlüssel  <br/> |
   

