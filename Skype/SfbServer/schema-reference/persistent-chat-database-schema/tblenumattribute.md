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
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute ist eine hart codierte Tabelle, die die Sichtbarkeits-und Verhaltensattribute enthält, die in der Knoten Tabelle verwendet werden.
ms.openlocfilehash: b326ebe98592daccf7560dc90e299f31c158cd5c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295419"
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
