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
ms.localizationpriority: medium
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: "\"tblEnumValue\" ist eine hardkodierte Tabelle mit den Werten \"Visibility\" und \"Behavior\" der Attribute, die in der \"Node\"-Tabelle verwendet werden."
ms.openlocfilehash: 0854b20316f0200e2521109880cad32862524c22
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619701"
---
# <a name="tblenumvalue"></a>tblEnumValue
 
"tblEnumValue" ist eine hardkodierte Tabelle mit den Werten "Visibility" und "Behavior" der Attribute, die in der "Node"-Tabelle verwendet werden.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|valueID  <br/> |smallint, nicht NULL  <br/> |ID des Werts.  <br/> |
|Attributeid  <br/> |smallint, nicht NULL  <br/> |ID des Attributs.  <br/> |
|attributeValue  <br/> |nvarchar  (256), nicht NULL  <br/> |Name des Werts.  <br/> |
   
**Keys**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|valueID  <br/> |Primärschlüssel  <br/> |
|Attributeid  <br/> |Fremdschlüssel mit Suche in der Tabelle "tblEnumAttribute.attributeID".  <br/> |
   
**Tabellenwerte**

|**valueID**|**Attributeid**|**attributeValue**|
|:-----|:-----|:-----|
|2   <br/> |1   <br/> |privat  <br/> |
|3   <br/> |1   <br/> |Bereich  <br/> |
|4   <br/> |2   <br/> |Normalen  <br/> |
|5   <br/> |2   <br/> |Auditorium  <br/> |
|6   <br/> |1   <br/> |Öffnen  <br/> |
   
## <a name="see-also"></a>Siehe auch

[tblNode](tblnode.md)
