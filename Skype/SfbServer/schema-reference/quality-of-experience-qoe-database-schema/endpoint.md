---
title: Endpoint-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: Die Endpunkt-Tabelle ist eine unterstützende Tabelle, die Informationen zu den Endpunkten gespeichert, die in der Datenbank aufgezeichnet Sitzungen teilgenommen haben. Jeder Datensatz in der Tabelle steht für einen Endpunkt.
ms.openlocfilehash: f9c304408006ef9caf5521b8f0bbe28c2d917abe
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882997"
---
# <a name="endpoint-table"></a>Endpoint-Tabelle
 
Die Endpunkt-Tabelle ist eine unterstützende Tabelle, die Informationen zu den Endpunkten gespeichert, die in der Datenbank aufgezeichnet Sitzungen teilgenommen haben. Jeder Datensatz in der Tabelle steht für einen Endpunkt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diesen Endpunkt identifiziert.  <br/> |
|**Name** <br/> |nvarchar(256)  <br/> |Eindeutige  <br/> |Name des Endpunkts.  <br/> |
|**OS** <br/> |nvarchar(128)  <br/> | <br/> |Betriebssystem (OS) des Endpunkts.  <br/> |
|**CPUName** <br/> |nvarchar(128)  <br/> ||Prozessorname des Endpunkts.  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||Anzahl der Prozessorkerne des Endpunkts.  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||Prozessorgeschwindigkeit des Endpunkts.  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || Bitflag, die angibt, ob das System in einer virtualisierten Umgebung ausgeführt wird: <br/>  0 x 0000 - keine <br/>  0 x 0001 - Hyper-v <br/>  0 x 0002 - VMWare <br/>  0 x 0004 - virtual PC <br/>  0 x 0008 - Xen PC <br/> |
   

