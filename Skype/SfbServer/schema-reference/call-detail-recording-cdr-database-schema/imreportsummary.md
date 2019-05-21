---
title: IMReportSummary-Tabelle in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: Der IMReportSummaryTable stellt einen Gesamtbericht zu den Chat-Sitzungen bereit, die in einer Organisation abgehalten werden. Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 647b8dc3e48e56d126a65f524de90954b7aeca8f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296126"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>IMReportSummary-Tabelle in Skype for Business Server 2015
 
Der IMReportSummaryTable stellt einen Gesamtbericht zu den Chat-Sitzungen bereit, die in einer Organisation abgehalten werden. Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**StartTime** <br/> |datetime  <br/> |Primary  <br/> |Das Datum und die Uhrzeit, zu der die Sofortnachrichtensitzung begonnen hat.  <br/> |
|**TimePeriod** <br/> |Zeichen (1)  <br/> |Primary  <br/> ||
|**PoolFQDN** <br/> |nvarchar (257)  <br/> |Primary  <br/> |Vollständig qualifizierter Domänenname des Pools, der die Sitzung hostet.  <br/> |
|**AuthType** <br/> |int  <br/> |Primary  <br/> |Priorität (beispielsweise dringende oder nicht dringende) des Anrufs. Prioritätsinformationen werden in der [CallPriorities-Tabelle in Skype for Business Server 2015](callpriorities.md)gespeichert.  <br/> |
|**SessionCount gespeichert** <br/> |bigint  <br/> |||
|**MsgCount** <br/> |bigint  <br/> ||Die Gesamtzahl der während der Sitzung ausgetauschten Sofortnachrichten.  <br/> |
   

