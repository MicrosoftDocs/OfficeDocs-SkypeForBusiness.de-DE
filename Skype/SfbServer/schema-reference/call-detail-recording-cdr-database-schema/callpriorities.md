---
title: CallPriorities-Tabelle in Skype for Business Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: 'Die CallPriorities-Tabelle ist eine statische Tabelle, in der die Liste möglicher Anrufprioritäten wie "Notfall", "Dringend" oder "Normal" gespeichert wird.'
---

# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>CallPriorities-Tabelle in Skype for Business Server 2015
 
Die CallPriorities-Tabelle ist eine statische Tabelle, in der die Liste möglicher Anrufprioritäten wie "Notfall", "Dringend" oder "Normal" gespeichert wird.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |Tinyint  <br/> |Primary  <br/> ||
|**Priorität** <br/> |nvarchar(256)  <br/> || Gültige Werte: <br/>  0 – Unbekannt <br/>  1 – Nicht dringend <br/>  2 – Normal <br/>  3 – Dringend <br/>  4 – Notfall <br/> |
   

