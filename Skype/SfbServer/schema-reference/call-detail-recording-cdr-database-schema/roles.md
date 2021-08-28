---
title: Roles-Tabelle
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
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: Die Roles-Tabelle ist eine statische Tabelle, in der die Liste möglicher Konferenzrollen gespeichert wird, z. B. Teilnehmer und Referenten.
ms.openlocfilehash: 037197d12a83c5b79de22c0b7faef435d365da41
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58635879"
---
# <a name="roles-table"></a>Roles-Tabelle
 
Die Roles-Tabelle ist eine statische Tabelle, in der die Liste möglicher Konferenzrollen gespeichert wird, z. B. Teilnehmer und Referenten.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |Tinyint  <br/> |Primary  <br/> ||
|**Rolle** <br/> |nvarchar(256)  <br/> || Gültige Werte: <br/>  0 – Unbekannt <br/>  1 – Referent <br/>  2 – Teilnehmer <br/> |
   

