---
title: PayloadDescription-Tabelle
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: Bei der PayloadDescription-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für einen Codec, der in einer Audio- oder Videositzung verwendet wird.
ms.openlocfilehash: aa2d2048b61523ed0fab9b8b8796f7b3a29a83dbd1ebb5b5ec800e00520a387e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312983"
---
# <a name="payloaddescription-table"></a>PayloadDescription-Tabelle
 
Bei der PayloadDescription-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für einen Codec, der in einer Audio- oder Videositzung verwendet wird.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**PayloadDescriptionKey** <br/> |Ganzzahl  <br/> |Primary  <br/> |Eindeutige Zahl, die den Codec identifiziert.  <br/> |
|**PayloadDescription** <br/> |nvarchar(256)  <br/> |Eigen  <br/> |Name des Codecs.  <br/> |
   

