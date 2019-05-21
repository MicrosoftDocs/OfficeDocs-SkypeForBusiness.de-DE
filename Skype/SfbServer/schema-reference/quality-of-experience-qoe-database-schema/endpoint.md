---
title: Endpoint-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: Die Endpunkt Tabelle ist eine unterstützende Tabelle, in der Informationen zu den Endpunkten gespeichert werden, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden. Jeder Datensatz in der Tabelle steht für einen Endpunkt.
ms.openlocfilehash: 7d582d382784d04d4495de972aa20673862284f4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294992"
---
# <a name="endpoint-table"></a>Endpoint-Tabelle
 
Die Endpunkt Tabelle ist eine unterstützende Tabelle, in der Informationen zu den Endpunkten gespeichert werden, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden. Jeder Datensatz in der Tabelle steht für einen Endpunkt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diesen Endpunkt kennzeichnet.  <br/> |
|**Name** <br/> |nvarchar(256)  <br/> |Eindeutigen  <br/> |Endpunktname  <br/> |
|**OS** <br/> |nvarchar (128)  <br/> | <br/> |Betriebssystem (OS) des Endpunkts.  <br/> |
|**CPUName** <br/> |nvarchar (128)  <br/> ||Der CPU-Name des Endpunkts.  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||Die Anzahl von CPU-Kernen des Endpunkts.  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||CPU-Prozessorgeschwindigkeit des Endpunkts.  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || Bit-Flag, das angibt, ob das System in einer virtualisierten Umgebung ausgeführt wird: <br/>  0x0000-None <br/>  0x0001-HyperV <br/>  0x0002-VMware <br/>  0x0004 – virtueller PC <br/>  0x0008-xen-PC <br/> |
   

