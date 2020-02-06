---
title: tblEnumValue
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
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue ist eine hart codierte Tabelle, die die Sichtbarkeits-und Verhaltens Werte der Attribute enthält, die in der Knoten Tabelle verwendet werden.
ms.openlocfilehash: accb9cb4801984bd4b3839cd44e5b7feb8d06baa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814603"
---
# <a name="tblenumvalue"></a>tblEnumValue
 
tblEnumValue ist eine hart codierte Tabelle, die die Sichtbarkeits-und Verhaltens Werte der Attribute enthält, die in der Knoten Tabelle verwendet werden.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|Werttyp  <br/> |smallint, nicht NULL  <br/> |Die ID des Werts.  <br/> |
|AttributeID  <br/> |smallint, nicht NULL  <br/> |Die ID des Attributs.  <br/> |
|AttributeValue  <br/> |nvarchar (256); nicht NULL  <br/> |Der Name des Werts.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|Werttyp  <br/> |Primärschlüssel  <br/> |
|AttributeID  <br/> |Fremdschlüssel mit Lookup in der tblEnumAttribute. AttributeCollection-Tabelle.  <br/> |
   
**Tabellenwerte**

|**Werttyp**|**AttributeID**|**AttributeValue**|
|:-----|:-----|:-----|
|2  <br/> |1  <br/> |privat  <br/> |
|3  <br/> |1  <br/> |Bereich  <br/> |
|4  <br/> |2  <br/> |normal  <br/> |
|5  <br/> |2  <br/> |Auditorium  <br/> |
|6  <br/> |1  <br/> |Öffnen  <br/> |
   
## <a name="see-also"></a>Siehe auch

[tblNode](tblnode.md)
