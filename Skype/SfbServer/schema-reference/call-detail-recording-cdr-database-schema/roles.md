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
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: Die Tabelle "Rollen" ist eine statische Tabelle, in der die Liste möglicher Konferenz Rollen wie Teilnehmer und Referenten gespeichert ist.
ms.openlocfilehash: 2cf1fb22230d92951df0b3b8e18a5bd666c73519
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295895"
---
# <a name="roles-table"></a>Roles-Tabelle
 
Die Tabelle "Rollen" ist eine statische Tabelle, in der die Liste möglicher Konferenz Rollen wie Teilnehmer und Referenten gespeichert ist.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**Rolle** <br/> |nvarchar(256)  <br/> || Zulässige Werte: <br/>  0 – unbekannt <br/>  1-Referent <br/>  2 – Teilnehmer <br/> |
   

