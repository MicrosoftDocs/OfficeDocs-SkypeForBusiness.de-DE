---
title: CodecDescription-Tabelle
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: Die CodecDescription-Tabelle ordnet eindeutige Codec-IDs dem entsprechenden Codec zu. Codecs werden verwendet, um digitale Signale für Übertragung und Übertragung zu codieren und diese Signale dann für die Wiedergabe zu decodieren. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 0f5601847458f7ce59e0cd691b573ec77605b667
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763243"
---
# <a name="codecdescription-table"></a>CodecDescription-Tabelle
 
Die CodecDescription-Tabelle ordnet eindeutige Codec-IDs dem entsprechenden Codec zu. Codecs werden verwendet, um digitale Signale für Übertragung und Übertragung zu codieren und diese Signale dann für die Wiedergabe zu decodieren. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |Smallint  <br/> |Primary  <br/> |Eindeutige ID, die dem Codec zugewiesen ist.  <br/> |
|**CodecDescription** <br/> |varchar(256)  <br/> |Eigen  <br/> |Eindeutige Beschreibung des Codecs, der dem  CodecDescriptionKey entspricht.  <br/> |
   

