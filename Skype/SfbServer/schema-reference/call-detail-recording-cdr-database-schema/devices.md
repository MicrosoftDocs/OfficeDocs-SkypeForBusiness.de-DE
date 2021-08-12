---
title: Tabelle "Geräte" in Skype for Business Server 2015
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
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Bei der Devices-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz speichert Informationen über ein Gerät (Telefonapparat).
ms.openlocfilehash: eac31407de3f5a648ebe5f3819b2d7f3556e9bd6c2be930450e8e27700ead178
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295372"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Tabelle "Geräte" in Skype for Business Server 2015
 
Bei der Devices-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz speichert Informationen über ein Gerät (Telefonapparat).
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Deviceid** <br/> |Ganzzahl  <br/> |Primary  <br/> |Eindeutige Zahl, die diese Hardwareversion identifiziert.  <br/> |
|**ManufacturerId** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |Hersteller dieses Geräts. Weitere Informationen finden Sie in der [Tabelle "Hersteller" in Skype for Business Server 2015.](manufacturers.md) <br/> |
|**HardwareVersionId** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |Hardwareversion dieses Geräts. Weitere Informationen finden Sie in der [HardwareVersions-Tabelle in Skype for Business Server 2015.](hardwareversions.md) <br/> |
|**MacAddress** <br/> |Bigint  <br/> ||MAC-Adresse  <br/> |
   

