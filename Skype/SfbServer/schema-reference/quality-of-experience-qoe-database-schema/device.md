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
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Die Gerätetabelle ist eine unterstützende Tabelle, in der Informationen zu den verschiedenen Aufnahme-oder Render-Geräten gespeichert werden. Jeder Datensatz in der Tabelle steht für ein Gerät.
ms.openlocfilehash: a73deac9bec6ce4515eaffc256179b10d1f27106
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295006"
---
# <a name="device-table"></a>Device-Tabelle
 
Die Gerätetabelle ist eine unterstützende Tabelle, in der Informationen zu den verschiedenen Aufnahme-oder Render-Geräten gespeichert werden. Jeder Datensatz in der Tabelle steht für ein Gerät.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Nummer, die dieses Gerät kennzeichnet.  <br/> |
|**DeviceName** <br/> |nvarchar(256)  <br/> |DeviceName + DeviceType ist eindeutig  <br/> |Gerätename.  <br/> |
|**DeviceType** <br/> |bit  <br/> |DeviceName + DeviceType ist eindeutig  <br/> |Gerätetyp. 1 ist ein Aufnahmegerät, 0 ist ein Render-Gerät.  <br/> |
   

