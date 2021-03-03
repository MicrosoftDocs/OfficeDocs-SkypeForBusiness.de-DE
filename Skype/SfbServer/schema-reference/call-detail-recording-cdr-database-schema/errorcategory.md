---
title: Tabelle "ErrorCategory" in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'Die Tabelle "ErrorCategory" enthält den Anzeigenamen für jede Skype for Business Server 2015-Diagnoseklassifikation. Standardmäßig verwendet Skype for Business Server 2015 die folgenden Klassifizierungen:'
ms.openlocfilehash: ca3719f6d284cf715be1a87b1c7a5dc04ae84b04
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813145"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>Tabelle "ErrorCategory" in Skype for Business Server 2015
 
Die Tabelle "ErrorCategory" enthält den Anzeigenamen für jede Skype for Business Server 2015-Diagnoseklassifikation. Standardmäßig verwendet Skype for Business Server 2015 die folgenden Klassifizierungen:
  
- 0 – Erfolg
    
- 1 – Erwarteter Fehler
    
- 2 – Unerwarteter Fehler
    
Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**CategoryId** <br/> |tinyint  <br/> |Primary  <br/> |Eindeutige ID für die Klassifizierung.  <br/> |
|**Name** <br/> |nvarchar(256)  <br/> || Wert und Anzeigename, der der Klassifizierung zugewiesen ist. Gültige Werte sind: <br/>  0 – Erfolg <br/>  1 – Erwarteter Fehler <br/>  2 – Unerwarteter Fehler <br/> |
   

