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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: Der IMReportSummaryTable stellt einen Gesamtbericht zu den Chat-Sitzungen bereit, die in einer Organisation abgehalten werden. Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: f845a882bb8bd6ba5ca434ffc42a34725cfeac51
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815143"
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
   

