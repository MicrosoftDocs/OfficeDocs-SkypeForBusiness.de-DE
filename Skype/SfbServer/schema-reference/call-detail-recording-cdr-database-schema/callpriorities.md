---
title: CallPriorities-Tabelle in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: Die CallPriorities-Tabelle ist eine statische Tabelle, in der die Liste möglicher Anrufprioritäten wie "Notfall", "Dringend" oder "Normal" gespeichert wird.
ms.openlocfilehash: ed31d55852f0b685429bd7fbf70cff1bf81d63ae
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845138"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>CallPriorities-Tabelle in Skype for Business Server 2015
 
Die CallPriorities-Tabelle ist eine statische Tabelle, in der die Liste möglicher Anrufprioritäten wie "Notfall", "Dringend" oder "Normal" gespeichert wird.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |Tinyint  <br/> |Primary  <br/> ||
|**Priorität** <br/> |nvarchar(256)  <br/> || Gültige Werte: <br/>  0 – Unbekannt <br/>  1 – Nicht dringend <br/>  2 – Normal <br/>  3 – Dringend <br/>  4 – Notfall <br/> |
   

