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
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: Die ClientVersions-Tabelle ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Clienttypen und-Versionen gespeichert ist, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden. Jeder Datensatz in der Tabelle stellt eine Client Version dar.
ms.openlocfilehash: b42bc79fb04ca4ce2ef88fb7c280db7bc281e23b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296511"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>ClientVersions-Tabelle in Skype for Business Server 2015
 
Die ClientVersions-Tabelle ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Clienttypen und-Versionen gespeichert ist, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden. Jeder Datensatz in der Tabelle stellt eine Client Version dar.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**VersionID** <br/> |**int** <br/> |Primary  <br/> |Eindeutige Nummer, die diesen Clienttyp und die Version identifiziert.  <br/> |
|**Version** <br/> |**nvarchar(256)** <br/> ||Versionsname.  <br/> |
|**Clienttyp** <br/> |int  <br/> ||Gibt den Typ des in der Sitzung verwendeten Clients an. Weitere Informationen finden Sie in der [UserAgentDef-Tabelle](useragentdef.md) . <br/> Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
   

