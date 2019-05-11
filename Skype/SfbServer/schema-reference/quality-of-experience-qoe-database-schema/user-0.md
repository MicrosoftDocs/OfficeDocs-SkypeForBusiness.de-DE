---
title: User-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: Die Benutzer-Tabelle ist eine Tabelle, die eine Liste der verschiedenen Benutzer gespeichert, die in der Datenbank aufgezeichnet Sitzungen teilgenommen haben. Jeder Datensatz in der Tabelle steht für einen Benutzer.
ms.openlocfilehash: 426d272a5c8bee2fd37511edc62bcb3e1a0c533e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907038"
---
# <a name="user-table"></a>User-Tabelle
 
Die Benutzer-Tabelle ist eine Tabelle, die eine Liste der verschiedenen Benutzer gespeichert, die in der Datenbank aufgezeichnet Sitzungen teilgenommen haben. Jeder Datensatz in der Tabelle steht für einen Benutzer.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diesen Benutzer identifiziert.  <br/> |
|**URI** <br/> |nvarchar(450)  <br/> |Eindeutige  <br/> |URI-Zeichenfolge.  <br/> |
|**URIType** <br/> |int  <br/> ||1 ist Unbekannter URI-Typ.  <br/> 2 ist der URI des Benutzers.  <br/> 4 ist die Konferenz-URI.  <br/> 8 ist Telefon-URI.  <br/> |
|**TenantKey** <br/> |int  <br/> |Ausländisch  <br/> |Mandant des Benutzers, verwiesen von Tenant-Tabelle.  <br/> |
|**LastPoorCallTime** <br/> |datetime  <br/> ||Letzter Zeitstempel, wenn der Benutzer einen Anruf mit schlechten Audioqualität hatte.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Nur zur internen Verwendung.  <br/> |
   

