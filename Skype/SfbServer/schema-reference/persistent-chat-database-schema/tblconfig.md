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
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: "\"tblConfig\" enthält eine nicht unterstützte Konfiguration des Servers für beständigen Chat in einer Zeile."
ms.openlocfilehash: 614e4e6514d695777c39a9d76482f775bd1a0981
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809735"
---
# <a name="tblconfig"></a>tblConfig
 
"tblConfig" enthält eine nicht unterstützte Konfiguration des Servers für beständigen Chat in einer Zeile.
  
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
   

