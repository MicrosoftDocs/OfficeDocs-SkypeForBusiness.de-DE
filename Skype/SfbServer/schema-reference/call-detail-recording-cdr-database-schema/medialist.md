---
title: Tabelle "MediaList"
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: Die MediaList-Tabelle ist eine statische Tabelle, in der die Liste der verschiedenen Medientypen gespeichert ist.
ms.openlocfilehash: 6f593876a1b42163b6f2e75dbe44c1eb26b2ff16
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813135"
---
# <a name="medialist-table"></a>Tabelle "MediaList"
 
Die MediaList-Tabelle ist eine statische Tabelle, in der die Liste der verschiedenen Medientypen gespeichert ist.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**MediaId** <br/> |tinyint  <br/> |Primary  <br/> |Werte: 1-7  <br/> |
|**Medien** <br/> |nvarchar(256)  <br/> || Statische Zuordnung von MediaID- und Medienwerten: <br/>  1 -- Sofortnachrichten <br/>  2 – Dateiübertragung <br/>  3 – Remoteunterstützung <br/>  4 – Anwendungsfreigabe <br/>  5 -- Audio <br/>  6 -- Video <br/>  7 – App-Einladung <br/> |
   
Wenn Sie versuchen, den Modalitätstyp für die Werte in "LcsCDR.SessionDetailsView.MediaTypes" zu bestimmen, müssen Sie den folgenden #A0 verwenden: 
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
