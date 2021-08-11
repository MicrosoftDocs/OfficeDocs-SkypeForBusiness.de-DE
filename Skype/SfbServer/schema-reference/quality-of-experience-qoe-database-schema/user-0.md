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
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: Bei der User-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Darin wird eine Liste der verschiedenen Benutzer gespeichert, die an in der Datenbank aufgezeichneten Sitzungen beteiligt waren. Jeder Datensatz in der Tabelle steht für einen Benutzer.
ms.openlocfilehash: 87e6e24ea9bf1073411eeb8c930e8e6fb509ae115242b529331aa43a25d5ac11
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54329330"
---
# <a name="user-table"></a>User-Tabelle
 
Bei der User-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Darin wird eine Liste der verschiedenen Benutzer gespeichert, die an in der Datenbank aufgezeichneten Sitzungen beteiligt waren. Jeder Datensatz in der Tabelle steht für einen Benutzer.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |Ganzzahl  <br/> |Primary  <br/> |Eindeutige Zahl, die diesen Benutzer identifiziert.  <br/> |
|**uri** <br/> |nvarchar(450)  <br/> |Eigen  <br/> |URI-Zeichenfolge  <br/> |
|**URIType** <br/> |Ganzzahl  <br/> ||1 ist ein unbekannter URI-Typ.  <br/> 2 ist ein Benutzer-URI.  <br/> 4 ist ein Konferenz-URI.  <br/> 8 ist ein Telefon-URI.  <br/> |
|**TenantKey** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |Mandant des Benutzers. Verweis von der tenant-Tabelle.  <br/> |
|**LastPoorCallTime** <br/> |Datum/Uhrzeit  <br/> ||Letzter Zeitstempel, an dem der Benutzer einen Anruf mit schlechter Audioqualität geführt hat.  <br/> |
|**NextUpdateTS** <br/> |Datum/Uhrzeit  <br/> ||Ausschließlich für interne Zwecke.  <br/> |
   

