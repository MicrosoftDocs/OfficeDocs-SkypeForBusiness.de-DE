---
title: Users-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: Die Benutzer-Tabelle ist eine Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zu einem Benutzer Beteiligten in anrufen und Sitzungen, die Datensätze in der Datenbank verfügen.
ms.openlocfilehash: 3929ba33737c107ee60ec1e31beebb1addbb2e3f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885561"
---
# <a name="users-table"></a>Users-Tabelle
 
Die Benutzer-Tabelle ist eine Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zu einem Benutzer Beteiligten in anrufen und Sitzungen, die Datensätze in der Datenbank verfügen.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> ||Zeitstempel für die interne Verwendung.  <br/> |
|**Benutzer-ID** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diesen Benutzer identifiziert.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> | <br/> |Der URI des Benutzers.  <br/> |
|**TenantId** <br/> |int  <br/> |Ausländisch  <br/> |Mandanten-ID des Benutzers Finden Sie weitere Informationen der [Tenants-Tabelle](tenants.md) . <br/> |
|**UriTypeId** <br/> |int  <br/> |Ausländisch  <br/> |URI-Typ des Benutzers. Finden Sie weitere Informationen der [UriTypes-Tabelle](uritypes.md) . <br/> |
   

