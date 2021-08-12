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
ms.openlocfilehash: 6996c95ca170082ec89ac7d8fd92648b60c933b1fd72515bb7c3974df8cd5e92
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337583"
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
"EnumAttribute" ist eine hardkodierte Tabelle, mit den Attributen "Visibility" und "Behavior", die in der "Node"-Tabelle verwendet werden.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|Attributeid  <br/> |smallint, nicht NULL  <br/> |ID des Attributs.  <br/> |
|Attributename  <br/> |nvarchar (256), nicht NULL  <br/> |Name des Attributs.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|Attributeid  <br/> |Primärschlüssel  <br/> |
   
**Tabellenwerte**

|**Attributeid**|**Attributename**|
|:-----|:-----|
|1  <br/> |Sichtbarkeit.  <br/> |
|2  <br/> |Verhalten.  <br/> |
   
## <a name="see-also"></a>Siehe auch

[tblNode](tblnode.md)
