---
title: Tabelle "CallType" in Skype for Business Server 2015
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
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: Die CallType-Tabelle ist eine statische Tabelle, in der die Liste möglicher Anruftypen gespeichert ist.
ms.openlocfilehash: 294af58755e980200d75c899d6110322e2ff774d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815433"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>Tabelle "CallType" in Skype for Business Server 2015
 
Die CallType-Tabelle ist eine statische Tabelle, in der die Liste möglicher Anruftypen gespeichert ist.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Primary  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || Zulässige Werte: <br/>  0-unbekannt <br/>  1 – Sofortnachrichten <br/>  2 – Anwendungsfreigabe <br/>  3-Audio <br/>  4 – Audio und Video <br/>  5-Dateiübertragung <br/> |
   

