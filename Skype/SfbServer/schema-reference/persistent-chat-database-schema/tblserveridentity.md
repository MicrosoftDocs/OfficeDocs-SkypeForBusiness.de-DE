---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity enthält die aktiven Chat Server im persistent Chat Serverpool.
ms.openlocfilehash: b35960bd1deef5470724f580bce2375b2e034cb9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295188"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity enthält die aktiven Chat Server im persistent Chat Serverpool.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|ServerID  <br/> |int, nicht NULL  <br/> |Server-ID. Entspricht der Instanz-ID des zentralen Verwaltungsspeichers.  <br/> |
|ServerAddress  <br/> |nvarchar (256); nicht NULL  <br/> |Server Adresse unter Verwendung der Windows Communication Foundation-Adresse.  <br/> |
|serverLastPingTime  <br/> |datetime  <br/> |Der letzte Zeitpunkt, zu dem der Kanal Server diese Zeile aktualisiert hat, um zu beweisen, dass er ausgeführt wird.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|ServerID  <br/> |Primärschlüssel  <br/> |
   

