---
title: MonitoredRegionLink-Tabelle
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: Die MonitoredRegionLink-Tabelle ist eine Unterstützende Tabelle. Jeder Datensatz stellt eine Verbindung zwischen zwei Ländern/Regionen dar.
ms.openlocfilehash: 39add4c7ba3fc67c68645498772b06715967aa39
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763123"
---
# <a name="monitoredregionlink-table"></a>MonitoredRegionLink-Tabelle
 
Die MonitoredRegionLink-Tabelle ist eine Unterstützende Tabelle. Jeder Datensatz stellt eine Verbindung zwischen zwei Ländern/Regionen dar.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |Primär, Fremd  <br/> |Referenziert aus der [Region-Tabelle.](region.md)  <br/> |
|**Region2Key** <br/> |int  <br/> |Primär, Fremd  <br/> |Referenziert aus der [Region-Tabelle.](region.md)  <br/> |
   

