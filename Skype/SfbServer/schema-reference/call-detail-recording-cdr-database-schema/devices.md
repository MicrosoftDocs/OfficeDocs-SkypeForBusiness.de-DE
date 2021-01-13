---
title: Gerätetabelle in Skype for Business Server 2015
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
ms.openlocfilehash: da0d6ea8143fb8c81225e885fba1f05a90e2fda5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831815"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Gerätetabelle in Skype for Business Server 2015
 
Bei der Devices-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz speichert Informationen über ein Gerät (Telefonapparat).
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diese Hardwareversion identifiziert.  <br/> |
|**ManufacturerId** <br/> |int  <br/> |Fremd  <br/> |Hersteller dieses Geräts. Weitere Informationen finden Sie in der [Tabelle "Hersteller" in Skype for Business Server 2015.](manufacturers.md) <br/> |
|**HardwareVersionId** <br/> |int  <br/> |Fremd  <br/> |Hardwareversion dieses Geräts. Weitere Informationen finden Sie in der [Tabelle "HardwareVersions" in Skype for Business Server 2015.](hardwareversions.md) <br/> |
|**MacAddress** <br/> |bigint  <br/> ||MAC-Adresse  <br/> |
   

