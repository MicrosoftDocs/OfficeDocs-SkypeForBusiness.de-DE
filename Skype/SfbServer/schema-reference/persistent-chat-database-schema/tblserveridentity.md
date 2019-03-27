---
title: tblServerIdentity
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: TblServerIdentity enthält die aktiven Chatserver im Pool Persistent Chat Server.
ms.openlocfilehash: 1f9455e4c35a3bc6061c1d44ad10cbd4778c6c1f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899526"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
TblServerIdentity enthält die aktiven Chatserver im Pool Persistent Chat Server.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|serverID  <br/> |Int, nicht null  <br/> |Server-ID Die Instanz-ID entspricht aus dem zentralen Verwaltungsspeicher.  <br/> |
|serverAddress  <br/> |Nvarchar (256), nicht null  <br/> |Serveradresse mit der Windows Communication Foundation-Adresse.  <br/> |
|serverLastPingTime  <br/> |datetime  <br/> |Der letzte Zeitpunkt, die den Kanalserver aktualisiert diese Zeile zum Nachweis übergeben, die er ausgeführt wird.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|serverID  <br/> |Primärschlüssel.  <br/> |
   

