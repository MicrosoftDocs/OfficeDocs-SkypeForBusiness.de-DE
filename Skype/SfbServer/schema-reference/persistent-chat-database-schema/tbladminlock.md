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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212663"
---
# <a name="tbladminlock"></a>tblAdminLock
 
TblAdminLock enthält die Administratorsperre, die zum Administratorbefehle erforderlich ist.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |DateTime, nicht null  <br/> |Ablaufdatum und-Uhrzeit zu sperren. Der Besitzer kann diesen Wert in regelmäßigen Abständen erweitern.  <br/> |
|lockServerID  <br/> |Int, nicht null  <br/> |ID des Servers, der die Sperre besitzt.  <br/> |
|lockActorID  <br/> |Int, nicht null  <br/> |ID des Prinzipals, der die Sperre besitzt.  <br/> |
   

