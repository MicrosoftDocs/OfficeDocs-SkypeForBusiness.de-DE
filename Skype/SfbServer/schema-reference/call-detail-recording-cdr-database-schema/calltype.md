---
title: CallType-Tabelle in Skype für Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: Die CallType-Tabelle ist eine statische Tabelle, die die Liste der möglichen Anruftypen gespeichert.
ms.openlocfilehash: e2353176a69db9eada137525561541d26caa7a8e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>CallType-Tabelle in Skype für Business Server 2015
 
Die CallType-Tabelle ist eine statische Tabelle, die die Liste der möglichen Anruftypen gespeichert.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Primary  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || Zulässige Werte: <br/>  0 – unbekannt <br/>  1 – Sofortnachrichten <br/>  2 – Anwendungsfreigabe <br/>  3 – audio <br/>  4 – Audio und Video <br/>  5 – Dateiübertragung <br/> |
   

