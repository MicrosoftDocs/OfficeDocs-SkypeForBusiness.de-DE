---
title: MediaList-Tabelle
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
ms.localizationpriority: medium
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: Die MediaList-Tabelle ist eine statische Tabelle, in der die Liste der verschiedenen Medientypen gespeichert ist.
ms.openlocfilehash: a72a409e9cc50fb5c8a7b340674276299e0ac4e9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596419"
---
# <a name="medialist-table"></a>MediaList-Tabelle
 
Die MediaList-Tabelle ist eine statische Tabelle, in der die Liste der verschiedenen Medientypen gespeichert ist.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Mediaid** <br/> |Tinyint  <br/> |Primary  <br/> |Werte: 1-7  <br/> |
|**Medien** <br/> |nvarchar(256)  <br/> || Statische Zuordnung von MediaID- und Medienwerten: <br/>  1 -- Sofortnachrichten <br/>  2 – Dateiübertragung <br/>  3 – Remoteunterstützung <br/>  4 – Anwendungsfreigabe <br/>  5 -- Audio <br/>  6 -- Video <br/>  7 – App-Einladung <br/> |
   
Wenn Sie versuchen, den Modalitätstyp für die Werte in LcsCDR.SessionDetailsView.MediaTypes zu ermitteln, müssen Sie den folgenden Join-Codeausschnitt verwenden: 
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
