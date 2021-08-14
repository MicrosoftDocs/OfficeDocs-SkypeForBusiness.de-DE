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
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: Die MediaList-Tabelle ist eine statische Tabelle, in der die Liste der verschiedenen Medientypen gespeichert ist.
ms.openlocfilehash: 9242f20b3c2192fb1f5cd48c84784a3e8d283f6e91587aee408a9286d291add7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326271"
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
