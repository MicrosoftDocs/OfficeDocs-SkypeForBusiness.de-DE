---
title: Tabelle "Konferenzen" in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: Jeder Datensatz in dieser Tabelle enthält Anrufdetails zu einer Konferenz.
ms.openlocfilehash: 85da16807d6f314fb4f9239601c77a7aed2842ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813215"
---
# <a name="conferences-table-in-skype-for-business-server-2015"></a>Tabelle "Konferenzen" in Skype for Business Server 2015
 
Jeder Datensatz in dieser Tabelle enthält Anrufdetails zu einer Konferenz.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datum/Uhrzeit  <br/> |Primary  <br/> |Zeitpunkt, zu dem die Konferenzanforderung vom Agent für die Telefonkonferenz erfasst wurde. Wird nur als Primärschlüssel verwendet, um eine Konferenzinstanz eindeutig zu identifizieren.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |ID zur Identifikation der Sitzung. Wird in Verbindung mit **SessionIdTime verwendet,** um eine Konferenzinstanz eindeutig zu identifizieren. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Fremd  <br/> |Konferenz-URI Weitere Informationen finden Sie in der [Tabelle "ConferenceUris" in Skype for Business Server 2015.](conferenceuris.md) <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> | <br/> |Nützlich für wiederkehrende Konferenzen; Jede Instanz einer wiederkehrenden Konferenz hat denselben **ConferenceUri,** hat jedoch eine andere **ConfInstance**. <br/> |
|**ConferenceStartTime** <br/> |Datum/Uhrzeit  <br/> | <br/> |Startzeit der Konferenz.  <br/> |
|**ConferenceEndTime** <br/> |Datum/Uhrzeit  <br/> | <br/> |Startzeit der Konferenz.  <br/> |
|**PoolId** <br/> |int  <br/> |Fremd  <br/> |ID zum Identifizieren des Pools, in dem die Konferenz erfasst wurde. Weitere Informationen [finden Sie in der Tabelle "Pools".](pools.md) <br/> |
|**OrganizerId** <br/> |Int  <br/> |Fremd  <br/> |ID-Nummer, um den Organisator-URI dieser Konferenz zu identifizieren. Weitere Informationen [finden Sie in der Tabelle](users.md) "Benutzer". <br/> |
|**Wert** <br/> |smallint  <br/> || Eine Bitmaske, die Konferenzattribute enthält. Die folgenden Werte sind möglich: <br/>  0X01 <br/>  Synthetic <br/>  Transaction <br/> |
|**Verarbeitet** <br/> |bit  <br/> ||Internes Feld, das vom Überwachungsdienst verwendet wird.  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype for Business Server 2015 eingeführt.  <br/> |
   
\* Für die meisten Sitzungen hat SessionIdSeq den Wert 1. Wenn zwei Sitzungen genau zur gleichen Zeit gestartet werden, ist "SessionIdSeq" für eine Sitzung "1", für die andere "2" und so weiter.
  

