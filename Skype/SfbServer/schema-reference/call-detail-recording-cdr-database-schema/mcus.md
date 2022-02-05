---
title: Mcus-Tabelle in Skype for Business Server 2015
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
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Die Mcus-Tabelle ist eine Unterstützende Tabelle. Jeder Datensatz speichert Informationen zu einem Konferenzdienst. Dazu gehören der Chatkonferenzdienst und der Telefoniekonferenzdienst (der als Prozesse auf Front-End-Servern ausgeführt wird) sowie der Webkonferenzdienst und der A/V-Konferenzdienst.
---

# <a name="mcus-table-in-skype-for-business-server-2015"></a>Mcus-Tabelle in Skype for Business Server 2015
 
Die Mcus-Tabelle ist eine Unterstützende Tabelle. Jeder Datensatz speichert Informationen zu einem Konferenzdienst. Dazu gehören der Chatkonferenzdienst und der Telefoniekonferenzdienst (der als Prozesse auf Front-End-Servern ausgeführt wird) sowie der Webkonferenzdienst und der A/V-Konferenzdienst. 
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Primary  <br/> |Eindeutige Nummer, die diesen Konferenzserver identifiziert.  <br/> |
|**McuUri** <br/> |nvarchar(450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | Ausländisch <br/> |Konferenzservertyp, z. B. conf:chat (für IMs) oder conf:audio-video. Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) . <br/> |
   

