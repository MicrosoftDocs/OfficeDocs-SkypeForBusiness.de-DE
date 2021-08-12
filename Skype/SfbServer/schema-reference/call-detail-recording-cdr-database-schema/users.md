---
title: Users-Tabelle
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
description: Die Tabelle Users ist eine Unterstützende Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zu einem Benutzer, der an Anrufen oder Sitzungen mit Datensätzen in der Datenbank beteiligt ist.
ms.openlocfilehash: 09706bf5b519ce85cd52898911ad6b878b6e5056246c47154f370ae8c75cc774
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302239"
---
# <a name="users-table"></a>Users-Tabelle
 
Die Tabelle Users ist eine Unterstützende Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zu einem Benutzer, der an Anrufen oder Sitzungen mit Datensätzen in der Datenbank beteiligt ist.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |Datum/Uhrzeit  <br/> ||Zeitstempel für die interne Verwendung.  <br/> |
|**UserId** <br/> |Ganzzahl  <br/> |Primary  <br/> |Eindeutige Zahl, die diesen Benutzer identifiziert.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> | <br/> |Benutzer-URI  <br/> |
|**TenantId** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |Die Mandanten-ID dieses Benutzers. Weitere Informationen finden Sie in der [Tabelle "Mandanten".](tenants.md) <br/> |
|**UriTypeId** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |Der URI-Typ dieses Benutzers. Weitere Informationen finden Sie in der [UriTypes-Tabelle.](uritypes.md) <br/> |
   

