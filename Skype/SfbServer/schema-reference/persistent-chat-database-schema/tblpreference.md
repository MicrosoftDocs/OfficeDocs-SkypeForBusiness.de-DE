---
title: tblPreference
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: TblPreference enthält die Clientvoreinstellungen der der Benutzer. Dies wird im Allgemeinen von Clients vor Lync 2013 verwendet.
ms.openlocfilehash: 28656951c80e6e4010e6ca559e3f650e2b9bac4b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tblpreference"></a>tblPreference
 
TblPreference enthält die Clientvoreinstellungen der der Benutzer. Dies wird im Allgemeinen von Clients vor Lync 2013 verwendet.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|prefLabel  <br/> |Nvarchar (255), nicht null  <br/> |Bezeichnen mit einem Format, z. B.: \<Sip-Uri des Benutzers\>|Benutzername. \<Voreinstellungen\>.  <br/> |
|prefSeqID  <br/> |Int, nicht null  <br/> |Fortlaufende Zahl (pro Bezeichnung) für die versionsverwaltung.  <br/> |
|prefContent  <br/> |Nvarchar (Max.)  <br/> |Verschlüsselter Inhalt.  <br/> |
|lastModifiedBy  <br/> |Int, nicht null  <br/> |ID des Prinzipals, der die Voreinstellung aktualisiert hat.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|\<PrefLabel prefSeqID\>  <br/> |Primärschlüssel.  <br/> |
   

