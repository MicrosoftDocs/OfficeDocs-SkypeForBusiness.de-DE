---
title: Tabelle "Geräte" in Skype for Business Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: 'Bei der Devices-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz speichert Informationen über ein Gerät (Telefonapparat).'
---

# <a name="devices-table-in-skype-for-business-server-2015"></a>Tabelle "Geräte" in Skype for Business Server 2015
 
Bei der Devices-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz speichert Informationen über ein Gerät (Telefonapparat).
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Deviceid** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diese Hardwareversion identifiziert.  <br/> |
|**ManufacturerId** <br/> |int  <br/> |Ausländisch  <br/> |Hersteller dieses Geräts. Weitere Informationen finden Sie [in der Tabelle "Hersteller" in Skype for Business Server 2015](manufacturers.md). <br/> |
|**HardwareVersionId** <br/> |int  <br/> |Ausländisch  <br/> |Hardwareversion dieses Geräts. Weitere Informationen finden Sie [in der Tabelle "HardwareVersions" in Skype for Business Server 2015](hardwareversions.md). <br/> |
|**MacAddress** <br/> |Bigint  <br/> ||MAC-Adresse  <br/> |
   

