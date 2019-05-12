---
title: tblAdminLock
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: TblAdminLock enthält die Administratorsperre, die zum Administratorbefehle erforderlich ist.
ms.openlocfilehash: ea1cff137e58ef65eda172a9c09e5dd38e66d8a4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929812"
---
# <a name="tbladminlock"></a>tblAdminLock
 
TblAdminLock enthält die Administratorsperre, die zum Administratorbefehle erforderlich ist.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |DateTime, nicht null  <br/> |Ablaufdatum und-Uhrzeit zu sperren. Der Besitzer kann diesen Wert in regelmäßigen Abständen erweitern.  <br/> |
|lockServerID  <br/> |Int, nicht null  <br/> |ID des Servers, der die Sperre besitzt.  <br/> |
|lockActorID  <br/> |Int, nicht null  <br/> |ID des Prinzipals, der die Sperre besitzt.  <br/> |
   

