---
title: ConferenceMessageCount-Tabelle in Skype for Business Server 2015
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
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Jeder Datensatz in dieser Tabelle steht für einen Benutzer in einer Chat Konferenz und enthält die Anzahl der von diesem Benutzer gesendeten Nachrichten. Jede Konferenz wird durch mehrere Datensätze in dieser Tabelle dargestellt. ein Datensatz für jeden Benutzer.
ms.openlocfilehash: 66651f798d627ef4ea783c4ecf4e7cb8f1adab81
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815373"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>ConferenceMessageCount-Tabelle in Skype for Business Server 2015
 
Jeder Datensatz in dieser Tabelle steht für einen Benutzer in einer Chat Konferenz und enthält die Anzahl der von diesem Benutzer gesendeten Nachrichten. Jede Konferenz wird durch mehrere Datensätze in dieser Tabelle dargestellt. ein Datensatz für jeden Benutzer.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionID** <br/> |datetime  <br/> |Primär, fremd  <br/> |Uhrzeit der Konferenz Instanz. Wird in Verbindung mit **SessionIdSeq** verwendet, um eine Konferenz Instanz eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle "Konferenzen" in Skype for Business Server 2015](conferences.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primär, fremd  <br/> |Die ID-Nummer zum Identifizieren der Konferenz Instanz. Wird in Verbindung mit **SessionID** -Mal verwendet, um eine Konferenz Instanz eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle "Konferenzen" in Skype for Business Server 2015](conferences.md) . <br/> |
|**UserID** <br/> |int  <br/> |Fremd  <br/> |Eindeutige Nummer, die diesen Benutzer identifiziert, auf die in der [Tabelle "Benutzer](users.md)" verwiesen wird.  <br/> |
|**MessageCount** <br/> |smallint  <br/> | <br/> |Die Anzahl der Nachrichten, die dieser Benutzer während dieser Konferenz gesendet hat.  <br/> |
   

