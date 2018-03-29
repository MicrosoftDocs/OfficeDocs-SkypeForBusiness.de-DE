---
title: Users-Tabelle
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
ms.openlocfilehash: b14350d060485a57b4af42cbfe26db729872f6f8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="users-table"></a>Users-Tabelle
 
Die Benutzer-Tabelle ist eine Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zu einem Benutzer Beteiligten in anrufen und Sitzungen, die Datensätze in der Datenbank verfügen.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> ||Zeitstempel für die interne Verwendung.  <br/> |
|**Benutzer-ID** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diesen Benutzer identifiziert.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> | <br/> |Der URI des Benutzers.  <br/> |
|**TenantId** <br/> |int  <br/> |Fremdschlüssel  <br/> |Mandanten-ID des Benutzers Finden Sie weitere Informationen der [Tenants-Tabelle](tenants.md) . <br/> |
|**UriTypeId** <br/> |int  <br/> |Fremdschlüssel  <br/> |URI-Typ des Benutzers. Finden Sie weitere Informationen der [UriTypes-Tabelle](uritypes.md) . <br/> |
   

