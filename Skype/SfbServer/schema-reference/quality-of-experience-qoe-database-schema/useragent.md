---
title: UserAgent-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: Die UserAgent-Tabelle ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Benutzer-Agents gespeichert ist, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden. Jeder Datensatz in der Tabelle steht für einen Benutzer-Agent
ms.openlocfilehash: d0a287881a352801d237894c5b150b5a08d91fc8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805053"
---
# <a name="useragent-table"></a>UserAgent-Tabelle
 
Die UserAgent-Tabelle ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Benutzer-Agents gespeichert ist, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden. Jeder Datensatz in der Tabelle steht für einen Benutzer-Agent
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Nummer, die diesen Benutzer-Agent kennzeichnet.  <br/> |
|**UserAgent** <br/> |nvarchar(256)  <br/> |Eindeutigen  <br/> |Benutzer-Agent-Zeichenfolge.  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1 ist ein Vermittlungs Server.  <br/> 2 ist ein/V-Konferenz Server.  <br/> 4 ist Skype for Business.  <br/> 8 ist IP Phone.  <br/> 16 ist eine Live Meeting-Konsole.  <br/> 32 ist ein Bereitstellungs Überprüfungs Tool (Thrombose).  <br/> 64 ist Skype for Business Server auf Macintosh-Computern.  <br/> 128 ist Skype for Business Server Attendant.  <br/> 256 ist ein Konferenzankündigungsdienst.  <br/> 512 ist eine automatische Konferenzzentrale.  <br/> 1024 ist eine reaktionsgruppenanwendung.  <br/> 2048 ist außerhalb der Sprachsteuerung.  <br/> |
   

