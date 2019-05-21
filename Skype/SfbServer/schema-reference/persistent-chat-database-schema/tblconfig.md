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
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig enthält eine nicht unterstützte Konfiguration für beständigen Chat Server in einer Zeile.
ms.openlocfilehash: 244eebcb88c67b521022f9d64888678f221d2369
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295454"
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
   

