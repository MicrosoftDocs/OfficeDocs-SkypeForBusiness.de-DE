---
title: tblAdminLock
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: TblAdminLock enthält die Administratorsperre, die zum Administratorbefehle erforderlich ist.
ms.openlocfilehash: bf7537b7d1081bd415ff2e8fe3615864c71f593a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898952"
---
# <a name="tbladminlock"></a>tblAdminLock
 
TblAdminLock enthält die Administratorsperre, die zum Administratorbefehle erforderlich ist.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |DateTime, nicht null  <br/> |Ablaufdatum und-Uhrzeit zu sperren. Der Besitzer kann diesen Wert in regelmäßigen Abständen erweitern.  <br/> |
|lockServerID  <br/> |Int, nicht null  <br/> |ID des Servers, der die Sperre besitzt.  <br/> |
|lockActorID  <br/> |Int, nicht null  <br/> |ID des Prinzipals, der die Sperre besitzt.  <br/> |
   

