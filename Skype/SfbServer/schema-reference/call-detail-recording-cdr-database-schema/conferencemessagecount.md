---
title: ConferenceMessageCount-Tabelle in Skype für Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Jeder Datensatz in dieser Tabelle stellt einen Benutzer in einer Sofortnachrichtenkonferenz und enthält die Anzahl der Nachrichten, die von diesem Benutzer gesendet. Jede Konferenz wird durch mehrere Datensätze in dieser Tabelle dargestellt. einen Eintrag für jeden Benutzer.
ms.openlocfilehash: 6b9dfcf0743c03e69726bb501cc7a4a961bf5df8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>ConferenceMessageCount-Tabelle in Skype für Business Server 2015
 
Jeder Datensatz in dieser Tabelle stellt einen Benutzer in einer Sofortnachrichtenkonferenz und enthält die Anzahl der Nachrichten, die von diesem Benutzer gesendet. Jede Konferenz wird durch mehrere Datensätze in dieser Tabelle dargestellt. einen Eintrag für jeden Benutzer.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primär, Fremd  <br/> |Zeitpunkt des Konferenz-Instanz. Zusammen mit **SessionIdSeq** verwendet zur eindeutigen Identifizierung eine Konferenz-Instanz. [Conferences-Tabelle in Skype für Business Server 2015](conferences.md) Weitere Informationen finden Sie. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primär, Fremd  <br/> |ID-Nummer zum Identifizieren der Konferenz-Instanz. In Verbindung mit **SessionIdTime** verwendet, um eine Instanz der Konferenz eindeutig zu identifizieren. [Conferences-Tabelle in Skype für Business Server 2015](conferences.md) Weitere Informationen finden Sie. <br/> |
|**Benutzer-ID** <br/> |int  <br/> |Fremdschlüssel  <br/> |Eindeutige Zahl, die diesen Benutzer wird aus der [Tabelle Benutzer](users.md)identifiziert.  <br/> |
|**MessageCount** <br/> |smallint  <br/> | <br/> |Die Anzahl der während dieser Konferenz von diesem Benutzer gesendeten Nachrichten.  <br/> |
   

