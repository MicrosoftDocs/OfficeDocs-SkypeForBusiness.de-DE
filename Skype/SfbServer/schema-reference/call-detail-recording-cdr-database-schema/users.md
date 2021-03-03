---
title: Tabelle "Users"
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: Bei der Tabelle "Users" handelt es sich um eine Tabelle mit Unterstützung. Jeder Datensatz in der Tabelle speichert Informationen zu einem Benutzer, der an Anrufen oder Sitzungen mit Datensätzen in der Datenbank beteiligt ist.
ms.openlocfilehash: 1905efa9b87b0b94c55e3a72e8be86e9ab191661
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831615"
---
# <a name="users-table"></a>Tabelle "Users"
 
Bei der Tabelle "Users" handelt es sich um eine Tabelle mit Unterstützung. Jeder Datensatz in der Tabelle speichert Informationen zu einem Benutzer, der an Anrufen oder Sitzungen mit Datensätzen in der Datenbank beteiligt ist.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |Datum/Uhrzeit  <br/> ||Zeitstempel für die interne Verwendung.  <br/> |
|**UserId** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diesen Benutzer identifiziert.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> | <br/> |Benutzer-URI  <br/> |
|**TenantId** <br/> |int  <br/> |Fremd  <br/> |Die Mandanten-ID dieses Benutzers. Weitere Informationen [finden Sie in der Tabelle "Mandanten".](tenants.md) <br/> |
|**UriTypeId** <br/> |int  <br/> |Fremd  <br/> |Der URI-Typ dieses Benutzers. Weitere Informationen finden Sie in der [Tabelle "UriTypes".](uritypes.md) <br/> |
   

