---
title: ClientVersions-Tabelle in Skype for Business Server 2015
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
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: Die ClientVersions-Tabelle ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Clienttypen und-Versionen gespeichert ist, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden. Jeder Datensatz in der Tabelle stellt eine Client Version dar.
ms.openlocfilehash: c616f7d44d138732e96f2d71c7fdf0197c75ca5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815403"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>ClientVersions-Tabelle in Skype for Business Server 2015
 
Die ClientVersions-Tabelle ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Clienttypen und-Versionen gespeichert ist, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden. Jeder Datensatz in der Tabelle stellt eine Client Version dar.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**VersionID** <br/> |**int** <br/> |Primary  <br/> |Eindeutige Nummer, die diesen Clienttyp und die Version identifiziert.  <br/> |
|**Version** <br/> |**nvarchar(256)** <br/> ||Versionsname.  <br/> |
|**Clienttyp** <br/> |int  <br/> ||Gibt den Typ des in der Sitzung verwendeten Clients an. Weitere Informationen finden Sie in der [UserAgentDef-Tabelle](useragentdef.md) . <br/> Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
   

