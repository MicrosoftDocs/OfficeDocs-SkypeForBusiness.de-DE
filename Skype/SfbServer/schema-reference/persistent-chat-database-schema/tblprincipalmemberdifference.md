---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: Principalmemberdifference enthält Änderungen der Gruppenmitgliedschaften (sowohl hinzugefügte als auch entfernte Mitglieder), die von der Active Directory Domain Services Sync später noch nicht verarbeitet wurden.
ms.openlocfilehash: 4445bc6a4b83053d7d9244fc20d0a7a8cbd01b26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902236"
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
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
   

