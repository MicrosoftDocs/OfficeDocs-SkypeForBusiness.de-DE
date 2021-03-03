---
title: Tabelle "CallPriorities" in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: Die Tabelle "CallPriorities" ist eine statische Tabelle, in der die Liste möglicher Anrufprioritäten wie "Notfall", "Dringend" oder "Normal" enthalten ist.
ms.openlocfilehash: 54fdd70dcd939cfeb227862d6152577c4c91d3b3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813435"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>Tabelle "CallPriorities" in Skype for Business Server 2015
 
Die Tabelle "CallPriorities" ist eine statische Tabelle, in der die Liste möglicher Anrufprioritäten wie "Notfall", "Dringend" oder "Normal" enthalten ist.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**Priority** <br/> |nvarchar(256)  <br/> || Gültige Werte: <br/>  0 – Unbekannt <br/>  1 – Nicht dringend <br/>  2 – Normal <br/>  3 – Dringend <br/>  4 – Notfall <br/> |
   

