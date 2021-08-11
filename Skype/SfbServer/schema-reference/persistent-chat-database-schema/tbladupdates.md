---
title: tblADUpdates
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
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates enthält Active Directory Domain Services-Änderungen, die noch nicht von den späteren Active Directory-Synchronisierungsschritten verarbeitet wurden.
ms.openlocfilehash: 992834e0086df6ecbc0b8b1cf13a2feaca53cd6ed3f80b6a076abef31e362a6b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54329429"
---
# <a name="tbladupdates"></a>tblADUpdates
 
tblADUpdates enthält Active Directory Domain Services-Änderungen, die noch nicht von den späteren Active Directory-Synchronisierungsschritten verarbeitet wurden.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, nicht NULL  <br/> |Prinzipal-GUID des geänderten Objekts.  <br/> |
|prinADPath  <br/> |nvarchar (384), nicht NULL  <br/> |Distinguished Name (DN) des Objekts.  <br/> |
|prinAttributesChanged  <br/> |bit, nicht NULL  <br/> |TRUE, wenn sich mindestens ein Attribut des Objekts geändert hat.  <br/> |
|prinMembersChanged  <br/> |bit, nicht NULL  <br/> |TRUE, wenn sich die Mitgliedschaft geändert hat.  <br/> |
|prinAffiliationsChanged  <br/> |bit, nicht NULL  <br/> |Nicht verwendet.  <br/> |
|prinDeleted  <br/> |bit, nicht NULL  <br/> |TRUE, wenn das Objekt gelöscht wurde.  <br/> |
|lastUpdated  <br/> |datetime, nicht NULL  <br/> |Zeitstempel für den Zeitpunkt, an dem die Zeile eingefügt wurde.  <br/> |
   

