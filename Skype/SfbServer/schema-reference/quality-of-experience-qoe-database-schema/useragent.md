---
title: Tabelle "UserAgent"
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
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: Die Tabelle "UserAgent" ist eine Tabelle, in der eine Liste der verschiedenen Benutzeragenten gespeichert ist, die an in der Datenbank aufgezeichneten Sitzungen teilgenommen haben. Jeder Datensatz in der Tabelle stellt einen Benutzer-Agent dar.
ms.openlocfilehash: a1d0e647ff78d409555988a27592228fac2643be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799935"
---
# <a name="useragent-table"></a>Tabelle "UserAgent"
 
Die Tabelle "UserAgent" ist eine Tabelle, in der eine Liste der verschiedenen Benutzeragenten gespeichert ist, die an in der Datenbank aufgezeichneten Sitzungen teilgenommen haben. Jeder Datensatz in der Tabelle stellt einen Benutzer-Agent dar.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diesen Benutzer-Agent identifiziert.  <br/> |
|**UserAgent** <br/> |nvarchar(256)  <br/> |Eigen  <br/> |Zeichenfolge des Benutzer-Agents.  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1 ist der Vermittlungsserver.  <br/> 2 ist ein A/V-Konferenzserver.  <br/> 4 ist Skype for Business.  <br/> 8 ist IP Phone.  <br/> 16 ist live Meeting Console.  <br/> 32 ist das Tool zur Überprüfung der Bereitstellung (Deployment Validation Tool, DVT).  <br/> 64 ist Skype for Business Server auf Macintosh-Computern.  <br/> 128 ist die Skype for Business Server Attendant.  <br/> 256 ist der Konferenzankündigungsdienst.  <br/> 512 ist automatische Telefonzentrale.  <br/> 1024 ist reaktionsgruppe anwendung.  <br/> 2048 ist außerhalb der Sprachsteuerung.  <br/> |
   

