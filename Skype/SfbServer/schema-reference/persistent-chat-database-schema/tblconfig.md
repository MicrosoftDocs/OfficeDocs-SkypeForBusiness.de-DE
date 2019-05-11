---
title: tblConfig
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: TblConfig enthält einige Persistent Chat Server nicht unterstützte Konfiguration in einer Zeile.
ms.openlocfilehash: 79cd7e2303210bb07f35fa2c6b7ecc5c86b7e8cc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930022"
---
# <a name="tblconfig"></a>tblConfig
 
TblConfig enthält einige Persistent Chat Server nicht unterstützte Konfiguration in einer Zeile.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|Stellen configLabel  <br/> |Nvarchar (255), nicht null  <br/> |Enthält "Pool".  <br/> |
|configContent  <br/> |Nvarchar (Max.)  <br/> |Inhalt der Konfiguration.  <br/> |
|configPoolID  <br/> |GUID, nicht null  <br/> |Eindeutige ID der Datenbankinstanz.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|Stellen configLabel  <br/> |Primärschlüssel.  <br/> |
   

