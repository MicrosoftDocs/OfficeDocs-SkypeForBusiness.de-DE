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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Die Tabelle Devices ist eine unterstützende Tabelle. Jeder Datensatz speichert Informationen zu einem Gerät (Tischtelefon).
ms.openlocfilehash: e53a8947d106d6a92d7cf5cb881f20022e1bac69
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815283"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Tabelle "Geräte" in Skype for Business Server 2015
 
Die Tabelle Devices ist eine unterstützende Tabelle. Jeder Datensatz speichert Informationen zu einem Gerät (Tischtelefon).
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**DeviceID** <br/> |int  <br/> |Primary  <br/> |Eindeutige Nummer, die diese Hardware Version kennzeichnet.  <br/> |
|**ManufacturerId** <br/> |int  <br/> |Fremd  <br/> |Hersteller des Geräts. Weitere Informationen finden Sie [in der Tabelle "Hersteller" in Skype for Business Server 2015](manufacturers.md) . <br/> |
|**HardwareVersionId** <br/> |int  <br/> |Fremd  <br/> |Hardware Version dieses Geräts. Weitere Informationen finden Sie [in der Tabelle HardwareVersions in Skype for Business Server 2015](hardwareversions.md) . <br/> |
|**MacAddress** <br/> |bigint  <br/> ||Mac-Adresse  <br/> |
   

