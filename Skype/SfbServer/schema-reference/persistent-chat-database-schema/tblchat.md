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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: tblChat enthält alle Chatnachrichten.
ms.openlocfilehash: 7221136c435c1d4af836174ddfde5cbd02f4c5f6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814673"
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
   

