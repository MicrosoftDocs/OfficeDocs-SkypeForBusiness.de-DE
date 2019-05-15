---
title: Device-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Die Gerät-Tabelle ist eine unterstützende Tabelle, die Informationen zu den verschiedenen Capture gespeichert, oder darstellungsgeräte. Jeder Datensatz in der Tabelle steht für ein Gerät.
ms.openlocfilehash: 0b3c27708cd8e9d1b02914e6f2cba414e353609c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920026"
---
# <a name="device-table"></a>Device-Tabelle
 
Die Gerät-Tabelle ist eine unterstützende Tabelle, die Informationen zu den verschiedenen Capture gespeichert, oder darstellungsgeräte. Jeder Datensatz in der Tabelle steht für ein Gerät.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die dieses Gerät identifiziert.  <br/> |
|**DeviceName** <br/> |nvarchar(256)  <br/> |DeviceName + DeviceType ist unique  <br/> |Name des Aufnahmegeräts.  <br/> |
|**DeviceType** <br/> |bit  <br/> |DeviceName + DeviceType ist unique  <br/> |Gerätetyp. 1 ist ein Aufnahmegerät, 0 ist eine darstellungsgerät.  <br/> |
   

