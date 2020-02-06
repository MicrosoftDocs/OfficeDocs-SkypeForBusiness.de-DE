---
title: Roles-Tabelle
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
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: Die Tabelle "Rollen" ist eine statische Tabelle, in der die Liste möglicher Konferenz Rollen wie Teilnehmer und Referenten gespeichert ist.
ms.openlocfilehash: 8ebd01bc9cc51b33d28f87aa85be1473a6397201
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814933"
---
# <a name="roles-table"></a>Roles-Tabelle
 
Die Tabelle "Rollen" ist eine statische Tabelle, in der die Liste möglicher Konferenz Rollen wie Teilnehmer und Referenten gespeichert ist.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**Rolle** <br/> |nvarchar(256)  <br/> || Zulässige Werte: <br/>  0 – unbekannt <br/>  1-Referent <br/>  2 – Teilnehmer <br/> |
   

