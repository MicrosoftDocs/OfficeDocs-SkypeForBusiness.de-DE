---
title: CallPriorities-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities-Tabelle ist eine statische Tabelle, die die Liste der möglichen Anruf Prioritäten, wie beispielsweise "emergency", "sofortigen" oder "normal" gespeichert.
ms.openlocfilehash: aac21073e98d7c1ef8d137a736445b62e4fb9878
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901529"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>CallPriorities-Tabelle in Skype für Business Server 2015
 
CallPriorities-Tabelle ist eine statische Tabelle, die die Liste der möglichen Anruf Prioritäten, wie beispielsweise "emergency", "sofortigen" oder "normal" gespeichert.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**Priorität** <br/> |nvarchar(256)  <br/> || Zulässige Werte: <br/>  0 – unbekannt <br/>  1 – nicht dringend <br/>  2 - Normal <br/>  3 - dringende <br/>  4 - emergency <br/> |
   

