---
title: tblPrincipalMeta
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
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta enthält die Prinzipale, die aus den Active Directory-Domänendiensten aktualisiert werden müssen.
ms.openlocfilehash: c76f4a74b3f627d360a2d745e46b6f2dac26bff0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813573"
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
tblPrincipalMeta enthält die Prinzipale, die aus den Active Directory-Domänendiensten aktualisiert werden müssen.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|prinID  <br/> |int, nicht NULL  <br/> |Prinzipal-ID.  <br/> |
|prinAffiliationsDirty  <br/> |Bit, nicht NULL  <br/> |"True", wenn Haupt Zuordnungen aktualisiert werden müssen.  <br/> |
|prinAttributesDirty  <br/> |Bit, nicht NULL  <br/> |"True", wenn Prinzipal Attribute aktualisiert werden müssen.  <br/> |
|prinDeleted  <br/> |Bit, nicht NULL  <br/> |"True", wenn der Prinzipal gelöscht wurde.  <br/> |
|tryCount  <br/> |int  <br/> |Die Anzahl der Versuche, den Prinzipal von AD DS zu aktualisieren, die bisher geschehen sind.  <br/> |
|lastTry  <br/> |datetime  <br/> |Zeitstempel des letzten Versuchs, den Prinzipal zu aktualisieren. Kann NULL sein, wenn noch keine Aktualisierung versucht wurde.  <br/> |
|nextTry  <br/> |datetime  <br/> |Zeitstempel für die nächste geplante Aktualisierung. Kann NULL sein, wenn keine weitere Aktualisierung geplant wurde.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|prinID  <br/> |Primärschlüssel  <br/> |
|prinID  <br/> |Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.  <br/> |
   

