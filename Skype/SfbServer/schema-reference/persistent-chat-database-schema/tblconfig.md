---
title: tblConfig
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
ms.localizationpriority: medium
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig enthält eine Konfiguration für den Server für beständigen Chat in einer Zeile, die nicht unterstützt wird.
ms.openlocfilehash: 8cf1fc53087d3fc786ac47e848a21dbd2a8f5549
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595307"
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
   

