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
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock enthält die administratorsperre, die zum Ausführen einiger Administrator Befehle erforderlich ist.
ms.openlocfilehash: ccdc2b2667dee4d1d82a583ef7e7698d3107651a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295524"
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock enthält die administratorsperre, die zum Ausführen einiger Administrator Befehle erforderlich ist.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |DateTime, nicht NULL  <br/> |Ablaufdatum und-Uhrzeit Sperren Der Besitzer kann diesen Wert in regelmäßigen Abständen verlängern.  <br/> |
|lockServerID  <br/> |int, nicht NULL  <br/> |Die ID des Servers, der die Sperre besitzt.  <br/> |
|lockActorID  <br/> |int, nicht NULL  <br/> |Die ID des Prinzipals, der die Sperre besitzt.  <br/> |
   

