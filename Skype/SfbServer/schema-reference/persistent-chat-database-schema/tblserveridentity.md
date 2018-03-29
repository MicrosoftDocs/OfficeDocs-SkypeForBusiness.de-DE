---
title: tblServerIdentity
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
ms.openlocfilehash: 445021bb486d418011ea21dd32c0339e11b4d17a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
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
   

