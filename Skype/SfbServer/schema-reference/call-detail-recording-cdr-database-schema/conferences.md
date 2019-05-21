---
title: Konferenz Tabelle in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: Jeder Datensatz in dieser Tabelle enthält Anrufdetails zu einer Konferenz.
ms.openlocfilehash: 41a2a25e80b073b568152422defeee1ca3e2ac19
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296448"
---
# <a name="conferences-table-in-skype-for-business-server-2015"></a>Konferenz Tabelle in Skype for Business Server 2015
 
Jeder Datensatz in dieser Tabelle enthält Anrufdetails zu einer Konferenz.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionID** <br/> |datetime  <br/> |Primary  <br/> |Uhrzeit, zu der die Konferenzanforderung vom CdR-Agenten erfasst wurde. Wird nur als Primärschlüssel verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |Die ID-Nummer, um die Sitzung zu identifizieren. Wird in Verbindung mit **SessionID** -Mal verwendet, um eine Konferenz Instanz eindeutig zu identifizieren. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Fremd  <br/> |Konferenz-URI Weitere Informationen finden Sie [in der Tabelle ConferenceUris in Skype for Business Server 2015](conferenceuris.md) . <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> | <br/> |Nützlich für wiederkehrende Konferenzen; jede Instanz einer Besprechungsserie hat dieselbe **ConferenceUri**, hat aber eine andere **ConfInstance**. <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> | <br/> |Startzeit der Konferenz  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> | <br/> |Startzeit der Konferenz  <br/> |
|**Pool-Nr** <br/> |int  <br/> |Fremd  <br/> |Die ID-Nummer zur Identifizierung des Pools, in dem die Konferenz aufgenommen wurde. Weitere Informationen finden Sie in der [Tabelle Pools](pools.md) . <br/> |
|**Organizer-Nr** <br/> |Int  <br/> |Fremd  <br/> |Die ID-Nummer zum Identifizieren des Organisator-URIs dieser Konferenz. Weitere Informationen finden Sie in der [Tabelle "Benutzer](users.md) ". <br/> |
|**Kennzeichnen** <br/> |smallint  <br/> || Eine Bitmaske, die Konferenz Attribute enthält. Mögliche Werte: <br/>  0X01 <br/>  Synthetischen <br/>  Transaktion <br/> |
|**Verarbeitet** <br/> |bit  <br/> ||Internes Feld, das vom Überwachungsdienst verwendet wird.  <br/> Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype for Business Server 2015 eingeführt.  <br/> |
   
\*Bei den meisten Sitzungen erhält SessionIdSeq den Wert 1. Wenn zwei Sitzungen genau zur gleichen Zeit beginnen, ist der SessionIdSeq für einen 1, und für den anderen wird 2 usw.
  

