---
title: tblAdminLock
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: Die „tblAdminLock“-Tabelle enthält die Administratorsperre, die zur Ausführung bestimmter Administratorbefehle erforderlich ist.
ms.openlocfilehash: 1527cee53bc93c9b26a1cb961bba0a7fa53ae2e8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852839"
---
# <a name="tbladminlock"></a>tblAdminLock
 
Die „tblAdminLock“-Tabelle enthält die Administratorsperre, die zur Ausführung bestimmter Administratorbefehle erforderlich ist.
  
**Columns**

|**Spalte**|**Type**|**Beschreibung**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime, nicht NULL  <br/> |Ablaufdatum und -zeit der Sperre. Der Besitzer kann diesen Wert in regelmäßigen Abständen verlängern.  <br/> |
|lockServerID  <br/> |int, nicht NULL  <br/> |ID des Servers, der die Sperre besitzt.  <br/> |
|lockActorID  <br/> |int, nicht NULL  <br/> |ID des Prinzipals, der die Sperre besitzt.  <br/> |
   

