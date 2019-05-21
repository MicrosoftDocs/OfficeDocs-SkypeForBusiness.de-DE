---
title: tblChat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: tblChat enthält alle Chatnachrichten.
ms.openlocfilehash: 15c7030fe14f62c5d32af54c0f5a6901da3f977b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295538"
---
# <a name="tblchat"></a>tblChat
 
tblChat enthält alle Chatnachrichten.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|Kanal-Nr  <br/> |int, nicht NULL  <br/> |Knoten-ID.  <br/> |
|Chat-Funktion  <br/> |bigint, nicht NULL  <br/> |Eindeutige sequenzielle Nummer (pro Knoten-ID), die die von der tblLastChatId-Tabelle generierte Chatroom-Reihenfolge definiert.  <br/> |
|chatDate  <br/> |bigint, nicht NULL  <br/> |Zeitstempel für die Chatnachricht.  <br/> |
|UserID  <br/> |int, nicht NULL  <br/> |Prinzipal-ID des Plakats.  <br/> |
|isalert  <br/> |Bit, nicht NULL  <br/> |"True", wenn es sich bei der Nachricht um eine Warnmeldung handelt. False, wenn dies nicht der Fall ist.  <br/> |
|Inhalts  <br/> |nvarchar (max), nicht NULL  <br/> | Chat-Inhalt (die nur-Text-Version). Der Inhalt befindet sich normalerweise im nur-Text-Stil mit den folgenden Ausnahmen: <br/>  Dateien werden als MA-FileLink: Links dargestellt. <br/>  Links werden als HTML-Element dargestellt (auch wenn der Inhaltstyp nicht als HTML betrachtet werden kann). <br/>  Stories werden als "[Story]...."-ähnliches Format codiert. <br/> |
|RTF  <br/> |varchar (max)  <br/> |Chat-Inhalt (die RTF-Version). Kann NULL sein, wenn der Client Sie nicht bereitstellt.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|\<Kanal-Nr, Chat\>  <br/> |Primärschlüssel  <br/> |
   

