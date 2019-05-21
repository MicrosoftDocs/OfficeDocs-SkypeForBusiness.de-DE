---
title: Tabelle "Geräte" in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Die Tabelle Devices ist eine unterstützende Tabelle. Jeder Datensatz speichert Informationen zu einem Gerät (Tischtelefon).
ms.openlocfilehash: 145637b6385677007efa47cd21b3f0ea7d7f88f2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296378"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Tabelle "Geräte" in Skype for Business Server 2015
 
Die Tabelle Devices ist eine unterstützende Tabelle. Jeder Datensatz speichert Informationen zu einem Gerät (Tischtelefon).
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**DeviceID** <br/> |int  <br/> |Primary  <br/> |Eindeutige Nummer, die diese Hardware Version kennzeichnet.  <br/> |
|**ManufacturerId** <br/> |int  <br/> |Fremd  <br/> |Hersteller des Geräts. Weitere Informationen finden Sie [in der Tabelle "Hersteller" in Skype for Business Server 2015](manufacturers.md) . <br/> |
|**HardwareVersionId** <br/> |int  <br/> |Fremd  <br/> |Hardware Version dieses Geräts. Weitere Informationen finden Sie [in der Tabelle HardwareVersions in Skype for Business Server 2015](hardwareversions.md) . <br/> |
|**MacAddress** <br/> |bigint  <br/> ||Mac-Adresse  <br/> |
   

