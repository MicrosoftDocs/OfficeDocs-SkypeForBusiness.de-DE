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
description: tblServerIdentity enthält die aktiven Chatserver im Serverpool für beständigen Chat.
ms.openlocfilehash: 092331f275ef76372ad1bd2d2462acb9eb7848eea263d59c2276d7a4b6a83779
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303658"
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
   

