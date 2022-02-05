---
title: tblPrincipalMemberDifference
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: 'tblPrincipalMemberDifference enthält Gruppenmitgliedschaftsänderungen (sowohl hinzugefügte als auch entfernte Mitglieder), die noch nicht von den späteren Active Directory Domain Services-Synchronisierungsschritten verarbeitet wurden.'
---

# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
tblPrincipalMemberDifference enthält Gruppenmitgliedschaftsänderungen (sowohl hinzugefügte als auch entfernte Mitglieder), die noch nicht von den späteren Active Directory Domain Services-Synchronisierungsschritten verarbeitet wurden.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, nicht NULL  <br/> |Prinzipal-GUID der geänderten Gruppe.  <br/> |
|memberADPath  <br/> |nvarchar (256)  <br/> |Distinguished Name (DN) des Mitglieds.  <br/> |
|memberRemoved  <br/> |bit, nicht NULL  <br/> |FALSE, wenn das Mitglied hinzugefügt wurde. TRUE, wenn das Mitglied entfernt wurde.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |Primärschlüssel  <br/> |
   

