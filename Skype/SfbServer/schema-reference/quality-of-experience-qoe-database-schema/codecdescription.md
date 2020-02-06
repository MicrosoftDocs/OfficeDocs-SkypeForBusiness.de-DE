---
title: CodecDescription-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: Die CodecDescription-Tabelle ordnet eindeutige Codec-IDs dem zugehörigen Codec zu. Codecs werden verwendet, um digitale Signale für die Übertragung und Übertragung zu kodieren und diese Signale zur Wiedergabe zu decodieren. Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 53410b1bdf4875bd66a80c107dc56c5316fc30a3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810363"
---
# <a name="codecdescription-table"></a>CodecDescription-Tabelle
 
Die CodecDescription-Tabelle ordnet eindeutige Codec-IDs dem zugehörigen Codec zu. Codecs werden verwendet, um digitale Signale für die Übertragung und Übertragung zu kodieren und diese Signale zur Wiedergabe zu decodieren. Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |Primary  <br/> |Eindeutiger Bezeichner, der dem Codec zugewiesen ist.  <br/> |
|**CodecDescription** <br/> |varchar (256)  <br/> |Eindeutigen  <br/> |Eindeutige Beschreibung des Codecs, der dem CodecDescriptionKey entspricht.  <br/> |
   

