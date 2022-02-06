---
title: CallType-Tabelle in Skype for Business Server 2015
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
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: 'Die CallType-Tabelle ist eine statische Tabelle, in der die Liste der möglichen Anruftypen gespeichert ist.'
---

# <a name="calltype-table-in-skype-for-business-server-2015"></a>CallType-Tabelle in Skype for Business Server 2015
 
Die CallType-Tabelle ist eine statische Tabelle, in der die Liste der möglichen Anruftypen gespeichert ist.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Primary  <br/> ||
|**CallType** <br/> |Nvarchar  <br/> || Zulässige Werte: <br/>  0 – Unbekannt <br/>  1 – Chat <br/>  2 – Anwendungsfreigabe <br/>  3 – Audio <br/>  4 – Audio und Video <br/>  5 – Dateiübertragung <br/> |
   

