---
title: Tabelle "MonitoredRegionLink"
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
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: Die Tabelle "MonitoredRegionLink" ist eine Tabelle mit Unterstützung. Jeder Datensatz stellt eine Verknüpfung zwischen zwei Ländern/Regionen dar.
ms.openlocfilehash: f30ba249f89a2247e0e03c71fc97f05e69c59bcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806345"
---
# <a name="monitoredregionlink-table"></a>Tabelle "MonitoredRegionLink"
 
Die Tabelle "MonitoredRegionLink" ist eine Tabelle mit Unterstützung. Jeder Datensatz stellt eine Verknüpfung zwischen zwei Ländern/Regionen dar.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |Primär, Fremd  <br/> |Referenziert aus der [Tabelle "Region".](region.md)  <br/> |
|**Region2Key** <br/> |int  <br/> |Primär, Fremd  <br/> |Referenziert aus der [Tabelle "Region".](region.md)  <br/> |
   

