---
title: MCUs-Tabelle in Skype für Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Die Mcus-Tabelle ist eine Tabelle. Jeder Datensatz speichert Informationen über ein Live Meeting-Dienst. Dazu zählen die Sofortnachrichten-Konferenzdienst und der Telefonie-Konferenzdienst (die als Prozesse auf Front-End-Servern ausgeführt werden), und die-Webkonferenzdienst und A / V-Konferenzdienst.
ms.openlocfilehash: 2a85d46e733d230dc7c8096c8804146b19766bcf
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>MCUs-Tabelle in Skype für Business Server 2015
 
Die Mcus-Tabelle ist eine Tabelle. Jeder Datensatz speichert Informationen über ein Live Meeting-Dienst. Dazu zählen die Sofortnachrichten-Konferenzdienst und der Telefonie-Konferenzdienst (die als Prozesse auf Front-End-Servern ausgeführt werden), und die-Webkonferenzdienst und A / V-Konferenzdienst. 
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die Konferenzserver identifiziert.  <br/> |
|**McuUri** <br/> |nvarchar(450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | Fremdschlüssel <br/> |Konferenzservertyp wie Conf:chat (für Sofortnachrichten) oder Conf:audio-video. Finden Sie weitere Informationen der [UriTypes-Tabelle](uritypes.md) . <br/> |
   

