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
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: Die Tabelle Benutzer ist eine unterstützende Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zu einem Benutzer an anrufen oder Sitzungen mit Datensätzen in der Datenbank.
ms.openlocfilehash: 0dcc2fda73305be2bbe6a7a5c546dac0b05f8273
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295699"
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
   

