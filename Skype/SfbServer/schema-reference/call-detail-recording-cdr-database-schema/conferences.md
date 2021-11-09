---
title: Konferenztabelle in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: Jeder Datensatz in dieser Tabelle enthält Anrufdetails zu einer Konferenz.
ms.openlocfilehash: cbcda30c47b4bbeac012f80d64f297a9a1259f2c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60838447"
---
# <a name="conferences-table-in-skype-for-business-server-2015"></a>Konferenztabelle in Skype for Business Server 2015
 
Jeder Datensatz in dieser Tabelle enthält Anrufdetails zu einer Konferenz.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datum/Uhrzeit  <br/> |Primary  <br/> |Zeitpunkt, zu dem die Konferenzanfrage vom KDS-Agent erfasst wurde. Wird nur als Primärschlüssel verwendet, um eine Konferenzinstanz eindeutig zu identifizieren.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |ID zur Identifikation der Sitzung. Wird in Verbindung mit **SessionIdTime** verwendet, um eine Konferenzinstanz eindeutig zu identifizieren. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Ausländisch  <br/> |Konferenz-URI Weitere Informationen finden Sie in der [ConferenceUris-Tabelle in Skype for Business Server 2015.](conferenceuris.md) <br/> |
|**ConfInstance** <br/> |Uniqueidentifier  <br/> | <br/> |Nützlich für wiederkehrende Konferenzen; Jede Instanz einer wiederkehrenden Konferenz hat den gleichen **ConferenceUri,** hat jedoch eine andere **ConfInstance**. <br/> |
|**ConferenceStartTime** <br/> |Datum/Uhrzeit  <br/> | <br/> |Startzeit der Konferenz.  <br/> |
|**ConferenceEndTime** <br/> |Datum/Uhrzeit  <br/> | <br/> |Startzeit der Konferenz.  <br/> |
|**PoolId** <br/> |int  <br/> |Ausländisch  <br/> |ID-Nummer zum Identifizieren des Pools, in dem die Konferenz erfasst wurde. Weitere Informationen finden Sie in der [Tabelle "Pools".](pools.md) <br/> |
|**OrganizerId** <br/> |Int  <br/> |Ausländisch  <br/> |ID-Nummer, um den Organisator-URI dieser Konferenz zu identifizieren. Weitere Informationen finden Sie in der [Tabelle "Benutzer".](users.md) <br/> |
|**Wert** <br/> |Smallint  <br/> || Eine Bitmaske, die Konferenzattribute enthält. Die folgenden Werte sind möglich: <br/>  0X01 <br/>  Synthetische <br/>  Transaction <br/> |
|**Verarbeitet** <br/> |Bit  <br/> ||Internes Feld, das vom Überwachungsdienst verwendet wird.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype for Business Server 2015 eingeführt.  <br/> |
   
\* Für die meisten Sitzungen hat SessionIdSeq den Wert 1. Wenn zwei Sitzungen genau zur gleichen Zeit beginnen, lautet der SessionIdSeq für eine 1, für die andere 2 usw.
  

