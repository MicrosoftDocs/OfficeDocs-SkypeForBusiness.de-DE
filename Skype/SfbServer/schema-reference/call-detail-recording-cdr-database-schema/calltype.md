---
title: CallType-Tabelle in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: Die CallType-Tabelle ist eine statische Tabelle, in der die Liste der möglichen Anruftypen gespeichert ist.
ms.openlocfilehash: 7f00e924041c5b26f7045cf8f97ae82daa141611
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845088"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>CallType-Tabelle in Skype for Business Server 2015
 
Die CallType-Tabelle ist eine statische Tabelle, in der die Liste der möglichen Anruftypen gespeichert ist.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Primary  <br/> ||
|**CallType** <br/> |Nvarchar  <br/> || Zulässige Werte: <br/>  0 – Unbekannt <br/>  1 – Chat <br/>  2 – Anwendungsfreigabe <br/>  3 – Audio <br/>  4 – Audio und Video <br/>  5 – Dateiübertragung <br/> |
   

