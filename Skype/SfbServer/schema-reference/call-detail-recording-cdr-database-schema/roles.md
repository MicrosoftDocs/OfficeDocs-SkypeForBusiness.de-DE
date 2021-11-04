---
title: Roles-Tabelle
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
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: Die Roles-Tabelle ist eine statische Tabelle, in der die Liste möglicher Konferenzrollen gespeichert wird, z. B. Teilnehmer und Referenten.
ms.openlocfilehash: 2bd15fd98aff2ce8066a396efac0b538d4891a8f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776155"
---
# <a name="roles-table"></a>Roles-Tabelle
 
Die Roles-Tabelle ist eine statische Tabelle, in der die Liste möglicher Konferenzrollen gespeichert wird, z. B. Teilnehmer und Referenten.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |Tinyint  <br/> |Primary  <br/> ||
|**Rolle** <br/> |nvarchar(256)  <br/> || Gültige Werte: <br/>  0 – Unbekannt <br/>  1 – Referent <br/>  2 – Teilnehmer <br/> |
   

