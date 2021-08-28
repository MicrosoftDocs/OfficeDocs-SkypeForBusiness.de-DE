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
ms.localizationpriority: medium
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: Die CodecDescription-Tabelle ordnet eindeutige Codec-IDs dem entsprechenden Codec zu. Codecs werden verwendet, um digitale Signale für Übertragung und Übertragung zu codieren und diese Signale dann für die Wiedergabe zu decodieren. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: cfd0953322f9cc34d90947c0d9be7ecb13cd3c33
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58609172"
---
# <a name="codecdescription-table"></a>CodecDescription-Tabelle
 
Die CodecDescription-Tabelle ordnet eindeutige Codec-IDs dem entsprechenden Codec zu. Codecs werden verwendet, um digitale Signale für Übertragung und Übertragung zu codieren und diese Signale dann für die Wiedergabe zu decodieren. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |Smallint  <br/> |Primary  <br/> |Eindeutige ID, die dem Codec zugewiesen ist.  <br/> |
|**CodecDescription** <br/> |varchar(256)  <br/> |Eigen  <br/> |Eindeutige Beschreibung des Codecs, der dem  CodecDescriptionKey entspricht.  <br/> |
   

