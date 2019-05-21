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
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: Die Tabelle Benutzer ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Benutzer gespeichert ist, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden. Jeder Datensatz in der Tabelle steht für einen Benutzer.
ms.openlocfilehash: a9f72793d3b287406b1b3b7e1ad360e7f5abc598
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294614"
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
   

