---
title: tblEnumValue
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
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: "\"tblEnumValue\" ist eine hardkodierte Tabelle mit den Werten \"Visibility\" und \"Behavior\" der Attribute, die in der \"Node\"-Tabelle verwendet werden."
ms.openlocfilehash: a13bfbe79d1eb118f0727f390816a26d35a508d0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816025"
---
# <a name="tblenumvalue"></a>tblEnumValue
 
"tblEnumValue" ist eine hardkodierte Tabelle mit den Werten "Visibility" und "Behavior" der Attribute, die in der "Node"-Tabelle verwendet werden.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|valueID  <br/> |smallint, nicht NULL  <br/> |ID des Werts.  <br/> |
|attributeID  <br/> |smallint, nicht NULL  <br/> |ID des Attributs.  <br/> |
|attributeValue  <br/> |nvarchar  (256), nicht NULL  <br/> |Name des Werts.  <br/> |
   
**Keys**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|valueID  <br/> |Primärschlüssel  <br/> |
|attributeID  <br/> |Fremdschlüssel mit Suche in der Tabelle "tblEnumAttribute.attributeID".  <br/> |
   
**Tabellenwerte**

|**valueID**|**attributeID**|**attributeValue**|
|:-----|:-----|:-----|
|2   <br/> |1   <br/> |private  <br/> |
|3   <br/> |1   <br/> |Bereich  <br/> |
|4   <br/> |2   <br/> |normal  <br/> |
|5   <br/> |2   <br/> |auditorium  <br/> |
|6   <br/> |1   <br/> |open  <br/> |
   
## <a name="see-also"></a>Siehe auch

[tblNode](tblnode.md)
