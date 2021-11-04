---
title: CallPriorities-Tabelle in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.openlocfilehash: 21924d712ff4ee658f757911ce168fe8b662357d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743211"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>CallPriorities-Tabelle in Skype for Business Server 2015
 
Die CallPriorities-Tabelle ist eine statische Tabelle, in der die Liste möglicher Anrufprioritäten wie "Notfall", "Dringend" oder "Normal" gespeichert wird.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |Tinyint  <br/> |Primary  <br/> ||
|**Priorität** <br/> |nvarchar(256)  <br/> || Gültige Werte: <br/>  0 – Unbekannt <br/>  1 – Nicht dringend <br/>  2 – Normal <br/>  3 – Dringend <br/>  4 – Notfall <br/> |
   

