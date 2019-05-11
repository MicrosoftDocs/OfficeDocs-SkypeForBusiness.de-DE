---
title: ConferenceUris-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: Die ConfereneUris-Tabelle ist eine Tabelle, die speichert eine Liste der verschiedenen Konferenz-URIs, die in der Datenbank aufgezeichnet konferenzsitzungen teilgenommen haben. Jeder Datensatz in der Tabelle steht für eine Konferenz-URI.
ms.openlocfilehash: 70cb3ccecf1c63dd128cbffd6ac205e77c771835
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901066"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>ConferenceUris-Tabelle in Skype für Business Server 2015
 
Die ConfereneUris-Tabelle ist eine Tabelle, die speichert eine Liste der verschiedenen Konferenz-URIs, die in der Datenbank aufgezeichnet konferenzsitzungen teilgenommen haben. Jeder Datensatz in der Tabelle steht für eine Konferenz-URI.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> |Primary  <br/> |Zeitstempel; zu internen Zwecken.  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diesen Konferenz-URI identifiziert.  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> ||Konferenz-URI.  <br/> |
|**Prüfsumme** <br/> |int  <br/> ||Prüfsumme der ConferenceUri. Verwendet zum erhöht die Geschwindigkeit der Datenbank suchen.  <br/> |
|**UriTypeId** <br/> |int  <br/> |Ausländisch  <br/> |URI-Typ, wie etwa Conf:chat für Instant Messaging-Konferenz oder Conf:audio-video für Audio-Video-Konferenz. Finden Sie weitere Informationen die [UriTypes-Tabelle](uritypes.md) -Tabelle. <br/> |
   

