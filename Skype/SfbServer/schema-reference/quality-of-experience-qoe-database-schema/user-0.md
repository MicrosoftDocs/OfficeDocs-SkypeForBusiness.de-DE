---
title: User-Tabelle
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: Die Benutzer-Tabelle ist eine Tabelle, die eine Liste der verschiedenen Benutzer gespeichert, die in der Datenbank aufgezeichnet Sitzungen teilgenommen haben. Jeder Datensatz in der Tabelle steht für einen Benutzer.
ms.openlocfilehash: 3261133b8c36fe96fd847c075dce0be2a903c417
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="user-table"></a>User-Tabelle
 
Die Benutzer-Tabelle ist eine Tabelle, die eine Liste der verschiedenen Benutzer gespeichert, die in der Datenbank aufgezeichnet Sitzungen teilgenommen haben. Jeder Datensatz in der Tabelle steht für einen Benutzer.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diesen Benutzer identifiziert.  <br/> |
|**URI** <br/> |nvarchar(450)  <br/> |Eindeutige  <br/> |URI-Zeichenfolge.  <br/> |
|**URIType** <br/> |int  <br/> ||1 ist Unbekannter URI-Typ.  <br/> 2 ist der URI des Benutzers.  <br/> 4 ist die Konferenz-URI.  <br/> 8 ist Telefon-URI.  <br/> |
|**TenantKey** <br/> |int  <br/> |Fremdschlüssel  <br/> |Mandant des Benutzers, verwiesen von Tenant-Tabelle.  <br/> |
|**LastPoorCallTime** <br/> |datetime  <br/> ||Letzter Zeitstempel, wenn der Benutzer einen Anruf mit schlechten Audioqualität hatte.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Nur zur internen Verwendung.  <br/> |
   

