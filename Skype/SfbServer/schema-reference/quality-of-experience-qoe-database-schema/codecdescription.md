---
title: CodecDescription-Tabelle
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
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: Die CodecDescription-Tabelle ordnet eindeutige Codec-IDs dem entsprechenden Codec zu. Codecs werden verwendet, um digitale Signale für Übertragung und Übertragung zu codieren und diese Signale dann für die Wiedergabe zu decodieren. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 9facaa9ddf29024a731f9e199b5cf749d91bc6671c320ded510d693755640f38
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309174"
---
# <a name="codecdescription-table"></a>CodecDescription-Tabelle
 
Die CodecDescription-Tabelle ordnet eindeutige Codec-IDs dem entsprechenden Codec zu. Codecs werden verwendet, um digitale Signale für Übertragung und Übertragung zu codieren und diese Signale dann für die Wiedergabe zu decodieren. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |Smallint  <br/> |Primary  <br/> |Eindeutige ID, die dem Codec zugewiesen ist.  <br/> |
|**CodecDescription** <br/> |varchar(256)  <br/> |Eigen  <br/> |Eindeutige Beschreibung des Codecs, der dem  CodecDescriptionKey entspricht.  <br/> |
   

