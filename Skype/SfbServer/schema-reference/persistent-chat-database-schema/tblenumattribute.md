---
title: tblEnumAttribute
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
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: "\"EnumAttribute\" ist eine hardkodierte Tabelle, mit den Attributen \"Visibility\" und \"Behavior\", die in der \"Node\"-Tabelle verwendet werden."
ms.openlocfilehash: 698eda1e6e815ad4de4042312be1738a3a41d1f2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809715"
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
"EnumAttribute" ist eine hardkodierte Tabelle, mit den Attributen "Visibility" und "Behavior", die in der "Node"-Tabelle verwendet werden.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|attributeID  <br/> |smallint, nicht NULL  <br/> |ID des Attributs.  <br/> |
|attributeName  <br/> |nvarchar (256), nicht NULL  <br/> |Name des Attributs.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|attributeID  <br/> |Primärschlüssel  <br/> |
   
**Tabellenwerte**

|**attributeID**|**attributeName**|
|:-----|:-----|
|1   <br/> |Sichtbarkeit.  <br/> |
|2   <br/> |Verhalten.  <br/> |
   
## <a name="see-also"></a>Weitere Informationen

[tblNode](tblnode.md)
