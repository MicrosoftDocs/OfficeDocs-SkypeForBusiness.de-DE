---
title: Users-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: Die Tabelle Benutzer ist eine unterstützende Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zu einem Benutzer an anrufen oder Sitzungen mit Datensätzen in der Datenbank.
ms.openlocfilehash: 21d03dc2214ac74188094c10a7b53ec84b8a51a9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814803"
---
# <a name="users-table"></a>Users-Tabelle
 
Die Tabelle Benutzer ist eine unterstützende Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zu einem Benutzer an anrufen oder Sitzungen mit Datensätzen in der Datenbank.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> ||Zeitstempel für die interne Verwendung.  <br/> |
|**UserID** <br/> |int  <br/> |Primary  <br/> |Eindeutige Nummer, die diesen Benutzer kennzeichnet.  <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> | <br/> |Benutzer-URI.  <br/> |
|**Mandanten** <br/> |int  <br/> |Fremd  <br/> |Die Mandanten-ID des Benutzers. Weitere Informationen finden Sie in der [Tabelle Mandanten](tenants.md) . <br/> |
|**UriTypeId** <br/> |int  <br/> |Fremd  <br/> |Der URI-Typ des Benutzers. Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) . <br/> |
   

