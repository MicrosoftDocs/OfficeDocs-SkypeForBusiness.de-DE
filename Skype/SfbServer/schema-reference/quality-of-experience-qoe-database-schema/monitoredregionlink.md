---
title: MonitoredRegionLink-Tabelle
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
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
---

# <a name="monitoredregionlink-table"></a>MonitoredRegionLink-Tabelle
 
Die MonitoredRegionLink-Tabelle ist eine Unterstützende Tabelle. Jeder Datensatz stellt eine Verbindung zwischen zwei Ländern/Regionen dar.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |Primär, Fremd  <br/> |Referenziert aus der [Region-Tabelle](region.md).  <br/> |
|**Region2Key** <br/> |int  <br/> |Primär, Fremd  <br/> |Referenziert aus der [Region-Tabelle](region.md).  <br/> |
   

