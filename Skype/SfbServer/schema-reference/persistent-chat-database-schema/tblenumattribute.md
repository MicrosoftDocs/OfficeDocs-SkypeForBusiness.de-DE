---
title: tblEnumAttribute
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
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute ist eine hart codierte Tabelle, die die Sichtbarkeits-und Verhaltensattribute enthält, die in der Knoten Tabelle verwendet werden.
ms.openlocfilehash: 8244e2fb6ace6c4ed73f017f52df0c85d1f02315
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814613"
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
tblEnumAttribute ist eine hart codierte Tabelle, die die Sichtbarkeits-und Verhaltensattribute enthält, die in der Knoten Tabelle verwendet werden.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|AttributeID  <br/> |smallint, nicht NULL  <br/> |Die ID des Attributs.  <br/> |
|AttributeName  <br/> |nvarchar (256); nicht NULL  <br/> |Name des Attributs.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|AttributeID  <br/> |Primärschlüssel  <br/> |
   
**Tabellenwerte**

|**AttributeID**|**AttributeName**|
|:-----|:-----|
|1  <br/> |Sichtbarkeit.  <br/> |
|2  <br/> |Verhalten.  <br/> |
   
## <a name="see-also"></a>Siehe auch

[tblNode](tblnode.md)
