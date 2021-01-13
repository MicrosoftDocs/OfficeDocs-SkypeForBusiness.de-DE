---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: "\"tblServerIdentity\" enthält die aktiven Chatserver im Pool für den Server für beständigen Chat."
ms.openlocfilehash: 7fa8c1b804432b3a9368785682f45e9ce8d7898e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831495"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
"tblServerIdentity" enthält die aktiven Chatserver im Pool für den Server für beständigen Chat.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|serverID  <br/> |int, nicht NULL  <br/> |Server-ID. Entspricht der Instanz-ID aus dem zentralen Verwaltungsspeicher.  <br/> |
|serverAddress  <br/> |nvarchar (256), nicht NULL  <br/> |Serveradresse mit der Windows Communication Foundation-Adresse.  <br/> |
|serverLastPingTime  <br/> |Datum/Uhrzeit  <br/> |Der letzte Zeitpunkt, zu dem der Kanalserver diese Zeile aktualisiert hat, um die Ausführung zu beweisen.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|serverID  <br/> |Primärschlüssel  <br/> |
   

