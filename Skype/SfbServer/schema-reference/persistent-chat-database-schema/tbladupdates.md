---
title: tblADUpdates
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: TblADUpdates enthält Änderungen der Active Directory Domain Services, die von den späteren Schritten für die Active Directory-Synchronisierung noch nicht verarbeitet wurden.
ms.openlocfilehash: 4ed1abe2d5926c8b34ddccb28133ecc34ddaa03a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929861"
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
   

