---
title: Tabelle "CallType" in Skype for Business Server 2015
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
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: Die CallType-Tabelle ist eine statische Tabelle, in der die Liste der möglichen Anruftypen gespeichert ist.
ms.openlocfilehash: 89f29a2c826f4aef12cc0332e40df0fb421c3932
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813365"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>Tabelle "CallType" in Skype for Business Server 2015
 
Die CallType-Tabelle ist eine statische Tabelle, in der die Liste der möglichen Anruftypen gespeichert ist.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Primary  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || Zulässige Werte: <br/>  0 – Unbekannt <br/>  1 – Sofortnachrichten <br/>  2 – Anwendungsfreigabe <br/>  3 – Audio <br/>  4 – Audio und Video <br/>  5 – Dateiübertragung <br/> |
   

