---
title: Gerätetabelle
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Bei der Device-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird und in der Informationen über die verschiedenen Aufnahme- oder Darstellungsgeräte gespeichert sind. Jeder Datensatz in der Tabelle steht für ein Gerät.
ms.openlocfilehash: b985b927225cb726576b814c035ecce759e6fcba
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58590959"
---
# <a name="device-table"></a>Gerätetabelle
 
Bei der Device-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird und in der Informationen über die verschiedenen Aufnahme- oder Darstellungsgeräte gespeichert sind. Jeder Datensatz in der Tabelle steht für ein Gerät.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die dieses Gerät identifiziert.  <br/> |
|**DeviceName** <br/> |nvarchar(256)  <br/> |DeviceName + DeviceType ist unique  <br/> |Gerätename  <br/> |
|**DeviceType** <br/> |Bit  <br/> |DeviceName + DeviceType ist unique  <br/> |Gerätetyp. 1 ist ein Aufnahmegerät, 0 ist ein Darstellungsgerät.  <br/> |
   

