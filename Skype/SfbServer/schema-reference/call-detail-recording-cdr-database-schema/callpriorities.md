---
title: CallPriorities-Tabelle in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: Bei der CallPriorities-Tabelle handelt es sich um eine statische Tabelle, in der die Liste möglicher Anruf Prioritäten wie "Notfall", "dringend" oder "Normal" gespeichert ist.
ms.openlocfilehash: 57ab4c2b190b14d26a7f8be1791eb70473f1eb3c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815443"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>CallPriorities-Tabelle in Skype for Business Server 2015
 
Bei der CallPriorities-Tabelle handelt es sich um eine statische Tabelle, in der die Liste möglicher Anruf Prioritäten wie "Notfall", "dringend" oder "Normal" gespeichert ist.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Prioritäts-Nr** <br/> |tinyint  <br/> |Primary  <br/> ||
|**Priorität** <br/> |nvarchar(256)  <br/> || Zulässige Werte: <br/>  0 – unbekannt <br/>  1 – nicht dringend <br/>  2 – Normal <br/>  3 – dringend <br/>  4 – Notfall <br/> |
   

