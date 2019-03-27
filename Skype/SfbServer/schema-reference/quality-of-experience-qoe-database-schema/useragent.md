---
title: UserAgent-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: Die UserAgent-Tabelle ist eine Tabelle, die eine Liste der verschiedenen Benutzer-Agenten gespeichert, die in der Datenbank aufgezeichnet Sitzungen teilgenommen haben. Jeder Datensatz in der Tabelle steht für eine Benutzer-agent
ms.openlocfilehash: 17cb395569e8a634925be27705b878b104a3b70a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893104"
---
# <a name="useragent-table"></a>UserAgent-Tabelle
 
Die UserAgent-Tabelle ist eine Tabelle, die eine Liste der verschiedenen Benutzer-Agenten gespeichert, die in der Datenbank aufgezeichnet Sitzungen teilgenommen haben. Jeder Datensatz in der Tabelle steht für eine Benutzer-agent
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diesen Benutzer-Agent identifiziert.  <br/> |
|**UserAgent** <br/> |nvarchar(256)  <br/> |Eindeutige  <br/> |Benutzeragenten-Zeichenfolge.  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1: Vermittlungsserver.  <br/> 2 ist die A / V-Konferenzserver.  <br/> 4 ist Skype für Unternehmen.  <br/> 8: IP-Telefon  <br/> 16 ist Live Meeting-Konsole.  <br/> 32 ist Deployment Validation Tool (DVT).  <br/> 64: Skype für Business Server auf Macintosh-Computern.  <br/> 128 ist Skype für Business Server Attendant.  <br/> 256 ist konferenzankündigungsdienst.  <br/> 512 ist die automatische Konferenzzentrale.  <br/> 1024 ist die Anwendung "Reaktionsgruppe".  <br/> 2048 ist Lautstärkeregler.  <br/> |
   

