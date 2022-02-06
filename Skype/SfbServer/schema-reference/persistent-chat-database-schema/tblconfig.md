---
title: tblConfig
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
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: 'tblConfig enthält eine Konfiguration für den Server für beständigen Chat in einer Zeile, die nicht unterstützt wird.'
---

# <a name="tblconfig"></a>tblConfig
 
tblConfig enthält eine Konfiguration für den Server für beständigen Chat in einer Zeile, die nicht unterstützt wird.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar (255), nicht NULL  <br/> |Enthält „Pool“.  <br/> |
|configContent  <br/> |nvarchar (max)  <br/> |Inhalt der Konfiguration.  <br/> |
|configPoolID  <br/> |GUID, nicht NULL  <br/> |Eindeutige ID der Datenbankinstanz.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|configLabel  <br/> |Primärschlüssel  <br/> |
   

