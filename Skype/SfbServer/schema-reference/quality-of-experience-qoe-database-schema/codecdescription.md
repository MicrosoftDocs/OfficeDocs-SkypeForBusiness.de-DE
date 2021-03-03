---
title: Tabelle "CodecDescription"
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
description: Die Tabelle "CodecDescription" ordnet eindeutige Codecbezeichner dem entsprechenden Codec zu. Codecs werden verwendet, um digitale Signale für die Übertragung und Übertragung zu codieren und diese Signale dann für die Wiedergabe zu decodieren. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 95ba2218ff20aa6c67de6f60d6966916b6648a58
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831345"
---
# <a name="codecdescription-table"></a>Tabelle "CodecDescription"
 
Die Tabelle "CodecDescription" ordnet eindeutige Codecbezeichner dem entsprechenden Codec zu. Codecs werden verwendet, um digitale Signale für die Übertragung und Übertragung zu codieren und diese Signale dann für die Wiedergabe zu decodieren. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |Primary  <br/> |Eindeutige ID, die dem Codec zugewiesen ist.  <br/> |
|**CodecDescription** <br/> |varchar(256)  <br/> |Eigen  <br/> |Eindeutige Beschreibung des Codecs, der dem  CodecDescriptionKey entspricht.  <br/> |
   

