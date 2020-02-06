---
title: MonitoredRegionLink-Tabelle
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
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: Die Tabelle MonitoredRegionLink ist eine unterstützende Tabelle. Jeder Datensatz steht für einen Link zwischen zwei Ländern/Regionen.
ms.openlocfilehash: a6b92460e2b097460681023f7d6877f02c046bdc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807813"
---
# <a name="monitoredregionlink-table"></a>MonitoredRegionLink-Tabelle
 
Die Tabelle MonitoredRegionLink ist eine unterstützende Tabelle. Jeder Datensatz steht für einen Link zwischen zwei Ländern/Regionen.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |Primär, fremd  <br/> |Wird in der [Regions Tabelle](region.md)referenziert.  <br/> |
|**Region2Key** <br/> |int  <br/> |Primär, fremd  <br/> |Wird in der [Regions Tabelle](region.md)referenziert.  <br/> |
   

