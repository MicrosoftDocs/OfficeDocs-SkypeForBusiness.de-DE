---
title: tblAdminLock
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
ms.openlocfilehash: 919ead84ed9baab859e1e85eb2f30f5ff6902531
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tbladminlock"></a>tblAdminLock
 
TblAdminLock enthält die Administratorsperre, die zum Administratorbefehle erforderlich ist.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |DateTime, nicht null  <br/> |Ablaufdatum und-Uhrzeit zu sperren. Der Besitzer kann diesen Wert in regelmäßigen Abständen erweitern.  <br/> |
|lockServerID  <br/> |Int, nicht null  <br/> |ID des Servers, der die Sperre besitzt.  <br/> |
|lockActorID  <br/> |Int, nicht null  <br/> |ID des Prinzipals, der die Sperre besitzt.  <br/> |
   

