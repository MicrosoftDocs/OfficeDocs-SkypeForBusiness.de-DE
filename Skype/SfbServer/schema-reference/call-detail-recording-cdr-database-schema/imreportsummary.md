---
title: IMReportSummary-Tabelle in Skype for Business Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: Die IMReportSummaryTable bietet einen Gesamtbericht über die in einer Organisation gehaltenen Chatsitzungen. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
---

# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>IMReportSummary-Tabelle in Skype for Business Server 2015
 
Die IMReportSummaryTable bietet einen Gesamtbericht über die in einer Organisation gehaltenen Chatsitzungen. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**StartTime** <br/> |Datum/Uhrzeit  <br/> |Primary  <br/> |Datum und Uhrzeit, an dem bzw. zu der die Chatsitzung begann.  <br/> |
|**Zeitfenster** <br/> |char(1)  <br/> |Primary  <br/> ||
|**PoolFQDN** <br/> |nvarchar(257)  <br/> |Primary  <br/> |Vollqualifizierter Domänenname des Pools, der die Sitzung hostet.  <br/> |
|**Authtype** <br/> |int  <br/> |Primary  <br/> |Priorität (z. B. dringend oder nicht dringend) des Anrufs. Prioritätsinformationen werden in der [CallPriorities-Tabelle in Skype for Business Server 2015](callpriorities.md) gespeichert.  <br/> |
|**SessionCount** <br/> |Bigint  <br/> |||
|**MsgCount** <br/> |Bigint  <br/> ||Die Gesamtzahl der Chatnachrichten, die während der Sitzung ausgetauscht wurden.  <br/> |
   

