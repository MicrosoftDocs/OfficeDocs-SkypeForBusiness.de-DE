---
title: User-Ansicht
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: Die Ansicht des Benutzers speichert Informationen zu Benutzer wurden beteiligt anrufen und Sitzungen, die Datensätze in der Datenbank verfügen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 9e631c101660e8f14bca25f019f5d991a0d9aadd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877643"
---
# <a name="user-view"></a>User-Ansicht
 
Die Ansicht des Benutzers speichert Informationen zu Benutzer wurden beteiligt anrufen und Sitzungen, die Datensätze in der Datenbank verfügen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|Benutzer-ID  <br/> |int  <br/> |Eindeutige Zahl, die diesen Benutzer identifiziert.  <br/> |
|UserUri  <br/> |nvarchar(450)  <br/> |Der URI des Benutzers.  <br/> |
|TenantKey  <br/> |uniqueidentifier  <br/> |Mandant des Benutzers. Finden Sie weitere Informationen der [Tenants-Tabelle](tenants.md) . <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |Typ des Benutzer-URI. Finden Sie weitere Informationen der [UriTypes-Tabelle](uritypes.md) . <br/> |
   

