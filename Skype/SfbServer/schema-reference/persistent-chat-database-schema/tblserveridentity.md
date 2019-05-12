---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: TblServerIdentity enthält die aktiven Chatserver im Pool Persistent Chat Server.
ms.openlocfilehash: d780c2153b2e7f9f1ed5aad20217228e44f29504
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924808"
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
   

