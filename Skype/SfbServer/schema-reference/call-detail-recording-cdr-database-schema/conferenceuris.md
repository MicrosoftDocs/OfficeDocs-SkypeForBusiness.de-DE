---
title: ConferenceUris-Tabelle in Skype for Business Server 2015
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
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: Die Tabelle ConfereneUris ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Konferenz-URIs gespeichert ist, die an Konferenzsitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden. Jeder Datensatz in der Tabelle steht für einen Konferenz-URI.
ms.openlocfilehash: f1e95cce4fedf26477973a4fba6a9d3a32288f92
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815313"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>ConferenceUris-Tabelle in Skype for Business Server 2015
 
Die Tabelle ConfereneUris ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Konferenz-URIs gespeichert ist, die an Konferenzsitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden. Jeder Datensatz in der Tabelle steht für einen Konferenz-URI.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> |Primary  <br/> |Zeitstempel, intern verwendet.  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Primary  <br/> |Eindeutige Nummer, die diesen Konferenz-URI kennzeichnet.  <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> ||Konferenz-URI  <br/> |
|**Prüfsumme** <br/> |int  <br/> ||Prüfsumme von ConferenceUri. Wird verwendet, um die Geschwindigkeit von Datenbanksuchen zu erhöhen.  <br/> |
|**UriTypeId** <br/> |int  <br/> |Fremd  <br/> |URI-Typ wie conf: Chat für im-Konferenz oder conf: Audio-Video für Audio/Video-Konferenz. Weitere Informationen finden Sie in der [Tabelle UriTypes](uritypes.md) . <br/> |
   

