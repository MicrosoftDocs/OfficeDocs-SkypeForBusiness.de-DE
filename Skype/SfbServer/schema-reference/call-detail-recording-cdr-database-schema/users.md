---
title: Users-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: Die Benutzer-Tabelle ist eine Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zu einem Benutzer Beteiligten in anrufen und Sitzungen, die Datensätze in der Datenbank verfügen.
ms.openlocfilehash: fbe3ff7d2570f78cdf3b3418629fb9fd6209d944
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929987"
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
   

