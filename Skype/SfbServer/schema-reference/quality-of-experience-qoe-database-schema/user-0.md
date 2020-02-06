---
title: User-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: Die Tabelle Benutzer ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Benutzer gespeichert ist, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden. Jeder Datensatz in der Tabelle steht für einen Benutzer.
ms.openlocfilehash: fcb6c4d45f1392c31ba87637d6e3a1a697f7be9e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805093"
---
# <a name="user-table"></a>User-Tabelle
 
Die Tabelle Benutzer ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Benutzer gespeichert ist, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden. Jeder Datensatz in der Tabelle steht für einen Benutzer.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Nummer, die diesen Benutzer kennzeichnet.  <br/> |
|**URI** <br/> |nvarchar (450)  <br/> |Eindeutigen  <br/> |URI-Zeichenfolge.  <br/> |
|**URIType** <br/> |int  <br/> ||1 ist ein Unbekannter URI-Typ.  <br/> 2 ist ein Benutzer-URI.  <br/> 4 ist Konferenz-URI.  <br/> 8 ist ein Telefon-URI.  <br/> |
|**TenantKey** <br/> |int  <br/> |Fremd  <br/> |Der Mandant des Benutzers, auf den die Mandantentabelle verweist.  <br/> |
|**LastPoorCallTime** <br/> |datetime  <br/> ||Letzter Zeitstempel, wenn der Benutzer einen schlechten Audioanruf hatte.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Nur für interne Verwendung.  <br/> |
   

