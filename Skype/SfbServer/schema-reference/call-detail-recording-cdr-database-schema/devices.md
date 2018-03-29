---
title: Devices-Tabelle in Skype für Business Server 2015
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
ms.openlocfilehash: c7a5a5933d4fe2e465faf039a8ac2ed2a65fa563
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Devices-Tabelle in Skype für Business Server 2015
 
Die Geräte-Tabelle ist eine Tabelle. Jeder Datensatz speichert Informationen zu einem Gerät (Telefonapparat).
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Geräte-ID** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diese Hardwareversion identifiziert.  <br/> |
|**ManufacturerId** <br/> |int  <br/> |Fremdschlüssel  <br/> |Hersteller des dieses Gerät. [Manufacturers-Tabelle in Skype für Business Server 2015](manufacturers.md) Weitere Informationen finden Sie. <br/> |
|**HardwareVersionId** <br/> |int  <br/> |Fremdschlüssel  <br/> |Hardwareversion dieses Geräts. [HardwareVersions-Tabelle in Skype für Business Server 2015](hardwareversions.md) Weitere Informationen finden Sie. <br/> |
|**MacAddress** <br/> |bigint  <br/> ||MAC-Adresse  <br/> |
   

