---
title: ErrorCategory-Tabelle in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'Die ErrorCategory-Tabelle enthält den Anzeigenamen für jede Skype for Business Server Diagnoseklassifizierung 2015. Standardmäßig verwendet Skype for Business Server 2015 die folgenden Klassifizierungen:'
ms.openlocfilehash: 65894c843010af9a2c54d839f701877c7d2bea53
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854149"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>ErrorCategory-Tabelle in Skype for Business Server 2015
 
Die ErrorCategory-Tabelle enthält den Anzeigenamen für jede Skype for Business Server Diagnoseklassifizierung 2015. Standardmäßig verwendet Skype for Business Server 2015 die folgenden Klassifizierungen:
  
- 0 – Erfolg
    
- 1 – Erwarteter Fehler
    
- 2 – Unerwarteter Fehler
    
Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Categoryid** <br/> |Tinyint  <br/> |Primary  <br/> |Eindeutige ID für die Klassifizierung.  <br/> |
|**Name** <br/> |nvarchar(256)  <br/> || Wert und Anzeigename, der der Klassifizierung zugewiesen sind. Gültige Werte sind: <br/>  0 – Erfolg <br/>  1 – Erwarteter Fehler <br/>  2 – Unerwarteter Fehler <br/> |
   

