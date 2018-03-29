---
title: Principalmemberdifference
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: Principalmemberdifference enthält Änderungen der Gruppenmitgliedschaften (sowohl hinzugefügte als auch entfernte Mitglieder), die von der Active Directory Domain Services Sync später noch nicht verarbeitet wurden.
ms.openlocfilehash: 603c8345f2adc2ba7d5eb04835218fd3e83d8ed4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmemberdifference"></a>Principalmemberdifference
 
Principalmemberdifference enthält Änderungen der Gruppenmitgliedschaften (sowohl hinzugefügte als auch entfernte Mitglieder), die von der Active Directory Domain Services Sync später noch nicht verarbeitet wurden.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, nicht null  <br/> |Prinzipal-GUID der geänderten Gruppe.  <br/> |
|memberADPath  <br/> |Nvarchar (256)  <br/> |Distinguished Name des Elements.  <br/> |
|memberRemoved  <br/> |Bit, nicht null  <br/> |False, wenn das Element hinzugefügt wurde. True, wenn das Element entfernt wurde.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|\<PrinGuid memberADPath\>  <br/> |Primärschlüssel.  <br/> |
   

