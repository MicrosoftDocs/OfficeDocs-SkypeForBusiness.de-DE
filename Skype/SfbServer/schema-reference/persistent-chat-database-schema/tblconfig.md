---
title: tblConfig
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig enthält eine nicht unterstützte Konfiguration für beständigen Chat Server in einer Zeile.
ms.openlocfilehash: f79af00d6a9f97f0ce0836684a284779be662c1d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814623"
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig enthält eine nicht unterstützte Konfiguration für beständigen Chat Server in einer Zeile.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar (255); nicht NULL  <br/> |Enthält "Pool".  <br/> |
|configContent  <br/> |nvarchar (max)  <br/> |Konfigurationsinhalt.  <br/> |
|configPoolID  <br/> |GUID, nicht NULL  <br/> |Eindeutige ID der Datenbankinstanz.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|configLabel  <br/> |Primärschlüssel  <br/> |
   

