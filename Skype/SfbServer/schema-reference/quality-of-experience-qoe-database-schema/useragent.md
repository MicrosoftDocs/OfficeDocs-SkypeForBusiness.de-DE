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
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: Die UserAgent-Tabelle ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Benutzer-Agents gespeichert ist, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden. Jeder Datensatz in der Tabelle steht für einen Benutzer-Agent
ms.openlocfilehash: f0c8a2f182611887db1324d17b6b7c28d6a9393d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294586"
---
# <a name="useragent-table"></a>UserAgent-Tabelle
 
Die UserAgent-Tabelle ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Benutzer-Agents gespeichert ist, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden. Jeder Datensatz in der Tabelle steht für einen Benutzer-Agent
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Nummer, die diesen Benutzer-Agent kennzeichnet.  <br/> |
|**UserAgent** <br/> |nvarchar(256)  <br/> |Eindeutigen  <br/> |Benutzer-Agent-Zeichenfolge.  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1 ist ein Vermittlungs Server.  <br/> 2 ist ein/V-Konferenz Server.  <br/> 4 ist Skype for Business.  <br/> 8 ist IP Phone.  <br/> 16 ist eine Live Meeting-Konsole.  <br/> 32 ist ein Bereitstellungs Überprüfungs Tool (Thrombose).  <br/> 64 ist Skype for Business Server auf Macintosh-Computern.  <br/> 128 ist Skype for Business Server Attendant.  <br/> 256 ist ein Konferenzankündigungsdienst.  <br/> 512 ist eine automatische Konferenzzentrale.  <br/> 1024 ist eine reaktionsgruppenanwendung.  <br/> 2048 ist außerhalb der Sprachsteuerung.  <br/> |
   

