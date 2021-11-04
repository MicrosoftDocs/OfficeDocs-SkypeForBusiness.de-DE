---
title: UserStatistics-Tabelle
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: Die UserStatistics-Tabelle ist eine Unterstützende Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zur Nutzung des Systems durch einen einzelnen Benutzer. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 01f002e1cba20200334f8696f9fb2c20c98e82c1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756448"
---
# <a name="userstatistics-table"></a>UserStatistics-Tabelle
 
Die UserStatistics-Tabelle ist eine Unterstützende Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zur Nutzung des Systems durch einen einzelnen Benutzer. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserId** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diesen Benutzer identifiziert.  <br/> |
|**LastLogInTime** <br/> |Datum/Uhrzeit  <br/> ||Zeitpunkt, zu dem sich der Benutzer zuletzt angemeldet hat.  <br/> |
|**LastConfOrganizedTime** <br/> |Datum/Uhrzeit  <br/> ||Das letzte Mal, dass der Benutzer eine Konferenz organisiert hat.  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |Datum/Uhrzeit  <br/> ||Beim letzten Auftreten eines Anruffehlers für den Benutzer.  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |Datum/Uhrzeit  <br/> ||Das letzte Mal, dass der Benutzer als Konferenzorganisator einen Anruffehler auftrat.  <br/> |
   

