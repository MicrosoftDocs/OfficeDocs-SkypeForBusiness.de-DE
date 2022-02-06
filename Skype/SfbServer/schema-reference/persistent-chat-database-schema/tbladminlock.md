---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: 'Die „tblAdminLock“-Tabelle enthält die Administratorsperre, die zur Ausführung bestimmter Administratorbefehle erforderlich ist.'
---

# <a name="tbladminlock"></a>tblAdminLock
 
Die „tblAdminLock“-Tabelle enthält die Administratorsperre, die zur Ausführung bestimmter Administratorbefehle erforderlich ist.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime, nicht NULL  <br/> |Ablaufdatum und -zeit der Sperre. Der Besitzer kann diesen Wert in regelmäßigen Abständen verlängern.  <br/> |
|lockServerID  <br/> |int, nicht NULL  <br/> |ID des Servers, der die Sperre besitzt.  <br/> |
|lockActorID  <br/> |int, nicht NULL  <br/> |ID des Prinzipals, der die Sperre besitzt.  <br/> |
   

