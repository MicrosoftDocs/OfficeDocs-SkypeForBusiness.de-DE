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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity enthält die aktiven Chat Server im persistent Chat Serverpool.
ms.openlocfilehash: 4f6389f21c35da914b4943a279d8d485b6ec1eae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812273"
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
   

