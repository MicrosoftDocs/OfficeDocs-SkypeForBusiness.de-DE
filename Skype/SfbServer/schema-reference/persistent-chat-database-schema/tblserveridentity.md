---
title: tblServerIdentity
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity enthält die aktiven Chatserver im Serverpool für beständigen Chat.
---

# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity enthält die aktiven Chatserver im Serverpool für beständigen Chat.
  
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
   

