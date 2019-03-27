---
title: ErrorCategory-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'ErrorCategory-Tabelle enthält den Anzeigenamen für jedes Skype für Business Server 2015-diagnoseklassifizierung. Skype für Business Server 2015 verwendet standardmäßig die folgenden Klassifikationen:'
ms.openlocfilehash: 70322d30b516d003fcac015a4eda7382a13cd2be
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886959"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>ErrorCategory-Tabelle in Skype für Business Server 2015
 
ErrorCategory-Tabelle enthält den Anzeigenamen für jedes Skype für Business Server 2015-diagnoseklassifizierung. Skype für Business Server 2015 verwendet standardmäßig die folgenden Klassifikationen:
  
- 0 – Erfolg
    
- 1--Erwarteter Fehler
    
- 2 – unerwarteter Fehler
    
Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**CategoryId** <br/> |tinyint  <br/> |Primary  <br/> |Eindeutiger Bezeichner für die Klassifikation.  <br/> |
|**Name** <br/> |nvarchar(256)  <br/> || Wert und dem Anzeigenamen der Klassifikation zugewiesen. Gültige Werte sind: <br/>  0 – Erfolg <br/>  1--Erwarteter Fehler <br/>  2 – unerwarteter Fehler <br/> |
   

