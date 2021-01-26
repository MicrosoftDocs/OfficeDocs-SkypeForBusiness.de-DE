---
title: Tabelle "IMReportSummary" in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: Die IMReportSummaryTable enthält einen Gesamtbericht über die In-Messaging-Sitzungen, die in einer Organisation abgehalten werden. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 6a80918376440c13d60e059744d88c09c2705853
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821525"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>Tabelle "IMReportSummary" in Skype for Business Server 2015
 
Die IMReportSummaryTable enthält einen Gesamtbericht über die In-Messaging-Sitzungen, die in einer Organisation abgehalten werden. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**StartTime** <br/> |Datum/Uhrzeit  <br/> |Primary  <br/> |Datum und Uhrzeit, an dem bzw. zu der die Chatsitzung begann.  <br/> |
|**TimePeriod** <br/> |char(1)  <br/> |Primary  <br/> ||
|**PoolFQDN** <br/> |nvarchar(257)  <br/> |Primary  <br/> |Vollqualifizierter Domänenname des Pools, der die Sitzung hostet.  <br/> |
|**AuthType** <br/> |int  <br/> |Primary  <br/> |Priorität (z. B. dringend oder nicht dringend) des Anrufs. Prioritätsinformationen werden in der [Tabelle "CallPriorities" in Skype for Business Server 2015 gespeichert.](callpriorities.md)  <br/> |
|**SessionCount** <br/> |bigint  <br/> |||
|**MsgCount** <br/> |bigint  <br/> ||Die Gesamtzahl der Chatnachrichten, die während der Sitzung ausgetauscht wurden.  <br/> |
   

