---
title: Devices-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Die Geräte-Tabelle ist eine Tabelle. Jeder Datensatz speichert Informationen zu einem Gerät (Telefonapparat).
ms.openlocfilehash: f770f19fb94bf25bdb4c13e74dc41e05f6674788
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881702"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Devices-Tabelle in Skype für Business Server 2015
 
Die Geräte-Tabelle ist eine Tabelle. Jeder Datensatz speichert Informationen zu einem Gerät (Telefonapparat).
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Geräte-ID** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diese Hardwareversion identifiziert.  <br/> |
|**ManufacturerId** <br/> |int  <br/> |Ausländisch  <br/> |Hersteller des dieses Gerät. [Manufacturers-Tabelle in Skype für Business Server 2015](manufacturers.md) Weitere Informationen finden Sie. <br/> |
|**HardwareVersionId** <br/> |int  <br/> |Ausländisch  <br/> |Hardwareversion dieses Geräts. [HardwareVersions-Tabelle in Skype für Business Server 2015](hardwareversions.md) Weitere Informationen finden Sie. <br/> |
|**MacAddress** <br/> |bigint  <br/> ||MAC-Adresse  <br/> |
   

