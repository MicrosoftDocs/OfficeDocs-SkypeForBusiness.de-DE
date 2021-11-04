---
title: Users-Tabelle
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: Die Tabelle Users ist eine Unterstützende Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zu einem Benutzer, der an Anrufen oder Sitzungen mit Datensätzen in der Datenbank beteiligt ist.
ms.openlocfilehash: 7f3fb7fc015da4f96ab458a4ad40ccd1b2addbee
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741911"
---
# <a name="users-table"></a>Users-Tabelle
 
Die Tabelle Users ist eine Unterstützende Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zu einem Benutzer, der an Anrufen oder Sitzungen mit Datensätzen in der Datenbank beteiligt ist.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |Datum/Uhrzeit  <br/> ||Zeitstempel für die interne Verwendung.  <br/> |
|**UserId** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diesen Benutzer identifiziert.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> | <br/> |Benutzer-URI  <br/> |
|**TenantId** <br/> |int  <br/> |Ausländisch  <br/> |Die Mandanten-ID dieses Benutzers. Weitere Informationen finden Sie in der [Tabelle "Mandanten".](tenants.md) <br/> |
|**UriTypeId** <br/> |int  <br/> |Ausländisch  <br/> |Der URI-Typ dieses Benutzers. Weitere Informationen finden Sie in der [UriTypes-Tabelle.](uritypes.md) <br/> |
   

