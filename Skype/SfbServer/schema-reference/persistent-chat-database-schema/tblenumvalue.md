---
title: tblEnumValue
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: "\"TblEnumValue\" ist eine hardkodierte Tabelle mit den Werten Visibility und Behavior der Attribute, die in der Node-Tabelle verwendet werden."
ms.openlocfilehash: 00ee5a7a7538fa620e438ead5e986f859ef25a6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929868"
---
# <a name="tblenumvalue"></a>tblEnumValue
 
"TblEnumValue" ist eine hardkodierte Tabelle mit den Werten Visibility und Behavior der Attribute, die in der Node-Tabelle verwendet werden.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|valueID  <br/> |Smallint, nicht null  <br/> |ID des Werts.  <br/> |
|attributeID  <br/> |Smallint, nicht null  <br/> |ID des Attributs.  <br/> |
|attributeValue  <br/> |Nvarchar (256), nicht null  <br/> |Name des Werts.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|valueID  <br/> |Primärschlüssel.  <br/> |
|attributeID  <br/> |Fremdschlüssel mit Abfrage der Tabelle "tblenumattribute.AttributeID".  <br/> |
   
**Tabellenwerte**

|**valueID**|**attributeID**|**attributeValue**|
|:-----|:-----|:-----|
|2  <br/> |1  <br/> |privat  <br/> |
|3  <br/> |1  <br/> |Umfang  <br/> |
|4  <br/> |2  <br/> |normale  <br/> |
|5  <br/> |2  <br/> |Auditorium  <br/> |
|6  <br/> |1  <br/> |Öffnen Sie  <br/> |
   
## <a name="see-also"></a>Siehe auch

[tblNode](tblnode.md)
