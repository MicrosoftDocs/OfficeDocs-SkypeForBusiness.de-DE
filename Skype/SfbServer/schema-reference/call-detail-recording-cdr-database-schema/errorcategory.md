---
title: ErrorCategory-Tabelle in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'Die ErrorCategory-Tabelle enthält den Anzeigenamen für jede Diagnose Klassifizierung für Skype for Business Server 2015. Standardmäßig verwendet Skype for Business Server 2015 die folgenden Klassifizierungen:'
ms.openlocfilehash: f3ad3f86a382b900d53c5e86140a46d7f32ca1c1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815253"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>ErrorCategory-Tabelle in Skype for Business Server 2015
 
Die ErrorCategory-Tabelle enthält den Anzeigenamen für jede Diagnose Klassifizierung für Skype for Business Server 2015. Standardmäßig verwendet Skype for Business Server 2015 die folgenden Klassifizierungen:
  
- 0--Erfolg
    
- 1 – Erwarteter Fehler
    
- 2 – unerwarteter Fehler
    
Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**CategoryID** <br/> |tinyint  <br/> |Primary  <br/> |Eindeutiger Bezeichner für die Klassifizierung.  <br/> |
|**Name** <br/> |nvarchar(256)  <br/> || Wert und Anzeigename, der der Klassifizierung zugewiesen ist. Gültige Werte sind: <br/>  0--Erfolg <br/>  1 – Erwarteter Fehler <br/>  2 – unerwarteter Fehler <br/> |
   

