---
title: IMReportSummary-Tabelle in Skype für Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: Die IMReportSummaryTable stellt einen Gesamtbericht auf die chatsitzungen in einer Organisation bereit. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: f716a7406f4cf3562e2fa9244e8a766ef8537f53
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>IMReportSummary-Tabelle in Skype für Business Server 2015
 
Die IMReportSummaryTable stellt einen Gesamtbericht auf die chatsitzungen in einer Organisation bereit. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**StartTime** <br/> |datetime  <br/> |Primary  <br/> |Datum und Uhrzeit des Beginns die instant messaging-Sitzung.  <br/> |
|**TimePeriod** <br/> |vom Datentyp char(1)  <br/> |Primary  <br/> ||
|**"Poolfqdn"** <br/> |nvarchar(257)  <br/> |Primary  <br/> |Vollqualifizierter Domänenname des Pools, der die Sitzung hostet.  <br/> |
|**AuthType** <br/> |int  <br/> |Primary  <br/> |Priorität (beispielsweise dringend oder nicht dringend) des Anrufs. Prioritätsinformationen werden in der [CallPriorities-Tabelle in Skype für Business Server 2015](callpriorities.md)gespeichert.  <br/> |
|**SessionCount** <br/> |bigint  <br/> |||
|**MsgCount** <br/> |bigint  <br/> ||Gesamtzahl der Sofortnachrichten, die während der Sitzung ausgetauscht.  <br/> |
   

