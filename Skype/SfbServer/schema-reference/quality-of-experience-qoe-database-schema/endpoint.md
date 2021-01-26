---
title: Endpunkttabelle
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
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: Bei der Tabelle "Endpunkt" handelt es sich um eine Tabelle, in der Informationen zu den Endpunkten gespeichert werden, die an in der Datenbank aufgezeichneten Sitzungen teilgenommen haben. Jeder Datensatz in der Tabelle stellt einen Endpunkt dar.
ms.openlocfilehash: 9caa0571e562a84c1678208f0e70c27317deda3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823065"
---
# <a name="endpoint-table"></a>Endpunkttabelle
 
Bei der Tabelle "Endpunkt" handelt es sich um eine Tabelle, in der Informationen zu den Endpunkten gespeichert werden, die an in der Datenbank aufgezeichneten Sitzungen teilgenommen haben. Jeder Datensatz in der Tabelle stellt einen Endpunkt dar.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diesen Endpunkt identifiziert.  <br/> |
|**Name** <br/> |nvarchar(256)  <br/> |Eigen  <br/> |Endpunktname.  <br/> |
|**Betriebssystem** <br/> |nvarchar(128)  <br/> | <br/> |Betriebssystem des Endpunkts.  <br/> |
|**CPUName** <br/> |nvarchar(128)  <br/> ||Der CPU-Name des Endpunkts.  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||Die Anzahl der CPU-Kerne des Endpunkts.  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||Cpuprozessorgeschwindigkeit des Endpunkts.  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || Bit-Flag, das angibt, ob das System in einer virtualisierten Umgebung ausgeführt wird: <br/>  0x0000 – Keine <br/>  0x0001 – HyperV <br/>  0x0002 – VMWare <br/>  0x0004 – Virtueller PC <br/>  0x0008 – Xen PC <br/> |
   

