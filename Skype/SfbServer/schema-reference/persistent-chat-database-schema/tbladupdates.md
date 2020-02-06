---
title: tblADUpdates
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
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates enthält Änderungen an Active Directory-Domänendiensten, die noch nicht von den späteren Active Directory-Synchronisierungs Schritten verarbeitet wurden.
ms.openlocfilehash: 6d50e065bd10e11383f606b2a4dfed0d5584cd1e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814683"
---
# <a name="tbladupdates"></a>tblADUpdates
 
tblADUpdates enthält Änderungen an Active Directory-Domänendiensten, die noch nicht von den späteren Active Directory-Synchronisierungs Schritten verarbeitet wurden.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, nicht NULL  <br/> |Prinzipal-GUID des geänderten Objekts.  <br/> |
|prinADPath  <br/> |nvarchar (384); nicht NULL  <br/> |Distinguished Name des Objekts.  <br/> |
|prinAttributesChanged  <br/> |Bit, nicht NULL  <br/> |"True", wenn mindestens ein Attribut des Objekts geändert wurde.  <br/> |
|prinMembersChanged  <br/> |Bit, nicht NULL  <br/> |"True", wenn die Mitgliedschaft geändert wurde.  <br/> |
|prinAffiliationsChanged  <br/> |Bit, nicht NULL  <br/> |Nicht verwendet.  <br/> |
|prinDeleted  <br/> |Bit, nicht NULL  <br/> |"True", wenn das Objekt gelöscht wurde.  <br/> |
|lastUpdated  <br/> |DateTime, nicht NULL  <br/> |Zeitstempel, wann die Zeile eingefügt wurde.  <br/> |
   

