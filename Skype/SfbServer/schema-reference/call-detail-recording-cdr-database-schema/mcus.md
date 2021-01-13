---
title: Tabelle "Mcus" in Skype for Business Server 2015
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
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Bei der Tabelle "Mcus" handelt es sich um eine Tabelle mit Unterstützung. Jeder Datensatz speichert Informationen zu einem Konferenzdienst. Dazu können der Imkonferenzdienst und der Telefoniekonferenzdienst (die als Prozesse auf Front-End-Servern ausgeführt werden) sowie der Webkonferenzdienst und der A/V-Konferenzdienst gehören.
ms.openlocfilehash: fe43bfc747cd08febe00a68925ad520b6add5846
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821425"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Tabelle "Mcus" in Skype for Business Server 2015
 
Bei der Tabelle "Mcus" handelt es sich um eine Tabelle mit Unterstützung. Jeder Datensatz speichert Informationen zu einem Konferenzdienst. Dazu können der Imkonferenzdienst und der Telefoniekonferenzdienst (die als Prozesse auf Front-End-Servern ausgeführt werden) sowie der Webkonferenzdienst und der A/V-Konferenzdienst gehören. 
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Primary  <br/> |Eindeutige Nummer, die diesen Konferenzserver identifiziert.  <br/> |
|**McuUri** <br/> |nvarchar(450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | Fremd <br/> |Konferenzservertyp, z. B. conf:chat (für IMs) oder conf:audio-video. Weitere Informationen finden Sie in der [Tabelle "UriTypes".](uritypes.md) <br/> |
   

