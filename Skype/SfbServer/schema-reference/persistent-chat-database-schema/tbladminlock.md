---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock enthält die administratorsperre, die zum Ausführen einiger Administrator Befehle erforderlich ist.
ms.openlocfilehash: cb3a03fa7404004df37da2adf07eff1e37ff334f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814693"
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock enthält die administratorsperre, die zum Ausführen einiger Administrator Befehle erforderlich ist.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |DateTime, nicht NULL  <br/> |Ablaufdatum und-Uhrzeit Sperren Der Besitzer kann diesen Wert in regelmäßigen Abständen verlängern.  <br/> |
|lockServerID  <br/> |int, nicht NULL  <br/> |Die ID des Servers, der die Sperre besitzt.  <br/> |
|lockActorID  <br/> |int, nicht NULL  <br/> |Die ID des Prinzipals, der die Sperre besitzt.  <br/> |
   

