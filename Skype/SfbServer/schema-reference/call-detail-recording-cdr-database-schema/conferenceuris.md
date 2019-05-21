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
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: Die Tabelle ConfereneUris ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Konferenz-URIs gespeichert ist, die an Konferenzsitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden. Jeder Datensatz in der Tabelle steht für einen Konferenz-URI.
ms.openlocfilehash: 60f9952fa1fcc5b1a1a651c44beaed894a387b81
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296392"
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
   

