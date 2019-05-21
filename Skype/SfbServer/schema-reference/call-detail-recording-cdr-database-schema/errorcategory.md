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
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'Die ErrorCategory-Tabelle enthält den Anzeigenamen für jede Diagnose Klassifizierung für Skype for Business Server 2015. Standardmäßig verwendet Skype for Business Server 2015 die folgenden Klassifizierungen:'
ms.openlocfilehash: bafeb75ee9e6ae0f96b08e26909828f1b36f7e7b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296287"
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
   

