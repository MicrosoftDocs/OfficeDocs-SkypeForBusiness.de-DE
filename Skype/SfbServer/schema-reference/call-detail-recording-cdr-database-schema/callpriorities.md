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
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: Bei der CallPriorities-Tabelle handelt es sich um eine statische Tabelle, in der die Liste möglicher Anruf Prioritäten wie "Notfall", "dringend" oder "Normal" gespeichert ist.
ms.openlocfilehash: 6d324ce11b2e149378b6275441cb4a2467a641db
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296567"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>CallPriorities-Tabelle in Skype for Business Server 2015
 
Bei der CallPriorities-Tabelle handelt es sich um eine statische Tabelle, in der die Liste möglicher Anruf Prioritäten wie "Notfall", "dringend" oder "Normal" gespeichert ist.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Prioritäts-Nr** <br/> |tinyint  <br/> |Primary  <br/> ||
|**Priorität** <br/> |nvarchar(256)  <br/> || Zulässige Werte: <br/>  0 – unbekannt <br/>  1 – nicht dringend <br/>  2 – Normal <br/>  3 – dringend <br/>  4 – Notfall <br/> |
   

