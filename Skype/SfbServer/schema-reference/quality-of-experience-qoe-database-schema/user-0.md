---
title: Benutzertabelle
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: Bei der User-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Darin wird eine Liste der verschiedenen Benutzer gespeichert, die an in der Datenbank aufgezeichneten Sitzungen beteiligt waren. Jeder Datensatz in der Tabelle steht für einen Benutzer.
ms.openlocfilehash: 5c84f0b947199fa497964cb1689dccc571a98d14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800075"
---
# <a name="user-table"></a>Benutzertabelle
 
Bei der User-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Darin wird eine Liste der verschiedenen Benutzer gespeichert, die an in der Datenbank aufgezeichneten Sitzungen beteiligt waren. Jeder Datensatz in der Tabelle steht für einen Benutzer.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diesen Benutzer identifiziert.  <br/> |
|**uri** <br/> |nvarchar(450)  <br/> |Eigen  <br/> |URI-Zeichenfolge  <br/> |
|**URIType** <br/> |int  <br/> ||1 ist ein unbekannter URI-Typ.  <br/> 2 ist ein Benutzer-URI.  <br/> 4 ist ein Konferenz-URI.  <br/> 8 ist ein Telefon-URI.  <br/> |
|**TenantKey** <br/> |int  <br/> |Fremd  <br/> |Mandant des Benutzers. Verweis von der tenant-Tabelle.  <br/> |
|**LastPoorCallTime** <br/> |Datum/Uhrzeit  <br/> ||Letzter Zeitstempel, an dem der Benutzer einen Anruf mit schlechter Audioqualität geführt hat.  <br/> |
|**NextUpdateTS** <br/> |Datum/Uhrzeit  <br/> ||Ausschließlich für interne Zwecke.  <br/> |
   

