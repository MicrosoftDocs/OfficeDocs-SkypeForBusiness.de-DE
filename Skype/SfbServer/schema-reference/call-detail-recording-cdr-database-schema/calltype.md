---
title: CallType-Tabelle in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.openlocfilehash: 05bfcf5b13735a460f8122fc6b1ce5eeddf94b97
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743191"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>CallType-Tabelle in Skype for Business Server 2015
 
Die CallType-Tabelle ist eine statische Tabelle, in der die Liste der möglichen Anruftypen gespeichert ist.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Primary  <br/> ||
|**CallType** <br/> |Nvarchar  <br/> || Zulässige Werte: <br/>  0 – Unbekannt <br/>  1 – Chat <br/>  2 – Anwendungsfreigabe <br/>  3 – Audio <br/>  4 – Audio und Video <br/>  5 – Dateiübertragung <br/> |
   

