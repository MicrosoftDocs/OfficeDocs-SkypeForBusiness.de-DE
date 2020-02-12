---
title: MediaList-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: e7d739b27bf45b5f5a21183c30bd5b07108b4a9d
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888514"
---
# <a name="medialist-table"></a>MediaList-Tabelle
 
Die MediaList-Tabelle ist eine statische Tabelle, in der die Liste der verschiedenen Medientypen gespeichert ist.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**MediaId** <br/> |tinyint  <br/> |Primary  <br/> |Werte: 1-7  <br/> |
|**Media** <br/> |nvarchar(256)  <br/> || Statische Zuordnung von MediaID- und Media-Werten <br/>  1 – Sofortnachrichten <br/>  2-Dateiübertragung <br/>  3 – Remote Unterstützung <br/>  4 – Anwendungsfreigabe <br/>  5 – Audio <br/>  6 – Video <br/>  7-App-Einladung <br/> |
   
Wenn Sie versuchen, den Modalitätstyp für die Werte in LcsCDR.SessionDetailsView.MediaTypes zu bestimmen, müssen Sie das folgende Join-Snippet verwenden:  
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
