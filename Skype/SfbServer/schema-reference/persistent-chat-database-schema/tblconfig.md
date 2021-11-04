---
title: tblConfig
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig enthält eine Konfiguration für den Server für beständigen Chat in einer Zeile, die nicht unterstützt wird.
ms.openlocfilehash: 344922f4ffb1cf172c154117c95491558f8e8905
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767363"
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
   

