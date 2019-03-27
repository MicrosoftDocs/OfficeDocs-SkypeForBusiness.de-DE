---
title: tblADUpdates
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: TblADUpdates enthält Änderungen der Active Directory Domain Services, die von den späteren Schritten für die Active Directory-Synchronisierung noch nicht verarbeitet wurden.
ms.openlocfilehash: 0e7bde110ad3d0495cb7ddea55e405eac21d96b4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899603"
---
# <a name="tbladupdates"></a>tblADUpdates
 
TblADUpdates enthält Änderungen der Active Directory Domain Services, die von den späteren Schritten für die Active Directory-Synchronisierung noch nicht verarbeitet wurden.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, nicht null  <br/> |Prinzipal-GUID des geänderten Objekts.  <br/> |
|prinADPath  <br/> |Nvarchar (384), nicht null  <br/> |Distinguished Name des Objekts.  <br/> |
|prinAttributesChanged  <br/> |Bit, nicht null  <br/> |True, wenn mindestens ein Attribut des Objekts geändert.  <br/> |
|prinMembersChanged  <br/> |Bit, nicht null  <br/> |True, wenn die Mitgliedschaft geändert hat.  <br/> |
|prinAffiliationsChanged  <br/> |Bit, nicht null  <br/> |Nicht verwendet.  <br/> |
|prinDeleted  <br/> |Bit, nicht null  <br/> |True, wenn das Objekt gelöscht wurde.  <br/> |
|lastUpdated  <br/> |DateTime, nicht null  <br/> |Zeitstempel der, wenn die Zeile eingefügt wurde.  <br/> |
   

