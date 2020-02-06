---
title: Tabelle "Tabelle" in Skype for Business Server 2015
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
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Die Tabelle "MCU" ist eine unterstützende Tabelle. In jedem Datensatz werden Informationen zu einem Konferenzdienst gespeichert. Dazu gehören der Chat-Konferenzdienst und der Telefonie-Konferenzdienst (der als Prozesse auf Front-End-Servern ausgeführt wird) sowie der Webkonferenzdienst und ein/V-Konferenzdienst.
ms.openlocfilehash: 1e5141ee2a103e540d3ac50e99de0036f31262d7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815063"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Tabelle "Tabelle" in Skype for Business Server 2015
 
Die Tabelle "MCU" ist eine unterstützende Tabelle. In jedem Datensatz werden Informationen zu einem Konferenzdienst gespeichert. Dazu gehören der Chat-Konferenzdienst und der Telefonie-Konferenzdienst (der als Prozesse auf Front-End-Servern ausgeführt wird) sowie der Webkonferenzdienst und ein/V-Konferenzdienst. 
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Primary  <br/> |Eindeutige Nummer, die diesen Konferenzserver identifiziert.  <br/> |
|**McuUri** <br/> |nvarchar (450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | Fremd <br/> |Konferenz Servertyp wie conf: Chat (für IMS) oder conf: Audio-Video. Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) . <br/> |
   

