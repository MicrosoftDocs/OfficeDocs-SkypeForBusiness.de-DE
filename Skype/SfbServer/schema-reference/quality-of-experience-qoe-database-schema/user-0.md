---
title: User-Tabelle
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
ms.localizationpriority: medium
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: Bei der User-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Darin wird eine Liste der verschiedenen Benutzer gespeichert, die an in der Datenbank aufgezeichneten Sitzungen beteiligt waren. Jeder Datensatz in der Tabelle steht für einen Benutzer.
ms.openlocfilehash: 4278c3649ea55db969295f4068fcfe268a7258bb
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582549"
---
# <a name="user-table"></a>User-Tabelle
 
Bei der User-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Darin wird eine Liste der verschiedenen Benutzer gespeichert, die an in der Datenbank aufgezeichneten Sitzungen beteiligt waren. Jeder Datensatz in der Tabelle steht für einen Benutzer.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diesen Benutzer identifiziert.  <br/> |
|**uri** <br/> |nvarchar(450)  <br/> |Eigen  <br/> |URI-Zeichenfolge  <br/> |
|**URIType** <br/> |int  <br/> ||1 ist ein unbekannter URI-Typ.  <br/> 2 ist ein Benutzer-URI.  <br/> 4 ist ein Konferenz-URI.  <br/> 8 ist ein Telefon-URI.  <br/> |
|**TenantKey** <br/> |int  <br/> |Ausländisch  <br/> |Mandant des Benutzers. Verweis von der tenant-Tabelle.  <br/> |
|**LastPoorCallTime** <br/> |Datum/Uhrzeit  <br/> ||Letzter Zeitstempel, an dem der Benutzer einen Anruf mit schlechter Audioqualität geführt hat.  <br/> |
|**NextUpdateTS** <br/> |Datum/Uhrzeit  <br/> ||Ausschließlich für interne Zwecke.  <br/> |
   

