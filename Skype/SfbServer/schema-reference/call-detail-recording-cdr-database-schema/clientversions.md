---
title: ClientVersions-Tabelle in Skype für Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: Die ClientVersions-Tabelle ist eine unterstützende Tabelle, die eine Liste der verschiedenen Clienttypen gespeichert, und Versionen, die in der Datenbank aufgezeichnet Sitzungen teilgenommen haben. Jeder Datensatz in der Tabelle steht für eine Clientversion.
ms.openlocfilehash: 488c7f4211eacb6fc496d6198258c119641ebd14
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>ClientVersions-Tabelle in Skype für Business Server 2015
 
Die ClientVersions-Tabelle ist eine unterstützende Tabelle, die eine Liste der verschiedenen Clienttypen gespeichert, und Versionen, die in der Datenbank aufgezeichnet Sitzungen teilgenommen haben. Jeder Datensatz in der Tabelle steht für eine Clientversion.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Primary  <br/> |Eindeutige Zahl, identifiziert dieser Clienttyp und Version.  <br/> |
|**Version** <br/> |**nvarchar(256)** <br/> ||Versionsname  <br/> |
|**Clienttyp** <br/> |int  <br/> ||Gibt den Typ des Clients, die in der Sitzung verwendet. [UserAgentDef-Tabelle](useragentdef.md) Weitere Informationen finden Sie. <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
   

