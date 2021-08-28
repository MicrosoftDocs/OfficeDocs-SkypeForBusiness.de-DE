---
title: UserAgent-Tabelle
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: Die UserAgent-Tabelle ist eine Unterstützende Tabelle, in der eine Liste der verschiedenen Benutzer-Agents gespeichert wird, die an in der Datenbank aufgezeichneten Sitzungen teilgenommen haben. Jeder Datensatz in der Tabelle stellt einen Benutzer-Agent dar.
ms.openlocfilehash: 0c23582550e659f4a48661c80770c385e168ed3c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58590059"
---
# <a name="useragent-table"></a>UserAgent-Tabelle
 
Die UserAgent-Tabelle ist eine Unterstützende Tabelle, in der eine Liste der verschiedenen Benutzer-Agents gespeichert wird, die an in der Datenbank aufgezeichneten Sitzungen teilgenommen haben. Jeder Datensatz in der Tabelle stellt einen Benutzer-Agent dar.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diesen Benutzer-Agent identifiziert.  <br/> |
|**UserAgent** <br/> |nvarchar(256)  <br/> |Eigen  <br/> |Benutzer-Agent-Zeichenfolge.  <br/> |
|**UAType** <br/> |Smallint  <br/> | <br/> |1 ist Vermittlungsserver.  <br/> 2 ist ein A/V-Konferenzserver.  <br/> 4 ist Skype for Business.  <br/> 8 ist IP-Telefon.  <br/> 16 ist live Meeting Console.  <br/> 32 ist das Deployment Validation Tool (DVT).  <br/> 64 ist auf Macintosh-Computern Skype for Business Server.  <br/> 128 ist Skype for Business Server Attendant.  <br/> 256 ist Konferenzankündigung Dienst.  <br/> 512 ist die automatische Telefonzentrale für Konferenzen.  <br/> 1024 ist reaktionsgruppenanwendung.  <br/> 2048 ist außerhalb der Sprachsteuerung.  <br/> |
   

