---
title: Device-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Die Gerätetabelle ist eine unterstützende Tabelle, in der Informationen zu den verschiedenen Aufnahme-oder Render-Geräten gespeichert werden. Jeder Datensatz in der Tabelle steht für ein Gerät.
ms.openlocfilehash: 93e6b2215fa1e20b930d678c45f10e26feffd351
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810153"
---
# <a name="device-table"></a>Device-Tabelle
 
Die Gerätetabelle ist eine unterstützende Tabelle, in der Informationen zu den verschiedenen Aufnahme-oder Render-Geräten gespeichert werden. Jeder Datensatz in der Tabelle steht für ein Gerät.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Nummer, die dieses Gerät kennzeichnet.  <br/> |
|**DeviceName** <br/> |nvarchar(256)  <br/> |DeviceName + DeviceType ist eindeutig  <br/> |Gerätename.  <br/> |
|**DeviceType** <br/> |bit  <br/> |DeviceName + DeviceType ist eindeutig  <br/> |Gerätetyp. 1 ist ein Aufnahmegerät, 0 ist ein Render-Gerät.  <br/> |
   

