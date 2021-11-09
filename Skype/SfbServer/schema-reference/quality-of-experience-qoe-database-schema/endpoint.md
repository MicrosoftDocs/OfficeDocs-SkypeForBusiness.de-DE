---
title: Endpunkttabelle
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: Die Endpunkttabelle ist eine Unterstützende Tabelle, in der Informationen zu den Endpunkten gespeichert werden, die an in der Datenbank aufgezeichneten Sitzungen teilgenommen haben. Jeder Datensatz in der Tabelle stellt einen Endpunkt dar.
ms.openlocfilehash: 7e892d0e913f8b06fc78f00fbbb348774b9548d3
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834001"
---
# <a name="endpoint-table"></a>Endpunkttabelle
 
Die Endpunkttabelle ist eine Unterstützende Tabelle, in der Informationen zu den Endpunkten gespeichert werden, die an in der Datenbank aufgezeichneten Sitzungen teilgenommen haben. Jeder Datensatz in der Tabelle stellt einen Endpunkt dar.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Nummer, die diesen Endpunkt identifiziert.  <br/> |
|**Name** <br/> |nvarchar(256)  <br/> |Eigen  <br/> |Endpunktname.  <br/> |
|**Betriebssystem** <br/> |nvarchar(128)  <br/> | <br/> |Betriebssystem des Endpunkts.  <br/> |
|**CPUName** <br/> |nvarchar(128)  <br/> ||CPU-Name des Endpunkts.  <br/> |
|**CPUNumberOfCores** <br/> |Smallint  <br/> ||Anzahl der CPU-Kerne des Endpunkts.  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||CPU-Prozessorgeschwindigkeit des Endpunkts.  <br/> |
|**VirtualizationFlag** <br/> |Tinyint  <br/> || Bitkennzeichen, das angibt, ob das System in einer virtualisierten Umgebung ausgeführt wird: <br/>  0x0000 – Keine <br/>  0x0001 – HyperV <br/>  0x0002 – VMWare <br/>  0x0004 – Virtueller PC <br/>  0x0008 – Xen PC <br/> |
   

