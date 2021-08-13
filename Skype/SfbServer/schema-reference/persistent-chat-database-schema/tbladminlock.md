---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: Die „tblAdminLock“-Tabelle enthält die Administratorsperre, die zur Ausführung bestimmter Administratorbefehle erforderlich ist.
ms.openlocfilehash: ad3b2543e2715462b953c611c8b5f24ea7885a6cb910931aa5b832b8196856eb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351944"
---
# <a name="tbladminlock"></a>tblAdminLock
 
Die „tblAdminLock“-Tabelle enthält die Administratorsperre, die zur Ausführung bestimmter Administratorbefehle erforderlich ist.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime, nicht NULL  <br/> |Ablaufdatum und -zeit der Sperre. Der Besitzer kann diesen Wert in regelmäßigen Abständen verlängern.  <br/> |
|lockServerID  <br/> |int, nicht NULL  <br/> |ID des Servers, der die Sperre besitzt.  <br/> |
|lockActorID  <br/> |int, nicht NULL  <br/> |ID des Prinzipals, der die Sperre besitzt.  <br/> |
   

