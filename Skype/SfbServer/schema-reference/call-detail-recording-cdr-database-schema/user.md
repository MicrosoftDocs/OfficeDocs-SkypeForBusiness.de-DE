---
title: User-Ansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: Die Ansicht des Benutzers speichert Informationen zu Benutzer wurden beteiligt anrufen und Sitzungen, die Datensätze in der Datenbank verfügen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: f4e255f2de8dd087308ee46c64ef301cc0e9d390
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930078"
---
# <a name="user-view"></a>User-Ansicht
 
Die Ansicht des Benutzers speichert Informationen zu Benutzer wurden beteiligt anrufen und Sitzungen, die Datensätze in der Datenbank verfügen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|Benutzer-ID  <br/> |int  <br/> |Eindeutige Zahl, die diesen Benutzer identifiziert.  <br/> |
|UserUri  <br/> |nvarchar(450)  <br/> |Der URI des Benutzers.  <br/> |
|TenantKey  <br/> |uniqueidentifier  <br/> |Mandant des Benutzers. Finden Sie weitere Informationen der [Tenants-Tabelle](tenants.md) . <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |Typ des Benutzer-URI. Finden Sie weitere Informationen der [UriTypes-Tabelle](uritypes.md) . <br/> |
   

