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
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: Die CodecDescription-Tabelle ordnet eindeutige Codec-IDs dem zugehörigen Codec zu. Codecs werden verwendet, um digitale Signale für die Übertragung und Übertragung zu kodieren und diese Signale zur Wiedergabe zu decodieren. Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 678b458757c54385b608d89efd6b2c621c6cd42f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295041"
---
# <a name="codecdescription-table"></a>CodecDescription-Tabelle
 
Die CodecDescription-Tabelle ordnet eindeutige Codec-IDs dem zugehörigen Codec zu. Codecs werden verwendet, um digitale Signale für die Übertragung und Übertragung zu kodieren und diese Signale zur Wiedergabe zu decodieren. Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |Primary  <br/> |Eindeutiger Bezeichner, der dem Codec zugewiesen ist.  <br/> |
|**CodecDescription** <br/> |varchar (256)  <br/> |Eindeutigen  <br/> |Eindeutige Beschreibung des Codecs, der dem CodecDescriptionKey entspricht.  <br/> |
   

