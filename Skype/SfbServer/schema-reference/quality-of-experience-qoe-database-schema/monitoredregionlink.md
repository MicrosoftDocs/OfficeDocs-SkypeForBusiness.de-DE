---
title: MonitoredRegionLink-Tabelle
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
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: Die MonitoredRegionLink-Tabelle ist eine Unterstützende Tabelle. Jeder Datensatz stellt eine Verbindung zwischen zwei Ländern/Regionen dar.
ms.openlocfilehash: f026e35dfd0c0cfd0b7a43d62089754b6824cfa8
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604614"
---
# <a name="monitoredregionlink-table"></a>MonitoredRegionLink-Tabelle
 
Die MonitoredRegionLink-Tabelle ist eine Unterstützende Tabelle. Jeder Datensatz stellt eine Verbindung zwischen zwei Ländern/Regionen dar.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |Primär, Fremd  <br/> |Referenziert aus der [Region-Tabelle.](region.md)  <br/> |
|**Region2Key** <br/> |int  <br/> |Primär, Fremd  <br/> |Referenziert aus der [Region-Tabelle.](region.md)  <br/> |
   

