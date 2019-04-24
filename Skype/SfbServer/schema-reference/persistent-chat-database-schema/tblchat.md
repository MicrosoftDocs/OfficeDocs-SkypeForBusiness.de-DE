---
title: tblChat
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: TblChat enthält alle Chatnachrichten.
ms.openlocfilehash: 54e19fe729d9f96afb04d22a917864118de75efe
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212649"
---
# <a name="tblchat"></a>tblChat
 
TblChat enthält alle Chatnachrichten.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|channelId  <br/> |Int, nicht null  <br/> |Knoten-ID  <br/> |
|chatId  <br/> |Bigint, nicht null  <br/> |Eindeutige fortlaufende Zahl (pro Knoten-ID), die die Reihenfolge der Chatrooms, generiert von der TblLastChatId-Tabelle definiert.  <br/> |
|chatDate  <br/> |Bigint, nicht null  <br/> |Zeitstempel für die Chatnachricht.  <br/> |
|Benutzer-ID  <br/> |Int, nicht null  <br/> |Prinzipal-ID des bereitstellers.  <br/> |
|isAlert  <br/> |Bit, nicht null  <br/> |True, wenn die Nachricht eine Warnung an. False, wenn es nicht der Fall ist.  <br/> |
|Inhalt  <br/> |Nvarchar (Max), nicht null  <br/> | Chatinhalte (die nur-Text-Version). Der Inhalt ist in der Regel im nur-Text mit den folgenden Ausnahmen: <br/>  Dateien werden als Ma-Filelink dargestellt: Links. <br/>  Links werden als HTML-Elemente dargestellt (obwohl des Inhaltstyps HTML angesehen werden kann). <br/>  Textabschnitte werden als ein "[STORY]..." codiert-Format. <br/> |
|RTF  <br/> |varchar(max)  <br/> |Chatinhalte (die RTF-Version). Möglicherweise Null, wenn der Client es zur Verfügung steht.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|\<ChannelID chatD\>  <br/> |Primärschlüssel.  <br/> |
   

