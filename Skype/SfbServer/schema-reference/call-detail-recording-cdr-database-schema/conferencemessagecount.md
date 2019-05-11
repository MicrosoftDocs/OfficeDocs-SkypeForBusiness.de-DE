---
title: ConferenceMessageCount-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Jeder Datensatz in dieser Tabelle stellt einen Benutzer in einer Sofortnachrichtenkonferenz und enthält die Anzahl der Nachrichten, die von diesem Benutzer gesendet. Jede Konferenz wird durch mehrere Datensätze in dieser Tabelle dargestellt. einen Eintrag für jeden Benutzer.
ms.openlocfilehash: f45de53333b23368351c8c5330b474cd3260192b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901429"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>ConferenceMessageCount-Tabelle in Skype für Business Server 2015
 
Jeder Datensatz in dieser Tabelle stellt einen Benutzer in einer Sofortnachrichtenkonferenz und enthält die Anzahl der Nachrichten, die von diesem Benutzer gesendet. Jede Konferenz wird durch mehrere Datensätze in dieser Tabelle dargestellt. einen Eintrag für jeden Benutzer.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primär, Fremd  <br/> |Zeitpunkt des Konferenz-Instanz. Zusammen mit **SessionIdSeq** verwendet zur eindeutigen Identifizierung eine Konferenz-Instanz. [Conferences-Tabelle in Skype für Business Server 2015](conferences.md) Weitere Informationen finden Sie. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primär, Fremd  <br/> |ID-Nummer zum Identifizieren der Konferenz-Instanz. In Verbindung mit **SessionIdTime** verwendet, um eine Instanz der Konferenz eindeutig zu identifizieren. [Conferences-Tabelle in Skype für Business Server 2015](conferences.md) Weitere Informationen finden Sie. <br/> |
|**Benutzer-ID** <br/> |int  <br/> |Ausländisch  <br/> |Eindeutige Zahl, die diesen Benutzer wird aus der [Tabelle Benutzer](users.md)identifiziert.  <br/> |
|**MessageCount** <br/> |smallint  <br/> | <br/> |Die Anzahl der während dieser Konferenz von diesem Benutzer gesendeten Nachrichten.  <br/> |
   

