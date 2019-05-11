---
title: ClientVersions-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: Die ClientVersions-Tabelle ist eine unterstützende Tabelle, die eine Liste der verschiedenen Clienttypen gespeichert, und Versionen, die in der Datenbank aufgezeichnet Sitzungen teilgenommen haben. Jeder Datensatz in der Tabelle steht für eine Clientversion.
ms.openlocfilehash: 86711c89baf374576ee53c64a67688cde10103cc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901443"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>ClientVersions-Tabelle in Skype für Business Server 2015
 
Die ClientVersions-Tabelle ist eine unterstützende Tabelle, die eine Liste der verschiedenen Clienttypen gespeichert, und Versionen, die in der Datenbank aufgezeichnet Sitzungen teilgenommen haben. Jeder Datensatz in der Tabelle steht für eine Clientversion.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Primary  <br/> |Eindeutige Zahl, identifiziert dieser Clienttyp und Version.  <br/> |
|**Version** <br/> |**nvarchar(256)** <br/> ||Versionsname  <br/> |
|**Clienttyp** <br/> |int  <br/> ||Gibt den Typ des Clients, die in der Sitzung verwendet. [UserAgentDef-Tabelle](useragentdef.md) Weitere Informationen finden Sie. <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
   

